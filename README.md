# People Intelligence Foundation

An AI-assisted prototype for exploring how organizations can support employees through change. It brings shared business and people context together with reusable evaluation and planning workflows.

**[Open the live prototype](https://people-context-compass.lovable.app)** · [View the presentation](People_Intelligence_Demo_Updated.pptx)

All company, employee, role and work sample data in this demo is fictional. Outputs are suggestions for human review, not employment decisions.

## The problem

During organizational change, business goals, role requirements and employee information are often scattered across systems. People teams and managers need a way to connect that context when considering development and internal mobility.

## How the prototype works

1. **Foundation:** Explore company goals, the organization, current roles and employee profiles.
2. **Agent Studio:** Describe a business need, review an AI-generated design and approve a workflow configuration.
3. **AI Literacy Evaluation:** Provide an employee's work sample and receive evidence-based developmental feedback.
4. **Mobility Workflow:** Upload a future organization plan. The workflow combines it with the employee's Foundation profile and saved AI literacy evaluation, when available, to propose a development plan.

The prototype demonstrates the reuse of a saved evaluation. Approval connects the design to an existing mobility workflow; it does not generate arbitrary new executable agents.

## Try the demo

The presentation contains three copyable prompts. To follow the example for **Fatima Al-Sayed (E1018)**:

1. Open the live app and explore Foundation.
2. In Agent Studio, request a mobility planning workflow, review the design and select **Approve & Create**.
3. Open AI Literacy Evaluation Skill, upload [Fatima's work sample](E1018_work_sample.md), and request an evaluation. Save the result.
4. Open Mobility Planning Workflow, upload the [future organization plan](Corvana_Future_GTM_Organization_updated.md), and request a mobility plan for Fatima. Review the sources in the result.

Download the `.md` files from GitHub before uploading them to the app. The work samples include a reviewer reference with expected issues; remove that section from a copy if you want to test whether the evaluation can independently identify those issues.

## Current limitations

- This is a prototype built with Lovable and fictional data, not a production HR system.
- The mobility workflow reuses saved AI literacy evaluations rather than necessarily invoking the skill during each run.
- Uploaded prompts, files and generated plans are temporary and reset on refresh; saved evaluations persist.
- The AI workflows accept `.md` and `.txt` uploads. AI runs have a shared 30-second interval.
- App and AI feature availability depends on the hosting service and available usage credits.

## Built with Lovable

I defined the product problem, designed the employee mobility scenario and iterated on the workflows using Lovable. The prototype combines AI-generated designs with shared organizational context and example employee evidence.
