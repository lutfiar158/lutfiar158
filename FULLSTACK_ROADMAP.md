# Full-Stack Roadmap — Lutfiar Rahman Maarif

This is a practical learning plan, not a claim that every listed technology or feature has already been completed. Progress should be reflected here only after each milestone is implemented and verified.

## Goal

Build one deployed, documented full-stack application that demonstrates the complete development lifecycle: requirements, data modeling, server-side code, validation, security, testing, deployment, and maintenance.

## Flagship Project: SkillSprint

**SkillSprint** is a personal learning tracker. A signed-in user can create learning goals, record study sessions, and review progress over time.

The project is deliberately small enough to finish, but rich enough to demonstrate full-stack fundamentals.

### MVP scope

- Create, view, edit, and delete learning goals.
- Organize goals by skill or topic and track status and target dates.
- Record a study session against a goal, including duration and optional notes.
- Show a dashboard with weekly study time, completed sessions, active goals, and recent activity.
- Filter goals and browse session history.
- Validate user input on the server and display useful loading, empty, success, and error states.
- Keep each user's records private and verify record ownership on the server.
- Provide a responsive, keyboard-accessible interface.

### Proposed stack

| Layer | Choice | Why |
|---|---|---|
| Application | SvelteKit + TypeScript | Build UI and server-side workflows in one codebase |
| Styling | Tailwind CSS | Continue from the current portfolio stack |
| Database | PostgreSQL | Learn relational data, constraints, joins, and indexes |
| Database access | Drizzle ORM + migrations | Keep schema and queries typed and migrations version-controlled |
| Validation | Zod or equivalent schema validation | Validate untrusted input at server boundaries |
| Authentication | A maintained SvelteKit-compatible library | Avoid inventing password/session security |
| Tests | Vitest + Playwright | Cover business logic and important user journeys |
| Delivery | GitHub Actions + a Node-capable host and managed PostgreSQL | Automate checks and publish a usable demo |

Keep the hosting and authentication choices flexible until their current free tiers, regional availability, and deployment requirements have been checked.

## Milestones

### Phase 1 — Requirements and foundations

- [ ] Write user stories and acceptance criteria.
- [ ] Sketch the dashboard, goals list, goal form, and session form.
- [ ] Create the repository and write a useful README before coding.
- [ ] Review TypeScript basics, HTTP methods/status codes, forms, async/await, and environment variables.
- [ ] Write an initial data model and explain the relationships.

**Done when:** another developer can understand the scope, run the scaffold, and identify what is in and out of the MVP.

### Phase 2 — Database and CRUD

- [ ] Scaffold the SvelteKit application.
- [ ] Configure local environment variables and an example environment file.
- [ ] Define tables and relationships for users, goals, skills/topics, and study sessions.
- [ ] Add version-controlled database migrations and seed data for local development.
- [ ] Implement server-side create, read, update, and delete workflows for goals and sessions.
- [ ] Add constraints and indexes where the use cases justify them.

**Done when:** a user can create and update goals and log sessions, and the records remain after restarting the application.

### Phase 3 — Authentication and authorization

- [ ] Add sign-in/sign-out using a maintained authentication library.
- [ ] Protect private routes and mutations on the server.
- [ ] Enforce ownership in every query or mutation involving a user's data.
- [ ] Validate request data on the server, not only in the browser.
- [ ] Handle expired sessions, unauthenticated requests, and unauthorized record access.
- [ ] Keep secrets in environment variables; never commit real credentials.

**Done when:** one user cannot read, edit, or delete another user's records by changing an ID or URL.

### Phase 4 — Useful product behavior

- [ ] Build the dashboard from real database queries.
- [ ] Add filters and session history.
- [ ] Handle empty, loading, validation, and server-error states.
- [ ] Review mobile layouts, form labels, keyboard navigation, and contrast.
- [ ] Add pagination if the data size warrants it.

**Done when:** the core workflow feels complete without fake metrics or hard-coded demo results.

### Phase 5 — Quality and delivery

- [ ] Unit-test validation and business logic with Vitest.
- [ ] Add Playwright tests for sign-in, goal CRUD, logging a session, and access control.
- [ ] Add GitHub Actions checks for install, type checking, tests, and build.
- [ ] Deploy the application and provision the production database.
- [ ] Verify production environment variables, migrations, logs, and error behavior.
- [ ] Test the deployed application using a fresh account.

**Done when:** the main workflows pass automated checks and work in the deployed version.

### Phase 6 — Portfolio case study

- [ ] Add a live demo link and screenshots/GIF to the README.
- [ ] Document the architecture and data model.
- [ ] Explain two or three meaningful technical decisions and their trade-offs.
- [ ] Document local setup, environment variables, migrations, tests, and deployment.
- [ ] List known limitations honestly and create follow-up issues.
- [ ] Update the main portfolio with the project's real features and links.

**Done when:** a reviewer can open the demo, understand the problem, inspect the code, run it locally, and see evidence of testing.

## Suggested 12-week cadence

| Weeks | Focus |
|---|---|
| 1–2 | Requirements, HTTP, TypeScript refresh, schema design, wireframes |
| 3–4 | SvelteKit server workflows, PostgreSQL, Drizzle, migrations, CRUD |
| 5–6 | Authentication, server-side validation, authorization, privacy boundaries |
| 7–8 | Dashboard queries, filters, UX states, accessibility |
| 9–10 | Unit and end-to-end tests, CI, security review |
| 11 | Production deployment, database migration, environment configuration |
| 12 | README, screenshots, case study, portfolio update, bug fixes |

Treat the weeks as a guide, not a deadline. Understanding and shipping a smaller complete app beats rushing through a checklist.

## Definition of done for every feature

- [ ] Acceptance criteria are written before implementation.
- [ ] Valid input succeeds; invalid input gives a clear error.
- [ ] Server-side authorization is checked where private data is involved.
- [ ] The UI handles empty and failure states.
- [ ] Relevant automated tests pass.
- [ ] The README or decision notes are updated when behavior or setup changes.
- [ ] The change is committed with a clear message.

## Weekly routine

Aim for five focused sessions per week, around 45 minutes each:

1. Spend 5 minutes choosing one outcome.
2. Work for 30–35 minutes with notifications and unrelated tabs closed.
3. Use the last 5–10 minutes to test, commit, and write the next step.
4. On a busy day, do a 10-minute minimum: fix one small issue, write a test, or document the next action.
5. At the end of the week, review what works in the app rather than how many hours were logged.

## Learning resources

- [SvelteKit documentation](https://svelte.dev/docs/kit)
- [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html)
- [Drizzle ORM — PostgreSQL](https://orm.drizzle.team/docs/get-started/postgresql-new)
- [Vitest guide](https://vitest.dev/guide/)
- [Playwright introduction](https://playwright.dev/docs/intro)
- [OWASP Session Management Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html)

## Progress log

Only record completed, verified outcomes here.

- 2026-10-17 — Roadmap created; flagship project scope and quality criteria defined.
