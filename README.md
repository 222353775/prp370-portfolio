# PRP370 Digital Portfolio

**Student:** Minathi Fortune Shezi
**Student Number:** 222353775
**Module:** Project Presentation 3 (PRP370S)
**Assessment:** Assessment 2 - GitHub Portfolio (Industry Placement)

## Context & Declaration
This portfolio is based on my Work Integrated Learning (WIL) Industry Placement at **Mavis Strategic Partners**. During this placement, I am working as the solo Full Stack Developer on the **School Performance Hub** MVP. 

For this assessment, I have focused on the **Week 3 completion and Week 4 planning** of the Curriculum Tracker. The artefacts below demonstrate how I am planning, tracking, and reflecting on the project. 
*Note: Due to a POPIA governance decision, the project is currently hosted locally (no remote GitHub or Vercel), so UI screenshots for Week 4 are pending. The evidence below reflects the actual database structure and codebase.*

---

## 1. Agile Team Charter

### Evidence
**Team Purpose:** To build a pilot-ready school management web app that proves a connected accountability loop for school leadership and teachers.

**Team Structure:**
*   **Me:** Solo Full Stack Developer (TypeScript, Next.js, Prisma)
*   **Supervisor/Reviewer:** Sipo Kupiso (MSP Senior)

**Core Values & Boundaries:**
*   **Local-Only Rule (POPIA):** Development is fully local (Docker Postgres) until the MSP information officer signs off on the POPIA impact assessment. No real learner data leaves the machine.
*   **Strict Multi-Tenancy:** Every table has a `schoolId`, and all data access goes through a tenant-scoped data layer. A user from School A can never read School B's data.
*   **Audit Trail:** Every write action must be logged to the `AuditLog` table.

**Definition of Done (DoD):**
A task is done when the database migration runs cleanly, permissions are unit-tested (Vitest), the UI works on a phone-sized screen, and it passes the end-to-end Playwright tests. 

### Reflection
During my placement, the Agile Team Charter had to adapt to a major governance blocker: the POPIA compliance sign-off is delayed. This forced a "local-only" working agreement, meaning I cannot use remote CI or share preview links with MSP. This artefact demonstrates that Agile is about adapting to real-world constraints. If I did this again, I would push for the POPIA assessment to be started on Day 1, as it fundamentally changes the deployment workflow.

---

## 2. User Stories and Tasks

### Evidence
**US1 — View Weekly Timetable (Completed Week 3)**
*As a teacher, I want to see my timetable for the week so I can plan my schedule.*
*   Build `/teacher/timetable` page.
*   Create `timetable-week.tsx` component.
*   Fetch data via `src/server/db/timetableSlot.ts`.

**US2 — Mark Lesson Done (Planned Week 4)**
*As a teacher, I want to mark a lesson done in under a minute, or give a reason and recovery date, so that pacing is accurate.*
*   Create `LessonRecord` database model.
*   Add permission rules (`lessonRecord`) in `permissions.ts` (Unit tested).
*   Build the UI marking flow.

**US3 — Track Pacing (Planned Week 4)**
*As a teacher, I want to see topics done vs. expected so I know if I am behind.*
*   Create `CurriculumTopic` model.
*   Build the progress bar UI.

![Code Snippet](code.png)

### Reflection
I used user stories to break down the curriculum tracker. This artefact shows how I prioritize tasks. While the permission rules and tests for US2 and US3 were written in Week 2, the actual database models and UI have not been built yet. This highlights a key lesson: writing backend logic is useless if the frontend blocks aren't finished. It connects to my product backlog, where I have to move these items forward.

---

## 3. Product Backlog

### Evidence
| Priority | Backlog Item | Status | Notes |
| :--- | :--- | :--- | :--- |
| P1 | Authentication & Tenant Isolation | Done | 437 of 437 tests pass |
| P1 | Timetable & Terms Migration | Done | Includes UI component |
| P1 | Seed Script (Umthombo High) | Done | 20 staff, 150 learners |
| P1 | **CurriculumTopic & LessonRecord Migrations** | **To Do** | Blocked until Week 4 branch starts |
| P1 | Today's Lessons Screen (US2) | To Do | |
| P1 | Teacher Pacing View (US3) | To Do | |
| P2 | Next.js 16.4.0 Upgrade | To Do | Security advisory build warning |

![Database Schema](database.png)

### Reflection
This product backlog represents the reality of the project. I included it to show that I understand how to manage prerequisites. Before I can build the Week 4 UI, I need to do the database migrations for `CurriculumTopic` and `LessonRecord`. I also logged a security advisory (Next.js upgrade) as a P2 item. This backlog connects to the sprint backlog by showing exactly what was pulled into the completed Week 3 sprint.

---

## 4. Sprint Backlog (Completed Week 3)

### Evidence
**Sprint Goal:** Deliver a fully functional, multi-tenant timetable system with a seeded fictional school.

| Task | Status |
| :--- | :--- |
| Database migration: `timetable_and_learners` added | Done |
| Tenant-scoped data layer: filtered by `schoolId` with tests | Done |
| Idempotent seed script (`pnpm db:seed`) | Done |
| UI component: mobile-first weekly timetable | Done |
| Playwright E2E test: role-gating per role | Done |

### Reflection
This sprint backlog illustrates the Week 3 completion. I selected this artefact because it proves I delivered a working feature despite governance challenges. The biggest challenge was the schema freeze: I needed an approved one-off migration to add the `AuditLog` table. The moment I got approval, I finished the sprint. This artefact connects to my retrospective because it proves the foundation is solid for Week 4.

---

## 5. Agile Logbook

### Evidence
*Note: Below are actual blockers logged from governance decisions (G-01 to G-28).*

**Daily Stand-up Entries / Blockers:**
*   **Governance (G-10):** Development is fully local (no GitHub remote) until POPIA impact assessment is signed off. CI has never run remotely. *Action:* Focus on local Vitest tests.
*   **Governance (G-11):** Better Auth conflict: Making school mandatory on every session broke parent logins (parents with kids at two schools). *Action:* Enforced tenancy in the data layer instead of the session.
*   **Governance (G-14):** Schema freeze: Needed a one-off migration to add `AuditLog` table so every write is audited from day one. 
*   **Scope Drift:** System-admin tooling (a stage 5 item) was built while Week 4 hadn't started. *Action:* Log it in "after MVP" and refocus.

**Retrospective:**
*   **Went well:** Permissions and tenant isolation were built and tested first (437 tests passing). 
*   **Didn't go well:** Scope drifted into stage 5 system-admin tooling. No shareable preview link for MSP due to local-only hosting.
*   **Improvements:** Start Week 4 immediately with the `CurriculumTopic` migration. Agree on a private remote repo or preview host with MSP before the 13 Nov prototype demo.

### Reflection
The Agile Logbook is the most honest reflection of my WIL experience. My blockers are not just coding bugs—they are POPIA compliance, authentication conflicts, and scope creep. Tracking these in the logbook taught me that "done" requires balancing security and governance with features. Deferring the Next.js security upgrade creates technical debt. This logbook ties all my previous artefacts together, proving that I can manage a project solo and adapt to real-world blockers.
