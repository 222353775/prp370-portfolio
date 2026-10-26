# prp370-portfolio
# PRP370 Digital Portfolio

**Student:** Minathi Fortune Shezi
**Student Number:** 222353775
**Module:** Project Presentation 3 (PRP370S)
**Assessment:** Assessment 2 - GitHub Portfolio (Industry Placement)

## Context & Declaration
This portfolio is based on my Work Integrated Learning (WIL) Industry Placement at **Mavis Strategic Partners**. During this placement, I worked as a Full Stack Developer on the **ProKonecta** project. 

For this assessment, I have focused on the **Customer Service Request-to-Quote workflow** (covering the customer request, provider matching, quote submission, and customer acceptance). Because I am no longer at the company, the Agile artefacts below have been **reconstructed** based on my actual development work to demonstrate how the project was (and could have been) planned, tracked, and reflected on. 

*Note: Company, client, and personal data have been anonymised. This is an individual assessment, and the reflections focus on my personal contribution as a Full Stack Developer.*

---

## 1. Agile Team Charter

### Evidence
**Team Purpose:** To design, build, and hand over a functional Request-to-Quote workflow for the ProKonecta marketplace platform.

**My Role:** Full Stack Developer (React 19, Next.js 16, TypeScript).

**Team Structure:**
*   **Me:** Full Stack Developer
*   **Supervisor/Lead:** Sipo Kupiso
*   **Receiving Team:** Backend Hardening & QA Team (responsible for independent testing and edge-case handling)

**Core Values:**
*   Working software over perfect code.
*   Clear documentation for seamless handovers.
*   Honest communication about blockers.

**Working Agreements:**
*   Commit to Git/GitHub frequently with clear messages.
*   Validate all API inputs using TypeScript and ensure JWT authentication is secure.
*   Document assumptions and known gaps before handing over to the testing team.

**Definition of Done (DoD):**
A feature is "done" when the UI connects to the API, handles loading/error states, and is documented for the receiving team. *Note: Backend hardening and full E2E testing are explicitly out of my scope and belong to the receiving team.*

### Reflection
During my WIL placement at Mavis Strategic Partners, I learned very quickly that a "Team Charter" is not just a corporate formality; it is crucial for managing expectations. When I drafted the Definition of Done for my full stack work, I had to consciously separate my responsibilities (building the frontend, connecting APIs, and basic validation) from the receiving team's responsibilities (backend hardening and rigorous testing). This artefact demonstrates that I understand Agile is about delivering value incrementally. If I did this again, I would push for a shared definition of done with the receiving team from day one, ensuring that our API contracts and acceptance criteria were agreed upon before I wrote a single line of code.

---

## 2. User Stories and Tasks

### Evidence
**US1 — Submit a service request**
*As a customer, I want to describe the service I need so that relevant providers can respond.*
*   Build the request form for category, description, timing, budget, and location.
*   Validate and submit the request.
*   Show a confirmation and the request’s status.

**US2 — Find and unlock matching leads**
*As a provider, I want to see relevant service requests and unlock their details so that I can decide which opportunities to pursue.*
*   Match requests to providers by category and service area.
*   Show a lead preview and the unlock cost.
*   Check credit balance and handle insufficient-credit responses.
*   Reveal request details after a successful unlock.

**US3 — Send a quote**
*As a provider, I want to send a quote for an unlocked request so that the customer can consider my offer.*
*   Create a quote with price, terms, and validity.
*   Validate required fields and save the quote.
*   Notify the customer that a quote is available.

**US4 — Review and respond to quotes**
*As a customer, I want to compare provider quotes and accept one so that I can move forward with the service.*
*   Display incoming quotes and relevant provider details.
*   Allow the customer to accept, reject, or negotiate a quote.
*   Update the request and job status when a quote is accepted.

### Reflection
I used user stories to break down the complex Request-to-Quote workflow into manageable, user-centric tasks. This artefact demonstrates my ability to translate technical requirements (like JWT authentication and MySQL data mapping) into actual user value. The most challenging story to implement was US2 (Find and unlock matching leads) because it required complex validation and edge-case handling for the credit balance. I included these stories to show how I approach full-stack development: starting with the end-user's goal and working backwards to the database schema. This connects directly to my product backlog, where these stories became actionable tasks.

---

## 3. Product Backlog

### Evidence
*Note: Priorities were reconstructed based on the critical path of the WIL project.*

| Priority | Backlog Item | Type | Status |
| :--- | :--- | :--- | :--- |
| P1 | Customer service-request form, validation, and submission | Feature | Done |
| P1 | Provider matching and lead preview | Feature | Done |
| P1 | Lead unlock flow with credit and balance handling | Feature | Done |
| P1 | Provider quote submission | Feature | Done |
| P1 | Customer quote review and response | Feature | Done |
| P1 | Backend hardening: authorization, validation, error handling, and transaction safety | Tech Debt | Handed Over |
| P1 | End-to-end and integration testing across the request-to-quote journey | Testing | Handed Over |
| P2 | Feature documentation, acceptance criteria, and handover notes | Documentation | Done |

### Reflection
This product backlog represents the full scope of the Request-to-Quote feature I built during my placement at Mavis Strategic Partners. I included it in my portfolio because it highlights a major shift in my mindset as a developer. Previously, I viewed "coding the feature" as the only real task. However, constructing this backlog showed me that technical debt and testing are not afterthoughts; they are critical P1 items. I had to prioritize the core workflow (submission, matching, quoting) so I had something to hand over, while leaving the backend hardening to the receiving team. This backlog connects to the sprint backlog by showing exactly what I pulled into my final sprint before the handover.

---

## 4. Sprint Backlog

### Evidence
**Sprint Goal:** Deliver a usable Request-to-Quote workflow and hand over a documented implementation for independent testing and backend hardening.

| Task | Assigned To | Status |
| :--- | :--- | :--- |
| Implement the feature UI and connect it to the relevant APIs (Next.js/React) | Me | Done |
| Handle loading, validation, and error states | Me | Done |
| Document the flow, assumptions, and known gaps for handover | Me | Done |
| Test the workflow across customer and provider roles | Receiving Team | Handed Over |
| Check authorization, input validation, and backend edge cases | Receiving Team | Handed Over |
| Harden backend behavior and report defects or follow-up work | Receiving Team | Handed Over |

### Reflection
This sprint backlog illustrates the transition of my work from active development to a handover phase. I selected this artefact because it clearly shows how a sprint goal must align with the team's boundaries. As a full stack developer, my sprint goal was to build and document a working feature, not necessarily to perfect it to production standards. The moment I handed the tasks over to the receiving team, I had to trust the process and let go. This artefact connects to my retrospective because it proves that while the coding phase was successful, the handover phase exposed a need for better upfront API contract agreements. 

---

## 5. Agile Logbook

### Evidence
*Note: The following stand-up entries and retrospective are representative of my actual experience during the handover phase.*

**Daily Stand-up Entries:**
*   **Day 1:** *Did:* Built the request flow and connected its main submission path. *To do:* Complete provider matching and review the request journey end to end. *Blocker:* Need confirmation of expected request fields and matching rules.
*   **Day 2:** *Did:* Implemented the provider lead view and quote-submission path. *To do:* Check customer quote review and prepare the handover notes. *Blocker:* Credit and API edge cases need agreement with the backend owners.
*   **Day 3:** *Did:* Fixed UI issues, documented the workflow, and prepared the handover. *To do:* Support the receiving team as they test and harden the feature. *Blocker:* Testing feedback and backend changes are now dependent on the receiving team.

**Retrospective:**
*   **Went well:** A working feature was available to hand over rather than only a design or specification. Separating implementation from follow-on testing made ownership of the next phase visible.
*   **Didn't go well:** The handover exposed gaps between the feature’s assumptions and the backend’s expected behavior. Acceptance criteria and edge cases needed clarification during testing.
*   **Improvements:** Agree on acceptance criteria, API contracts, and a shared definition of done before implementation begins. Include a handover checklist with setup steps, test scenarios, and named owners for follow-up work.

### Reflection
The Agile Logbook is the most honest reflection of my WIL experience at Mavis Strategic Partners. Tracking my daily stand-ups revealed a recurring pattern: my blockers were often not technical coding errors, but rather *communication gaps* regarding API expectations and edge cases. The retrospective was a turning point for me. It taught me that "done" should mean more than a completed interface; it requires agreed acceptance criteria and reliable backend behavior. Deferring backend hardening creates technical debt, and a receiving team needs enough context (API expectations, setup instructions) to test independently. This logbook ties all my previous artefacts together, proving that clear ownership and early communication are what separate a deliberate handover from unfinished work.
