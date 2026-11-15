# Work Sample — E1029 Daniel Cho

> **FICTIONAL DEMO DATA.** All companies, people and figures are invented.

| Field | Value |
|---|---|
| Employee | Daniel Cho |
| Employee ID | E1029 |
| Current role | Customer Success Manager (R-CSM) |
| Team | Customer Success |
| Task ID | WS-CSM-003 |
| Date | 2026-11-12 |
| Time limit | 45 minutes |
| AI tool | Corvana Copilot (approved enterprise tool) |

---

## 1. Task Instructions (as given)

> Use AI to analyze the account health export for 8 accounts in your book with renewals in the next 6 months.
> Write a **short renewal-risk memo** to the VP Customer Success: rank the accounts by risk, explain the top 3 risks, and recommend one action for each.
> Only draw conclusions the data supports. Note any data you think is wrong. Customer contact details are included in the export; follow the AI data policy (share only what the analysis needs).

## 2. Information Available to the Employee

### 2a. Account health export (as given)
| Account | ARR | Renewal date | Licensed techs | Active techs (30d) | Logins trend (90d) | Support tickets (90d) | NPS | Primary contact | CSM notes |
|---|---|---|---|---|---|---|---|---|---|
| Copperline Mechanical | $48K | 2026-12-29 | 120 | 104 | Flat | 6 | 42 | j.kerr@copperline.example · (555) 201-3344 | Champion (Jamie Kerr) left company Oct 2026; no replacement contact yet |
| Pinecrest HVAC | $36K | 2027-02-15 | 90 | 51 | Down 38% | 14 | 10 | m.vance@pinecrest.example · (555) 201-7781 | New ops manager started Sep; retraining planned for Nov |
| Ridgeway Facilities | $62K | 2027-03-31 | 150 | 168 | Up 5% | 4 | 55 | a.holt@ridgeway.example · (555) 201-9012 | — |
| Summit Plumbing Co. | $28K | 2027-01-20 | 70 | 66 | Flat | 2 | 61 | r.diaz@summitplumb.example · (555) 201-4456 | Asked about Professional tier |
| Elmwood Electric | $22K | 2027-04-10 | 60 | 30 | Down 12% | 11 | 18 | k.ng@elmwood.example · (555) 201-6623 | Complained about mobile app logouts (ticket #4471) |
| Bayview Service Group | $75K | 2027-05-01 | 200 | 182 | Up 2% | 5 | 48 | t.ross@bayview.example · (555) 201-1199 | — |
| Granite Peak HVAC | $31K | 2027-03-05 | 80 | 70 | Flat | 3 | 39 | l.chen@granitepeak.example · (555) 201-5530 | — |
| Harborline Mechanical | $40K | 2027-02-28 | 110 | 94 | Down 6% | 7 | 33 | s.patel@harborline.example · (555) 201-8874 | Evaluating a competitor (mentioned on Oct QBR) |

### 2b. Note on data
- "Active techs (30d)" = unique technicians who logged into the mobile app in the last 30 days.
- No pricing changes were made to any of these accounts in 2026.

## 3. Working Notes and Actions (Copilot session log + Daniel's notes)

| Time | Action / note |
|---|---|
| 0:00 | Copied export into a sheet. **Deleted the Primary contact column** before pasting. Note: *"Analysis doesn't need emails or phone numbers. Policy says minimum necessary."* |
| 0:04 | **Prompt 1:** |

> *"You are helping a Customer Success Manager assess renewal risk. Data below (8 accounts). For each account: calculate adoption = active techs / licensed techs, days to renewal from 2026-11-12, and list risk signals from all columns including CSM notes. Show your calculations in a table first, then rank by risk. Do not guess causes that are not in the data."*

| Time | Action / note |
|---|---|
| 0:06 | **Copilot output (excerpt):** |

> | Account | Adoption | Days to renewal | Risk |
> |---|---|---|---|
> | Pinecrest HVAC | 57% | 95 | High |
> | Elmwood Electric | 50% | 149 | High |
> | Harborline Mechanical | 85% | 108 | Medium |
> | Copperline Mechanical | 87% | 47 | **Low** |
> | Ridgeway Facilities | **112%** | 139 | Low — excellent adoption |
> | … | | | |
>
> *"Pinecrest HVAC is the highest risk. The 38% drop in logins was likely caused by the price increase in July, which reduced engagement. Elmwood's low NPS reflects general dissatisfaction with the product."*

| Time | Action / note |
|---|---|
| 0:09 | Note: *"Copperline LOW? Renewal in 47 days and the champion left. That's my #1 risk. Model read the numbers and ignored the notes column even though I told it to use it."* |
| 0:11 | Note: *"Ridgeway 112% — can't have more active than licensed. Either they're sharing logins or licensed count is stale. Data issue, not 'excellent adoption'. Flag to RevOps."* |
| 0:13 | Note: *"Elmwood — it's not 'general dissatisfaction', it's the logout bug, ticket #4471. Specific and fixable."* |
| 0:14 | Checked days-to-renewal for 3 accounts by hand. Matched. |
| 0:16 | **Prompt 2:** *"Re-rank, treating 'champion left' and 'evaluating competitor' notes as high-risk signals. Exclude Ridgeway adoption from the ranking and mark it as a data issue."* |
| 0:18 | Accepted new ranking. |
| 0:20 | **Prompt 3:** *"Draft a memo to my VP with the top 3 risks and one action each. Under 200 words."* |
| 0:23 | Edited Elmwood action. Kept rest of draft. |
| 0:26 | Submitted. |

## 4. Final Work Product

> **To:** Derek Coleman, VP Customer Success
> **From:** Daniel Cho
> **Re:** Renewal risk — my book, renewals Dec 2026–May 2027
>
> **Top 3 risks**
>
> 1. **Copperline Mechanical — $48K, renews Dec 29 (47 days).** Our champion Jamie Kerr left in October and we have no new contact. Adoption is healthy (87%), but nobody owns the renewal on their side.
>    *Action:* Exec-to-exec outreach this week to identify a new owner.
>
> 2. **Pinecrest HVAC — $36K, renews Feb 15.** Logins down 38%, adoption 57%, NPS 10, 14 tickets in 90 days. The drop follows the July price increase and a new ops manager starting in September.
>    *Action:* Run the planned retraining in November and book a value review with the new ops manager.
>
> 3. **Harborline Mechanical — $40K, renews Feb 28.** Mentioned evaluating a competitor at the October QBR.
>    *Action:* Prepare a competitive value review with the AE before January.
>
> **Also watching:** Elmwood Electric (adoption 50%, NPS 18). Complaints are tied to the mobile logout bug (#4471); I'll push for a fix date with Support.
>
> **Data issue:** Ridgeway Facilities shows 168 active vs. 150 licensed technicians. Asked RevOps to check for login sharing or a stale license count. Excluded from ranking.

## 5. Reviewer Reference — Known Issues in the AI Output

Factual comparison of the AI output against the brief. This is not an evaluation of the employee.

| ID | Issue in AI output | Brief reference |
|---|---|---|
| AI-1 | Ranked Copperline as low risk; ignored "champion left" in notes | Export, CSM notes column |
| AI-2 | Presented Ridgeway 112% adoption as "excellent" instead of a data anomaly | Export: 168 active > 150 licensed |
| AI-3 | Attributed Pinecrest's login drop to a "July price increase" | 2b: no pricing changes in 2026; notes cite new ops manager |
| AI-4 | Generic cause for Elmwood ("general dissatisfaction") | Notes cite mobile logout bug, ticket #4471 |
