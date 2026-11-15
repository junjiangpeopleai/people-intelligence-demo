# Corvana Future GTM Organization — Proposal (Updated)

> **FICTIONAL FUTURE-STATE PROPOSAL (DEMO DATA).** This document describes a *proposed* organization. It is **not** Corvana's current structure, and no decisions about individual employees have been made. Corvana and all names, roles and figures are invented for a hackathon demo.

**Program:** Project Relay | **Status:** Proposed — for mobility planning | **Version:** 1.0 (transition paths aligned to current role IDs in `04_roles_current_updated.json`) | **Effective (target):** April 30, 2027

---

## 1. Transformation Context

Corvana's GTM org (48 people) is organized in functional silos: SDR → Sales → Onboarding → Customer Success, with RevOps and Marketing as support functions. Growth has slowed (38% → 21% YoY), outbound reply rates are down 41%, AEs spend ~38% of their time on admin, and CSMs carry 70+ accounts each.

The proposal moves GTM to **segment pods supported by a shared Agent Ops & Intelligence team**. AI agents take on repeatable work (lead research, first-touch outreach, inbound response, CRM logging, account health monitoring). People focus on judgment, relationships, and designing and supervising that agent work.

**Goals (FY2027)**
- 50% of first meetings booked through agent-assisted workflows
- 40 new accounts above $80K ACV (upmarket motion)
- Churn risk detected ≥ 60 days before renewal for 90% of accounts
- **85% of affected employees placed in new or adjacent internal roles** (redeploy before hiring externally)

**Principles**
- Every agent has a named human owner. Agents do not make pricing, contract or discount commitments.
- Mobility recommendations are inputs to a conversation between employee, manager and HRBP, never automatic decisions.
- Employee preferences are respected. Nobody is moved against a stated preference without a conversation first.

---

## 2. Future Organization Chart (PROPOSED — NOT CURRENT)

```
[PROPOSED] Corvana GTM Organization — target April 2027
│
├── VP Sales
│   ├── Mid-Market Pod
│   │   ├── Pod Lead (Sales Manager)                    F-PL      x1
│   │   ├── Pipeline Strategist                         F-PS      x2
│   │   ├── Account Executive                           F-AE      x5
│   │   └── Solutions Engineer                          F-SE      x2  (dotted line → SE Lead in Upmarket Pod)
│   │
│   ├── Upmarket Pod
│   │   ├── Pod Lead (Sales Manager)                    F-PL      x1
│   │   ├── Pipeline Strategist                         F-PS      x2
│   │   ├── Enterprise Account Executive                F-EAE     x6
│   │   ├── Account Executive                           F-AE      x3
│   │   └── Solutions Engineer                          F-SE      x2
│   │
│   └── Agent Ops & Intelligence (shared; dotted line → VP Customer Success)
│       ├── Agent Operations Lead                       F-AOL     x1
│       │   ├── GTM Engineer                            F-GTME    x3
│       │   └── Revenue Intelligence Analyst            F-RIA     x2
│       └── Content Strategist (AI-assisted)            F-CS      x2  (dotted line → Pipeline Strategists)
│
└── VP Customer Success
    └── Retention Pod
        ├── Customer Outcomes Manager                   F-COM     x7
        ├── Onboarding Specialist                       F-ONB     x2
        └── AI Enablement Partner                       F-AIE     x1  (serves all GTM pods)

Total proposed roles: 42 + 2 VPs = 44 (vs. 48 today; gap covered by attrition and open roles in other departments)
```

**Agents in the proposed structure (not headcount)**
| Agent | Human owner (role) | Work covered |
|---|---|---|
| `agent.ai_sdr` | Pipeline Strategist (per pod) | Lead research, first-touch outreach, inbound response |
| `agent.crm_logger` (planned) | GTM Engineer | Call notes and CRM updates |
| `agent.account_health` (planned) | Customer Outcomes Manager | Health monitoring and churn alerts |
| `agent.proposal_drafter` (planned) | Account Executive / Enterprise AE | First-draft proposals; Deal Desk approves discounts > 20% |

---

## 3. Future Role Details

**AI literacy levels** follow the AI Literacy Evaluation Skill (file 08): Explorer < Practitioner < Builder < Leader. Dimensions: D1 Concepts & Limits · D2 Prompting · D3 Critical Evaluation · D4 Workflow Integration · D5 Agent Collaboration · D6 Responsible Use & Privacy.
"Key dimensions" are the dimensions that matter most for the role. A gap of one level is acceptable if it can be closed within 90 days.

---

### F-PS · Pipeline Strategist (x4)
- **Team / reports to:** Mid-Market or Upmarket Pod → Pod Lead
- **Purpose:** Owns pipeline creation for the pod by directing agent-run outbound instead of sending emails one by one.
- **Responsibilities:** Define ICP and target account lists · Write messaging and approved-claims guidance for `agent.ai_sdr` · Review agent output samples weekly and fix failure patterns · Take warm handoffs and qualify meetings · Report pipeline quality to Pod Lead
- **Required skills:** Prospecting, Messaging/copywriting, ICP analysis, Objection handling, Salesforce
- **AI literacy:** Minimum **Practitioner**. Key dimensions: **D2, D3, D5** (reviewing agent claims for accuracy is a core duty)
- **Example transition paths:** R-SDR Sales Development Rep · R-MKT Marketing Specialist

### F-GTME · GTM Engineer (x3)
- **Team / reports to:** Agent Ops & Intelligence → Agent Operations Lead
- **Purpose:** Builds and maintains the automations and agent workflows that GTM depends on.
- **Responsibilities:** Build and maintain workflows across Salesforce, Clay, HubSpot and Corvana Copilot · Maintain enrichment and data quality · Implement guardrails and logging for agents · Support pods with new automation requests
- **Required skills:** Workflow automation, CRM admin, APIs/no-code tools, Data quality, Clay
- **AI literacy:** Minimum **Builder**. Key dimensions: **D4, D5, D6**
- **Example transition paths:** R-RO Revenue Operations Analyst · R-SDR Sales Development Rep (with automation experience) · R-SE Solutions Engineer

### F-AOL · Agent Operations Lead (x1)
- **Team / reports to:** Agent Ops & Intelligence → VP Sales (dotted line → VP Customer Success)
- **Purpose:** Accountable for performance, guardrails and human-in-the-loop design across all GTM agents.
- **Responsibilities:** Set agent performance and quality metrics · Own the agent risk register and escalation paths · Manage GTM Engineers and Revenue Intelligence Analysts · Decide what work moves to agents and what stays human
- **Required skills:** Team leadership, Process design, AI evaluation, Risk/compliance awareness, Coaching
- **AI literacy:** Minimum **Leader**. Key dimensions: **D3, D5, D6**
- **Example transition paths:** R-SDRM SDR Manager · R-RO Revenue Operations Analyst (senior)

### F-RIA · Revenue Intelligence Analyst (x2)
- **Team / reports to:** Agent Ops & Intelligence → Agent Operations Lead
- **Purpose:** Owns forecasting and the analytics that show whether agent-assisted GTM is working.
- **Responsibilities:** Maintain forecast model (target accuracy: 71% → 85%) · Build pipeline and agent performance dashboards · Analyze conversion by pod and channel · Brief leadership monthly
- **Required skills:** SQL/analytics, Forecasting, Data storytelling, Data quality
- **AI literacy:** Minimum **Practitioner**. Key dimensions: **D3, D4**
- **Example transition paths:** R-RO Revenue Operations Analyst · R-AE Account Executive (analytical) · R-MKT Marketing Specialist (campaign analytics)

### F-AE · Account Executive (x8)
- **Team / reports to:** Mid-Market or Upmarket Pod → Pod Lead
- **Purpose:** Closes mid-market deals with agent-prepared research, notes and proposals.
- **Responsibilities:** Run discovery and demos with SEs · Edit and own agent-drafted proposals · Negotiate and close · Review agent-logged CRM data for accuracy
- **Required skills:** Discovery, Negotiation, Proposal writing, Forecasting, Salesforce
- **AI literacy:** Minimum **Practitioner**. Key dimensions: **D2, D3**
- **Example transition paths:** R-AE Account Executive (continuing) · R-SDR Sales Development Rep (top performers, with ramp)

### F-EAE · Enterprise Account Executive (x6)
- **Team / reports to:** Upmarket Pod → Pod Lead
- **Purpose:** Runs complex deals above $80K ACV with accounts of 200+ technicians.
- **Responsibilities:** Multi-stakeholder deal strategy (MEDDICC) · Executive conversations · Coordinate SEs, Deal Desk and Customer Outcomes on complex deals · Validate agent-generated account research before use
- **Required skills:** Complex deal management, Executive presence, Negotiation, Discovery
- **AI literacy:** Minimum **Practitioner**. Key dimensions: **D3, D6** (handling customer data and claims in high-stakes deals)
- **Example transition paths:** R-AE Account Executive (IC3) · R-SDR Sales Development Rep (top performers; longer ramp + MEDDICC training)

### F-SE · Solutions Engineer (x4)
- **Team / reports to:** Mid-Market or Upmarket Pod → Pod Lead (SE Lead sits in Upmarket Pod)
- **Purpose:** Technical discovery and solution design for prospects.
- **Responsibilities:** Demos and technical discovery · Solution design for upmarket accounts · Review agent-generated demo scripts
- **Required skills:** Product demos, Technical discovery, Solution design, APIs/no-code tools
- **AI literacy:** Minimum **Practitioner**. Key dimensions: **D2, D3**
- **Example transition paths:** R-SE Solutions Engineer (continuing) · R-ONB Onboarding Specialist (technical)

### F-COM · Customer Outcomes Manager (x7)
- **Team / reports to:** Retention Pod → VP Customer Success
- **Purpose:** Strategic partner to ~40 larger accounts. Acts on agent-generated health and expansion signals.
- **Responsibilities:** Act on churn alerts from `agent.account_health` · Run executive business reviews · Build expansion hypotheses with AEs · Own renewals · Flag wrong or missing agent signals
- **Required skills:** Account management, Business reviews, Data interpretation, Change management, Renewals
- **AI literacy:** Minimum **Practitioner**. Key dimensions: **D1, D3** (knowing when a health signal is wrong)
- **Example transition paths:** R-CSM Customer Success Manager · R-ONB Onboarding Specialist · R-AE Account Executive (relationship-focused)

### F-ONB · Onboarding Specialist (x2)
- **Team / reports to:** Retention Pod → VP Customer Success
- **Purpose:** Gets new customers live, using agent-generated configuration plans. Target time-to-value: 45 → 30 days.
- **Responsibilities:** Lead implementations · Review agent-generated configuration plans · Train customer admins
- **Required skills:** Implementation, Project management, Product configuration, Training design
- **AI literacy:** Minimum **Practitioner**. Key dimensions: **D3, D4**
- **Example transition paths:** R-ONB Onboarding Specialist (continuing)

### F-AIE · AI Enablement Partner (x1)
- **Team / reports to:** Retention Pod → VP Customer Success (serves all GTM pods)
- **Purpose:** Helps GTM employees build the AI skills that new roles require, and runs the AI literacy program.
- **Responsibilities:** Design learning paths using the learning catalog (file 13) · Run prompting labs, verification drills and agent design studios · Coach managers on career conversations during the transition · Run work-sample assessments with the People Team
- **Required skills:** Training design, Coaching, AI tool fluency, Change management
- **AI literacy:** Minimum **Builder**. Key dimensions: **D1, D5, D6** (has to teach the limits and the rules, not only the tools)
- **Example transition paths:** R-ONB Onboarding Specialist · R-CSM Customer Success Manager · R-SDRM SDR Manager · R-MKT Marketing Specialist

### F-CS · Content Strategist (AI-assisted) (x2)
- **Team / reports to:** Agent Ops & Intelligence → Agent Operations Lead (dotted line → Pipeline Strategists)
- **Purpose:** Owns brand voice and accuracy for content that agents draft.
- **Responsibilities:** Maintain voice guide and **approved external claims list** · Edit and fact-check agent-drafted content · Content strategy for upmarket segment
- **Required skills:** Editing, Brand voice, Content strategy, Messaging/copywriting
- **AI literacy:** Minimum **Practitioner**. Key dimensions: **D2, D3, D6**
- **Example transition paths:** R-MKT Marketing Specialist · R-SDR Sales Development Rep (strong writers)

### F-PL · Pod Lead (Sales Manager) (x2)
- **Team / reports to:** Mid-Market or Upmarket Pod → VP Sales
- **Purpose:** Leads a segment pod of people and the agents they supervise.
- **Responsibilities:** Pod targets and forecast · Coaching and career conversations · Decide with Agent Ops which pod tasks run through agents
- **Required skills:** Team leadership, Coaching, Forecasting, Process design
- **AI literacy:** Minimum **Builder**. Key dimensions: **D4, D5**
- **Example transition paths:** R-SDRM SDR Manager · R-AE Account Executive (IC3, leadership track)

---

## 4. Demo Application — How the Mobility Agent Should Use This Document

**Runtime inputs**
| Input | Source | Use |
|---|---|---|
| This document | Uploaded at runtime | Target roles, reporting lines, required skills, AI literacy expectations |
| Current organization | `Corvana_Current_GTM_Organization_updated.md` | Current teams, reporting lines, headcount |
| Employee profiles | `07_employees_gtm_updated.csv` | Current role, skills, performance, potential, aspiration, openness to change |
| Current roles | `04_roles_current_updated.json` | Starting point for each transition (match on `current_role_id`) |
| Mobility criteria | `06_gtm_reorg_plan.md` | Fit weighting: skill adjacency 40%, AI literacy 25%, performance & potential 20%, aspiration 15% |
| AI literacy evidence | `14_ai_literacy_work_samples.md` (where available) | Observed, per-dimension evidence with a strength rating |
| Learning options | `13_learning_catalog.json` | Building blocks for 30/60/90-day plans |

**Instructions for the agent**
1. For each employee, compare their current profile with **every** role in Section 3. Do not limit the comparison to the "example transition paths" — those are illustrations, not restrictions.
2. Recommend the top 2–3 roles with a fit score and a plain-language explanation for each. Show which skills match and which are missing.
3. **Use AI literacy evidence as it is.** Where evidence for a dimension is weak or missing, say so ("D5: no evidence"). Do not fill gaps with guesses or self-ratings, and do not treat low AI *use* as low *skill*. Recommend an assessment task to close the evidence gap.
4. Respect stated preferences. If `open_to_role_change = No`, start with development in the current or closest adjacent role.
5. Build a 30/60/90-day plan from the learning catalog for each recommended role.
6. Include talking points for the manager and set `human_review_required: true` on every output.
7. Never use protected attributes (age, gender, ethnicity, etc.) or the `flight_risk` field to rank people for roles.

**Demo note:** No future roles have been pre-selected for any employee, including E1001 Maya Patel and E1002 Diego Ramirez. Their recommendations should come from the agent's own reasoning over the inputs above. This document contains no employee assessment results.
