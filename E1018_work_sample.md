# Work Sample — E1018 Fatima Al-Sayed

> **FICTIONAL DEMO DATA.** All companies, people, prices and figures are invented.

| Field | Value |
|---|---|
| Employee | Fatima Al-Sayed |
| Employee ID | E1018 |
| Current role | Account Executive (R-AE) |
| Team | Sales |
| Task ID | WS-AE-002 |
| Date | 2026-11-11 |
| Time limit | 40 minutes |
| AI tool | Corvana Copilot (approved enterprise tool) |

---

## 1. Task Instructions (as given)

> You ran a discovery call with Brightwater Property Services yesterday. Use AI to help prepare a **one-page proposal summary** for their COO.
> Include: the problem in the customer's words, the proposed solution, price, implementation timeline and next steps.
> Use only facts from the discovery notes and Corvana's pricing and product reference below. Submit your final summary and working notes.

## 2. Information Available to the Employee

### 2a. Discovery notes (Fatima's own notes, 2026-11-10)
| # | Fact |
|---|---|
| B1 | Brightwater Property Services, Denver. Commercial property maintenance. **140 field technicians**, 6 dispatchers |
| B2 | Dispatch today: whiteboard + Google Sheets. Invoicing in QuickBooks Online |
| B3 | Technicians average **2.3 jobs/day**; COO's goal is **3 jobs/day** |
| B4 | Overtime cost last year: **$410K** (customer's figure) |
| B5 | Economic buyer: Marcus Lee, COO. Champion: Dana Ortiz, Operations Manager |
| B6 | Wants to be live **before April 1, 2027** (spring HVAC season) |
| B7 | Asked about integration with **QuickBooks Online** and with **FleetTrack** (their GPS vendor) |

### 2b. Corvana pricing & product reference
| # | Fact |
|---|---|
| C1 | List price: **$22 per technician per month**, billed annually |
| C2 | Discount authority: AE up to 15% · 15–20% needs VP Sales · **> 20% requires Deal Desk** |
| C3 | Native integrations include **QuickBooks Online**. **No native FleetTrack integration**; possible via API as SE-scoped custom work |
| C4 | Implementation: **6–8 weeks** for < 200 technicians; 8–10 weeks for 200–500 |
| C5 | Approved claim: customers reduce technician drive time by **18% on average** |

## 3. AI Output Received (first draft from Corvana Copilot)

**Fatima's prompt 1:**
> *"Write a 1-page proposal summary for Brightwater Property Services, COO Marcus Lee. Here are my discovery notes: [pasted B1–B7]. Here is our pricing and product info: [pasted C1–C5]. Make it executive-level, confident, focused on ROI."*

**Copilot draft (excerpt):**
> **Brightwater + Corvana: From Whiteboards to 3 Jobs a Day**
>
> **The challenge:** Your 140 technicians complete 2.3 jobs per day, and overtime cost you $410K last year.
>
> **The solution:** Corvana replaces your whiteboard and spreadsheets with AI-powered scheduling and dispatch, with **native integrations to QuickBooks Online and FleetTrack**, so your GPS data flows straight into dispatch.
>
> **Expected impact:** Customers reduce drive time by 18%, and Brightwater can expect to **cut overtime by 50% (about $205K a year)**.
>
> **Investment:** 140 technicians × $22 × 12 months = **$39,960 per year**. If signed by December 31, we can offer a **25% discount**.
>
> **Timeline:** Go live in **4 weeks**.
>
> **Next steps:** Technical review with Dana Ortiz; executive sign-off by December 15.

## 4. Working Notes and Actions (Copilot session log + Fatima's notes)

| Time | Action / note |
|---|---|
| 0:00 | Sent prompt 1 (above). |
| 0:03 | Read draft. Note: *"Good structure. Headline is strong, keep it."* |
| 0:05 | Opened integrations page. Note: *"FleetTrack is NOT native — C3. If Dana's team asks and it's wrong, deal's dead. Changing to 'API integration, scoped with our SE'."* |
| 0:08 | Note: *"25% discount — I can't offer that without Deal Desk, and I wouldn't lead with it anyway. Removing."* |
| 0:09 | Note: *"4 weeks go-live — no. They're under 200 techs, so 6–8 weeks (C4). Still well before April 1."* |
| 0:11 | Note: *"50% overtime cut — where's that from? Not in my notes, not an approved claim. Replace with their own goal: 2.3 → 3 jobs/day."* |
| 0:13 | **Prompt 2:** *"Rewrite the Expected impact section. Use only: (1) customer's goal of moving from 2.3 to 3 jobs per day, (2) the approved 18% drive time stat. No other numbers. Keep it to 3 sentences."* |
| 0:15 | Accepted rewritten impact section with one wording change. |
| 0:17 | **Prompt 3:** *"Make the tone warmer for a COO who is skeptical of software rollouts."* |
| 0:19 | Kept two sentences from the warmer version. |
| 0:22 | Edited next steps (added SE scoping call for FleetTrack). Investment section left as drafted. |
| 0:25 | Submitted. |

## 5. Final Work Product

> **Brightwater + Corvana: From Whiteboards to 3 Jobs a Day**
> *Prepared for Marcus Lee, COO · November 2026*
>
> **Where you are today**
> Your 140 technicians average 2.3 jobs a day, dispatched from a whiteboard and shared spreadsheets. Overtime cost Brightwater $410K last year, and your goal is 3 jobs per technician per day before spring HVAC season.
>
> **What we propose**
> Corvana replaces the whiteboard and spreadsheets with one scheduling and dispatch board your 6 dispatchers can run together. It connects natively to QuickBooks Online, so completed jobs flow straight to invoicing. For FleetTrack, we'll scope an API integration with our Solutions Engineer so GPS locations show up in dispatch.
>
> **Expected impact**
> Corvana customers reduce technician drive time by 18% on average. Less time on the road is the most direct path from 2.3 to 3 jobs a day. We'll set up reporting from day one so you can track that number weekly.
>
> **Investment**
> 140 technicians × $22 × 12 months = **$39,960 per year**.
>
> **Timeline**
> Typical go-live for teams your size is 6–8 weeks, which puts you live well ahead of April 1.
>
> **Next steps**
> 1. FleetTrack scoping call with Dana Ortiz and our Solutions Engineer (week of Nov 16)
> 2. Proposal review with Marcus Lee
> 3. Target signature mid-December for a February go-live
>
> — Fatima Al-Sayed, Account Executive

## 6. Reviewer Reference — Known Issues in the AI Draft

Factual comparison of the AI draft against the brief. This is not an evaluation of the employee.

| ID | Issue in AI draft | Brief reference |
|---|---|---|
| AI-1 | Claims native FleetTrack integration | C3: no native integration |
| AI-2 | "Cut overtime by 50% (about $205K)" — unsupported figure | Not in B1–B7 or C5 |
| AI-3 | Price arithmetic: 140 × $22 × 12 = **$36,960**, not $39,960 | C1, B1 |
| AI-4 | Offers 25% discount | C2: > 20% requires Deal Desk |
| AI-5 | 4-week go-live | C4: 6–8 weeks for < 200 technicians |
