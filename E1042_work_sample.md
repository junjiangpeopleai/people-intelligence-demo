# Work Sample — E1042 Rachel Stein

> **FICTIONAL DEMO DATA.** All companies, people, tables and figures are invented.

| Field | Value |
|---|---|
| Employee | Rachel Stein |
| Employee ID | E1042 |
| Current role | Revenue Operations Analyst (R-RO) |
| Team | RevOps |
| Task ID | WS-RO-005 |
| Date | 2026-11-13 |
| Time limit | 60 minutes |
| AI tool | Corvana Copilot (approved enterprise tool) |

---

## 1. Task Instructions (as given)

> Two parts. Use AI as you see fit.
> **Part A:** Write a SQL query that returns **Q3 2026 forecast accuracy per Account Executive**, using Corvana's definition below. Test it on the sample data.
> **Part B:** Write instructions for the planned **CRM logging agent** (`agent.crm_logger`), which will turn AE call transcripts into Salesforce activity notes. Include at least 3 failure cases and when a human must review.
> Submit the query, test results, agent instructions and working notes.

## 2. Information Available to the Employee

### 2a. Corvana metric definition (RevOps handbook)
> **Forecast accuracy** = 1 − |closed-won amount in quarter − week-1 commit| / week-1 commit, per AE.
> **Week-1 commit** = the `commit` snapshot taken on the **first Monday of the quarter**. Later snapshots are not used for accuracy.

### 2b. Schema
```
opportunities(opp_id, owner_id, amount, stage, close_date)
forecast_snapshots(snapshot_date, owner_id, snapshot_type, amount)   -- weekly snapshots; snapshot_type in ('commit','best_case')
users(user_id, name, role)
```
Q3 2026 = Jul 1 – Sep 30. First Monday of Q3 = **2026-07-06**.

### 2c. Sample data (Q3 2026, two AEs)
| owner | Week-1 commit (Jul 6) | Last commit snapshot (Sep 28) | Closed-won Q3 | Closed-won opps |
|---|---|---|---|---|
| U101 | $200,000 | $170,000 | $180,000 | 3 |
| U102 | $150,000 | $160,000 | $165,000 | 2 |

Finance-reported closed-won Q3 total for these two AEs: **$345,000**.

### 2d. CRM data policy (excerpt)
> Activity notes must **not** contain personal phone numbers, personal email addresses or health information about customer contacts. Pricing commitments must be logged only by the AE.

## 3. Working Notes and Actions — Part A (SQL)

| Time | Action / note |
|---|---|
| 0:00 | **Prompt 1:** *"Write Snowflake SQL for standard forecast accuracy per AE for Q3 2026. Tables: [pasted schema]. Accuracy = 1 - abs(actual - commit)/commit."* (Handbook definition of which snapshot to use was not included.) |
| 0:02 | **Copilot query (excerpt):** |

```sql
SELECT u.name,
       SUM(o.amount) AS closed_won,
       MAX(f.amount) AS commit_amt,
       1 - ABS(SUM(o.amount) - MAX(f.amount)) / MAX(f.amount) AS accuracy
FROM opportunities o
JOIN forecast_snapshots f ON f.owner_id = o.owner_id AND f.snapshot_type = 'commit'
JOIN users u ON u.user_id = o.owner_id
WHERE o.stage = 'Closed Won'
  AND o.close_date BETWEEN '2026-07-01' AND '2026-09-30'
  AND f.snapshot_date = (SELECT MAX(snapshot_date) FROM forecast_snapshots
                         WHERE snapshot_date <= '2026-09-30')
GROUP BY u.name;
```

| Time | Action / note |
|---|---|
| 0:05 | Ran on sample. Result: U101 closed_won = $180,000, U102 = $165,000. Total $345,000 — matches finance. Note: *"Totals OK here, but only because the subquery pins one snapshot date. If anyone changes that filter to a range, the join fans out — one row per snapshot per opp. Rewriting with CTEs so it's safe."* |
| 0:10 | **Prompt 2:** *"Rewrite using two CTEs: one aggregating closed-won per owner, one selecting the commit snapshot per owner. Join at owner level only. Add a NULLIF to avoid divide by zero."* |
| 0:13 | Ran rewritten query. U101 accuracy = 0.941, U102 = 0.969. Note: *"Checked by hand: U101 1 − |180−170|/170 = 0.941 ✓. U102 1 − |165−160|/160 = 0.969 ✓."* |
| 0:15 | Added a test: same query with a 3-month snapshot range → totals still $345K. Note: *"Fan-out fixed."* |

**Final query (submitted):**
```sql
WITH won AS (
  SELECT owner_id, SUM(amount) AS closed_won
  FROM opportunities
  WHERE stage = 'Closed Won'
    AND close_date BETWEEN '2026-07-01' AND '2026-09-30'
  GROUP BY owner_id
),
commit_snap AS (
  SELECT owner_id, amount AS commit_amt
  FROM forecast_snapshots
  WHERE snapshot_type = 'commit'
    AND snapshot_date = (SELECT MAX(snapshot_date) FROM forecast_snapshots
                         WHERE snapshot_type = 'commit' AND snapshot_date <= '2026-09-30')
)
SELECT u.name,
       w.closed_won,
       c.commit_amt,
       ROUND(1 - ABS(w.closed_won - c.commit_amt) / NULLIF(c.commit_amt, 0), 3) AS forecast_accuracy
FROM won w
JOIN commit_snap c ON c.owner_id = w.owner_id
JOIN users u ON u.user_id = w.owner_id
ORDER BY forecast_accuracy DESC;
```
**Test results submitted:** U102 0.969 · U101 0.941 · totals reconcile to finance ($345,000).

## 4. Working Notes and Actions — Part B (Agent instructions)

| Time | Action / note |
|---|---|
| 0:20 | Wrote first draft herself. Note: *"Want the structure to be mine; will use Copilot to stress-test."* |
| 0:32 | **Prompt 3:** *"Here are instructions for an agent that writes Salesforce activity notes from call transcripts. Act as a skeptical sales manager. List 5 ways this agent could produce wrong or harmful notes that my instructions don't cover."* |
| 0:34 | Copilot listed: speaker mix-ups, logging a discount mentioned as hypothetical as a commitment, wrong opportunity match, transcripts with poor audio, logging competitor names inconsistently. |
| 0:36 | Note: *"Hypothetical discount = great catch, adding. Competitor naming — minor, adding as a formatting rule. Poor audio — added confidence threshold."* |
| 0:40 | Finalized and submitted. |

**Agent instructions (submitted):**
> **agent.crm_logger — Instructions v0.1**
> **Owner:** GTM Engineer on duty · **Escalation:** RevOps channel
>
> **Goal:** After each AE call, create one Salesforce activity note on the correct opportunity: summary (≤ 120 words), next steps with owner and date, stakeholders mentioned, risks.
>
> **Rules**
> 1. Match the call to an opportunity using the calendar invite's opportunity ID. If no ID, or more than one open opportunity for the account, **do not log**; send to the AE for selection.
> 2. Never log pricing, discounts or contract terms as commitments. If pricing is discussed, write "Pricing discussed — see AE" and notify the AE.
> 3. Treat anything phrased as "what if," "could we," or "hypothetically" as a question, not a decision.
> 4. Attribute statements to a speaker only when the transcript speaker label is present. Otherwise write "a customer attendee said…".
> 5. Write competitor names exactly as in the competitor list. If a name is not on the list, write it as heard and tag `#check-competitor`.
>
> **Human review required when**
> - Transcript confidence is below 85%
> - Pricing, legal terms or churn intent is mentioned
> - The agent could not match an opportunity
>
> **Failure cases and how we catch them**
> | Failure | Detection |
> |---|---|
> | Note logged to the wrong opportunity | Weekly sample of 20 notes reviewed by RevOps; AE can flag with one click |
> | Hypothetical discount logged as agreed | Keyword trigger → mandatory AE review before save |
> | Next step missing owner or date | Schema check; note saved as draft until AE completes it |
> | Speaker misattribution | AE review on all notes for first 30 days, then sampled |

## 5. Reviewer Reference — Known Issues in the AI Output

Factual comparison of the AI output and task brief. This is not an evaluation of the employee.

| ID | Issue | Brief reference |
|---|---|---|
| AI-1 | Copilot's query uses the **latest** commit snapshot (`MAX(snapshot_date)`), not the week-1 snapshot (Jul 6). With the handbook definition, U101 = 1 − 20/200 = **0.900** and U102 = 1 − 15/150 = **0.900** | 2a, 2c |
| AI-2 | Join between opportunities and snapshots at owner level can duplicate rows if more than one snapshot matches | 2b |
| AI-3 | Copilot's list of agent failure modes did not mention personal contact data or health information in notes | 2d |
