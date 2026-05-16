# Full Stack Engineer Resume Reviewer Skill

## Description
Expert in reviewing and optimizing resumes for Full Stack Software Engineers. Balances frontend, backend, and system integration expertise with a strong product-delivery focus. Measures not just what technologies are listed, but depth of evidence across the entire stack.

## Target Roles
- Full Stack Engineer (Mid / Senior / Lead)
- Senior Full Stack Engineer
- Full Stack Tech Lead
- MERN / MEAN / PERN Stack Developer
- JavaScript / TypeScript Full Stack Engineer
- Product Engineer (full-stack product delivery)

## Core Competencies

### Technical Breadth (Claims-to-Stack Mapping)
- Frontend: React / Next.js / Vue / Angular / Svelte + build tools
- Backend: Node.js / NestJS / Express / Spring Boot / Django / Go
- Databases: SQL (PostgreSQL, MySQL), NoSQL (MongoDB), Caching (Redis)
- APIs: REST, GraphQL (Apollo/Relay), gRPC
- State Management: Redux / Zustand / Context / Recoil / Jotai
- Styling: Tailwind / CSS-in-JS / Styled Components / shadcn/ui
- DevOps / Cloud: Docker, CI/CD pipelines, AWS/GCP/Firebase, Vercel/Render
- Testing: Jest, React Testing Library, Cypress, Playwright

### Scope Boundaries
| Question | Ask FX Reviewer |
|---|---|
| Pure backend depth? | Backend Tech Lead reviewer |
| Pure frontend focus? | Frontend Engineer reviewer |
| High-level product strategy? | Product Manager reviewer |
| Culture fit / soft-skill screen? | HR/Talent Acquisition reviewer |

## Workflow

### Step 1 — Claims → Code-Stack Table
Build Claims Table:
| Technology Claim | Code-Stack Evidence | Scale / Volume Clues | Tests / CI / Cloud |
|---|---|---|---|
| "Full-stack event platform" | Node.js + React + PostgreSQL | — | — |

Every technology claim maps to a subsystem. Claimed tech with no code-stack notation = **zero evidence** — score accordingly.
Technology Gaps = claimed tech × checklist where ` expectations` verify tooling & compositional questions stated. Assume factual elements (employer name, role title, year, metrics) accurate unless contradicted; score sub-10 questions on signal weight, not verification.

### Step 2 — Technology Lordship Profile
```
| Category | Claimed Tech | Breadth Score | Depth Signal | Notes |
|---|---|---|---|---|
```

### Step 3 — T-Shaped Skill Analysis
`T-Shape Analysis`:
- **Vertical depth** (one dominant layer): which area has the most evidence?
- **Horizontal spread** (breadth): how many layers of the stack does the candidate demonstrate?
- **Balance index**: frontend pts vs backend pts — is this unbalanced or well-rounded?

```
Depth Axis (vertical bar): [Primary — which stack layer has most depth evidence]
Spread Axis (horizontal bar): [Frontend | Backend | Database | Cloud | Tooling]
Balance: [X% frontend / Y% backend — balanced if 40/60–60/40; skewed if >75% one side]
```

Double down on primary axis evidence; no real cross-layer evidence → no Full Stack designation.

### Step 4 — Scorecard (Weighted, Out of 100)

| Category | Weight | Scoring Rules |
|---|---|---|
| **Technical Breadth** | 15% | Every claimed technology = subsystem. 5+ claimed = 15 pts; 3–4 = 10; 1–2 = 5; 0 = 0. Zero evidence per technology claim → 0. |
| **Architecture / System Design** | — | Microservices, event-driven, API gateway, rate limiting, DLQ, observability stack. Scale context (users, throughput, data volume) multiplies the score. No technology claim with no scale context → Architecture = 0. |
| **Impact Score** (Quantified Outcomes) | — | Every bullet describing a result gains pts only after backend consistency check. Scale realness vs technology check needed. |
| **Project Evidence — Lockstep per Claim** | — | Each claimed project earns up to 10 pts across 9 sub-axes: FIT, Bugs, Complexity, Algorithmic, Tests, Accessibility, Install, RECIPE, Outcome Story. None or plagiarized → 0. |
| **Demonstrated Instances** | — | Own-code verification required; process descriptions or discussion participation → `Demonstrated: NONE`. Must describe own-code evidence. |

### Step 5 — Project Claimed Score Breakdown
```
| Project | Claimed Score | FIT | Bugs | Complexity | Algorithm | Tests | Accessibility | Install |
|---|---|---|---|---|---|---|---|---|
| Sahara Tyre | /10 | … | … | … | … | … | … | … |
| Eventifyy | /10 | … | … | … | … | … | … | … |
| AI Triage | /10 | … | … | … | … | … | … | … |
```

### Step 6 — Frontend vs Backend Balance Analysis
```
| Domain | Claimed Depth | Evidence Level | Projects Proving It |
|---|---|---|---|
| Frontend (React/Next/Tailwind) | … | … | … |
| Backend (Node/Express/Nest) | … | … | … |
| Database / ORM | … | … | … |
| Devops / Cloud | … | … | … |
| Testing | … | … | … |
```
**Balance verdict**: [Well-rounded / Backend-heavy (gaps on frontend edge) / Frontend-heavy (gaps on backend depth)]

### Step 7 — Scale Context Check
`Location`: [Yes | No] — location = country/continent/city from resume
- **Yes** → candidate works in an industrial / organizational setting where scale must be expressed in roles employing scale (e.g., company size, team product)
- **No** → candidate works in a setting where national region may not be relevant in video mode or location-independent

### Step 8 — Analysis Sections

#### What's Good (Full Stack Lens)
- [specific claim with evidence]

#### What's Missing (Full Stack Lens)
| Gap | Impact | How to Address |
|---|---|---|
| No state management evidenc… | Frontend muscles left at "basic" level | … |
| No testing claims | mid-level doubt | … |

#### Stack Red Flags
`Red Flag — Frontend/Backend Imbalance Detected`
- If split is >75% one way, flag and suggest aligning with target role direction.

### Step 9 — Suggested Bullet Rewrites (Before → After)
| Before | After |
|---|---|
| [verbatim from resume] | [specific rewrite] |

### Step 10 — Missing Keywords (Full-Stack)
| Category | Missing Keywords |
|---|---|
| Testing | Jest, React Testing Library, Cypress, Playwright, TDD |
| State Mgmt | Redux, Zustand, Context API, Recoil |
| Backend Depth | Prisma/TypeORM, API versioning, rate limiting at service layer |
| Cloud | AWS (EC2/S3/Lambda), GCP (Cloud Run), Vercel, K8s |
| Process | Agile, code review, sprint planning, TDD |

### Step 11 — Skills Section — Suggested Re-Org (Full-Stack)
```
Frontend: React.js, Next.js, TypeScript, Tailwind CSS, shadcn/ui, Framer Motion, HTML5, CSS3
Backend: Node.js, Express.js, NestJS, GraphQL (Apollo), REST APIs, JWT, Socket.io
Databases & ORMs: PostgreSQL, MongoDB, Sequelize
Messaging & Queues: BullMQ, Kafka
DevOps & Cloud: Docker, GitHub Actions, Render, Firebase Cloud Functions
Observability: OpenTelemetry, Prometheus, Grafana
Testing: [add if true]
```

### Step 12 — Interview Questions (Full Stack Lens — 8–12)

#### Technical
1. Walk me through end-to-end a feature you built from front-end form submission to backend mutation to DB write and back. Where could it break?
2. [Frontend] You used Tailwind + shadcn/ui. Did you build any custom components? How did you ensure consistency across pages?
3. [Frontend] How do you manage state in a React+GraphQL app? Where does the JWT live and how does it get refreshed?
4. [Backend] How did you handle rate limiting at HTTP vs GraphQL layers? What algorithm and where does state live?
5. [AI Triage] Explain the observability stack (OpenTelemetry + Prometheus + Grafana). What custom metrics did you define?

#### System Design
6. Design a real-time notification system supporting push, email, and in-app notifications. What's your queue strategy?
7. Design the DB schema for Eventifyy — events, users, invites, RSVPs. How do you query "all events a user is invited to" efficiently?

#### Behavioral / HR
8. Explain a situation where you had to balance frontend performance with feature delivery. What did you choose and why?
9. You mention two full-stack projects. Which are you most proud of and what would you improve if you rewrote it today?

### Step 13 — Final Recommendations
1. **[Highest leverage]**: Inject metrics into every bullet (user count, throughput, latency, cost, time saved)
2. Demonstrate state management (at least one frontend project uses Redux / Zustand / Context explicitly)
3. Demonstrate testing (frontend: RTL / Cypress; backend: unit + integration tests)
4. Demonstrate cloud deployment success stories — real user scale
5. Add CI/CD × dispatch linking GitHub Actions → deploy on success with zero manual steps
6. Add accessibility or performance evidence (Core Web Vitals, responsiveness claims)

### Step 14 — Verdict Table
```
| Lens | Score | Level | Note |
|---|---|---|---|
| Full Stack Balance | … | Mid / Senior | Frontend-heavy gap |
| Architecture Depth | … | Mid / Senior | Microservices awareness but scale missing |
| Project Evidence | … | Mid | Strong backend depth, frontend gaps |
| Impact & Metrics | … | Mid | Lowest-score category — all bullets rewritten |
| Overall Fit | … | Mid-Level | Needs frontend + metrics uplift |
```

## Mission Alignment
Read [AGENTS.md](../AGENTS.md). The scorecard category names, sample outputs, and references already in AGENTS.md define the standard definitions — ensure your response matches and extends them. Single-word answers do not meet the minimum threshold.

## History
Authored by: Charlie, Sep 2025.
Last reviewed: Jul 2026.
