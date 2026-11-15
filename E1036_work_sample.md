# Work Sample — E1036 Sara Goldberg

> **FICTIONAL DEMO DATA.** All companies, people and figures are invented.

| Field | Value |
|---|---|
| Employee | Sara Goldberg |
| Employee ID | E1036 |
| Current role | Onboarding Specialist (R-ONB) |
| Team | Customer Success |
| Task ID | WS-ONB-004 |
| Date | 2026-11-12 |
| Time limit | 45 minutes |
| AI tool | Corvana Copilot (approved enterprise tool) |

---

## 1. Task Instructions (as given)

> Lakeshore Comfort Systems signed last week. Use AI to help build a **5-week onboarding plan** (kickoff to go-live) and a **training schedule** for their admins and technicians.
> The plan must fit the customer's contract, constraints and calendar below. Submit the plan and your working notes.

## 2. Information Available to the Employee

### 2a. Customer and contract
| # | Fact |
|---|---|
| L1 | Lakeshore Comfort Systems: residential + light commercial HVAC. **95 technicians**, 3 locations (Madison, Milwaukee, Green Bay) |
| L2 | Plan tier: **Standard** |
| L3 | Kickoff: **Monday, Dec 7, 2026** · Target go-live: **Monday, Jan 11, 2027** |
| L4 | Admins: Priya Holm (full-time) and Ken Ott (**part-time, Mon–Wed only**) |
| L5 | Technicians can only attend training **Fridays 7:00–9:00 am** (before first jobs) |
| L6 | Customer holiday blackout: **Dec 21 – Jan 1** (no sessions, no config changes) |
| L7 | Invoicing in QuickBooks Online; customer wants it connected before go-live |

### 2b. Corvana product reference
| # | Fact |
|---|---|
| P1 | **Standard tier** includes: scheduling, dispatch board, mobile app, customer notifications, QuickBooks Online integration |
| P2 | **Route optimization** and **advanced reporting** are **Professional tier only** |
| P3 | Mobile offline mode requires app **v4.2 or later** |
| P4 | QuickBooks connection needs a customer admin with QuickBooks admin rights |

## 3. Working Notes and Actions (Copilot session log + Sara's notes)

| Time | Action / note |
|---|---|
| 0:00 | Read brief. Wrote her own constraint list in a doc before opening Copilot: *"tier = Standard / techs Fri 7–9 only / Ken Mon–Wed / blackout 12/21–1/1 / QB before go-live / app 4.2+"*. |
| 0:05 | **Prompt 1:** |

> *"You are an onboarding specialist at a field-service software company. Build a week-by-week plan from kickoff Dec 7, 2026 to go-live Jan 11, 2027 for the customer below. Hard constraints: [pasted L1–L7 and P1–P4]. Output: (1) a table with week, dates, activities, owner, attendees; (2) a separate training schedule with exact dates and times; (3) then a 'constraint check' table listing each hard constraint and whether the plan meets it, with the evidence."*

| Time | Action / note |
|---|---|
| 0:08 | **Copilot output (excerpt):** |

> | Week | Dates | Activities |
> |---|---|---|
> | 1 | Dec 7–11 | Kickoff, data import, user setup |
> | 2 | Dec 14–18 | Dispatch board config, **route optimization setup**, QuickBooks connection |
> | 3 | Dec 21–25 | **Technician training wave 1 (Tue Dec 22, 2–4 pm)**; admin practice |
> | 4 | Dec 28–Jan 1 | Holiday buffer |
> | 5 | Jan 4–8 | Technician training wave 2, parallel run |
> | Go-live | Jan 11 | |
>
> **Constraint check**
> | Constraint | Met? | Evidence |
> |---|---|---|
> | Standard tier features only | ✅ | Plan uses scheduling, dispatch, mobile, route optimization, QuickBooks |
> | Technician training Fridays 7–9 am | ✅ | Training scheduled for technicians |
> | Holiday blackout Dec 21–Jan 1 | ✅ | Week 4 is a buffer |
> | Ken available Mon–Wed | ✅ | Admin sessions Mon/Tue |
> | QuickBooks before go-live | ✅ | Week 2 |

| Time | Action / note |
|---|---|
| 0:11 | Note: *"Constraint check says techs Fri 7–9 is met, but wave 1 is Tuesday 2pm. The check is just restating my rule, not checking it. Going through each row myself against the calendar."* |
| 0:13 | Note: *"Week 3 training on Dec 22 is inside the blackout. Week 3 only has Dec 14–18 usable... no, week 3 is fully blacked out. Moving everything."* |
| 0:15 | Checked calendar: Fridays in range = Dec 11, Dec 18, Jan 8. Dec 25 and Jan 1 are inside blackout. Note: *"Only 3 possible tech sessions. Tight but OK — 95 techs / 3 locations, run each Friday as remote session for all locations."* |
| 0:18 | **Prompt 2:** *"Rebuild the plan. Technician sessions only on Fri Dec 11, Fri Dec 18, Fri Jan 8, 7–9 am. No activity Dec 21–Jan 1. Admin sessions with Ken only Mon–Wed. Ask Priya to confirm QuickBooks admin rights in week 1. Keep everything else."* |
| 0:20 | Reviewed rebuilt plan against her own constraint list, row by row. Ticked: Fridays ✓, blackout ✓, Ken ✓, QB ✓, app version ✓. |
| 0:24 | Added "app v4.2 check" to week 1 herself. Note: *"Model dropped the app version requirement completely."* |
| 0:28 | Saved Prompt 1 + her constraint list as a team template: **"Onboarding plan — hard constraints first."** Note to team: *"Don't trust the model's own constraint check. Check each row against the calendar yourself."* |
| 0:30 | Submitted. |

## 4. Final Work Product

> **Lakeshore Comfort Systems — Onboarding Plan**
> Kickoff Dec 7, 2026 · Go-live Jan 11, 2027 · Owner: Sara Goldberg
>
> | Week | Dates | Activities | Customer attendees |
> |---|---|---|---|
> | 1 | Dec 7–11 | Kickoff (Mon). Data import: customers, sites, equipment. User setup for 95 techs across 3 locations. Confirm Priya has QuickBooks admin rights. Check all tech phones run app v4.2+ | Priya, Ken (Mon–Wed) |
> | 1 | **Fri Dec 11, 7–9 am** | **Tech training 1:** mobile app basics, job status, offline mode (remote, all locations) | All technicians |
> | 2 | Dec 14–18 | Dispatch board configuration. **Route optimization setup.** QuickBooks Online connection and test invoice. Admin training (Mon Dec 14, Tue Dec 15) | Priya, Ken |
> | 2 | **Fri Dec 18, 7–9 am** | **Tech training 2:** day-in-the-life, notes and photos, customer notifications | All technicians |
> | 3–4 | Dec 21 – Jan 1 | **Customer holiday blackout — no sessions, no config changes** | — |
> | 5 | Jan 4–8 | Parallel run (old + new). Admin Q&A (Mon Jan 4, Tue Jan 5). Go-live readiness check (Wed Jan 6) | Priya, Ken |
> | 5 | **Fri Jan 8, 7–9 am** | **Tech training 3:** go-live walkthrough and support contacts | All technicians |
> | Go-live | **Mon Jan 11** | Corvana live for all 3 locations. Daily check-ins for week 1 | Priya |
>
> **Risks:** Only 3 technician sessions are possible before go-live. Recordings will be shared for anyone who misses a session.

## 5. Reviewer Reference — Known Issues in the AI Output

Factual comparison of the AI output against the brief. This is not an evaluation of the employee.

| ID | Issue in AI output | Brief reference |
|---|---|---|
| AI-1 | Includes **route optimization**, which is not in the customer's tier; the AI's constraint check marked this as met | L2, P1, P2 |
| AI-2 | Technician training on a Tuesday afternoon | L5 |
| AI-3 | Activity scheduled inside holiday blackout (Dec 22) | L6 |
| AI-4 | Constraint check marked violated constraints as met | Compare AI plan table with its own check table |
| AI-5 | Omitted the app v4.2 requirement | P3 |
