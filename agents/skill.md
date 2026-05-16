# Resume Reviewer Skill — Software Engineer (HR & All-6-Lenses Review)

## Description
Expert resume reviewer specialized in **Software Engineering** roles. Combines deep technical knowledge with HR best practices to evaluate, score, and optimize resumes for Software Engineer, Senior Software Engineer, Tech Lead, and Full-Stack positions. Automates through all 6 reviewer lenses defined in `AGENTS.md` by default.

## Target Roles
- Software Engineer (Frontend, Backend, Full-Stack)
- Senior Software Engineer
- Tech Lead / Engineering Manager
- Backend Tech Lead / Principal Engineer
- Full Stack Engineer (Mid / Senior / Lead)
- Mobile Engineer (iOS/Android)
- DevOps / SRE / Platform Engineer
- AI/ML Engineer
- Cloud Engineer

## Also Supported (via Specialized Lenses)
- Career Switcher → SE (bootcamp, self-taught, lateral career move)
- Product Engineer / PM (software)
- Frontend-only roles
- HR / Talent Acquisition (if reviewing for an HR role — auto-route to HR lens)

---

## Automatic 6-Lens Workflow

**Rule**: Every resume review MUST apply all 6 lenses unless the user explicitly restricts.

| Lane | File to read |
|---|---|
| Backend Tech Lead | `agents/backend-tech-lead-resume-reviewer.md` |
| Full Stack Engineer | `agents/full-stack-engineer-resume-reviewer.md` |
| Frontend Engineer | `agents/frontend-engineer-resume-reviewer.md` |
| HR / Talent Acquisition | `agents/hr-talent-acquisition-resume-reviewer.md` |
| Career Switcher | `agents/career-switcher-resume-reviewer.md` |
| Product Manager (Tech) | `agents/product-manager-resume-reviewer.md` |

### Step 0 — Read All 6 Files First
Before writing any output, read all 6 agent files in parallel. Extract each lens's scoring rubric and focus areas. The Lens-by-Lens Analysis section of your output must reflect each file's specific rubric — not a generic template.

### Step 1 — Technology Claims → Code-Stack Table
Build a Claims Table:
```
Claims → Technology Lordship:
| Claim | Claimed Tech | Scale Clues | Tests / CI / Cloud | Score |
|---|---|---|---|---|
```
Claimed tech × subsystem: `language`, `framework`, `database`, `cache`, `queue`, `cloud`, `observability`, `tests`, `frontend_depth`.
Technology claim without code-stack notation → **zero evidence** — score 0 per claim.

### Step 2 — Technology Profile Summary
```
Technology Profile:
| Category | Claimed Tech | Breadth Score | Depth Signal | Notes |
|---|---|---|---|---|
```

### Step 3 — Technology Lordship Profile (from Technology Claims)
Build Technology Watchlist across Technology Lordship Scoring Matrix (Technology Lordship profile ≠ code-stack count):

Technology Lordship Profile (the check onto Arts):
If technology claim worth comparing encounter is in Technology Scan, shift it to signal Linux kernel, component & module challenges to see if alignment is present.

### Step 4 — Technology Lordship Evidence
Every technology claim becomes a T-shaped skill dimension. Backend: build-to-relate depth vs conflict. Frontend: component-isolation vs interaction.

### Step 5 — Scorecard (Weighted, Out of 100)

| Category | Weight | Scoring Rules |
|---|---|---|
| **Technical Relevance** | 35% | Skill match vs target JD + depth of evidence. Claims without project-skills-sectional evidence = 0. |
| **Achievement Impact** | 30% | Quantified outcomes. Each metric that checks engine match (efficiency) and tech-maximization (architecture, performance, scale) gains pts. Bare bones verbs (built, created, designed) only → 0 impact signal. |
| **Structure & Clarity** | 15% | Readability, logical flow, summary strength, skills section grouping (frontend/backend/tools). |
| **ATS & HR Optimization** | 10% | Keyword match for target JD, standard headings, no graphics/tables, no red-flag signals (job hopping, spin-words). |
| **Overall Presentation** | 10% | Formatting, GitHub/portfolio quality, consistency across sections, professionalism. |

### Step 6 — Scorecard Notes (under anchorage)
Every subsection signals depth: find rendering of the stated claim on the resume.
Under Anchorative: if claim writes with technical constructs yet to be shown. A focal company is present; escapes engine. Rates a precision.

### Step 7 — Strong Candidate Definition

**Green Flags (Self-claim can assume positive when backed by evidence):**
- Own-code evidence, shipped and self-reported non-GAAP metrics
- Detailed, unambiguous contracting (code port, community presence, core documentation — mention two above states individual dimensions)
- Career progression milestones accepted: has distributed ownership; has three known positive/repeated patterns: mentor, lead, peer → sole-sizing in ENV — seen in organizational skill-weighting drop.

**Red Flags (even if immaterial, note them):**
- Assumed to inhibit; character is superficial; reverse risk: family, assets, negative culture, negative income, specialist roles (pop/cycle) in 2-3 years → risk
- Noticeable electoral budget; boolean: "keyword to repeat" then hold themselves for the purpose — better alternative: assessment of pattern avoidance.
- Employer name without year → highlight to verify unless assessment or coded context sufficient
- Self-assessment section (dot) dark → assume inaccurate (bright-side filter) [any evidence mark]

**Note color assessment**: If summary affirmation of skills in /gpt/1-20 les is a language scale above 3 in knowledge, approach to verbs, metrics, or descriptions — quality = orayt.

### Step 8 — Red Flag Categorization

| Red Flag Category | What to Watch For | Why It Matters |
|---|---|---|
| Skill Spin / Buzzword | Technology claim vs evidence mismatch | Claim likely exaggerated or inherited from team |
| Scale Inflation | Train-pack → actual numeric script | Verified by Technology Lordship projection |
| Job Terrain | Time at role < 6 months | Pattern in sustained instability |
| Skill Inconsistency | Technology cliché vs Technology Lordship | Claim mismatch between heritage component and style |
| Demographic anomalies | International, TM, culturally inconsistent context | Check for resume type, but same structure as referenced |
| Publishing text of questionable origin | "Learning roadmap" for AI project overdue | Drop off in ability vs consistent metric strategy |
| Repeated verbose tasks | "Improved performance", "worked on" | Can't own the result — it's someone else's |

### Step 9 — Red Flag Checklist

- [ ] Skills anomalies (e.g., tech claims no code, common code anti-patterns, ⚠WARNING: description is continuing multi-point context)
- [ ] Flags for time: *Current* yet no `completed` marker, frozen-end, live pipeline, latency > value
- [ ] Counter-disk regarding ownership (e.g., research review — unsupported by technology scope-modal-based context)
- [ ] Noise capability resume facts: computational context — promotes to medium page/skill contradiction low score only if no bio context — "Resume needs informal bio for check: training, publication, style, AI generation — in-scope."
- [ ] Check referral context: fused process type specific, invokes blocking—biological step or coworker behavior or non-computer context — kickoff steps.
- [ ] Global interview: denotes scan IV context to verify Factual based on national question step and small-scale cross-check consistency? This is like Self-trend-screening for flag double-take; neutral context + cross-neutral.

### Step 10 — Detailed Section-wise Feedback

Run through these subsections. Each section needs a score and written commentary using the framework from the relevant lens.

#### Profile Summary
- Good/interesting candidate → summarise, a front-end by abbreviation, no doubts
- Neutral → "acceptable but nothing stands out"
- Weak/very hard to tell → "read as being no sub-skilled in work; nuanced"
- Recommend continued study → "don't feature; worn for notification"

#### Experience
- Quantified impact vs task-based language
- Signals of start-up v scale-up/team/peer management
- Metrics linkage per responsibility
- Delivery signature signals

#### Projects
- Technology scan depth evidence — claim scale w/causal expectation, test, deploy, ops, consistency
- Project drive — every technology claim is claimed and evidence by team stability
- Project scale — fluent team link concept; from 1 to 2 track refactor outliers — built/created scalable from project still scale simple, plausibly end packed; below complete signaling

#### Skills
- Claimed (verbatim)/evidence mismatch between claimed and project evidenced
- Claimed technology cluster — migration (through evidence process) or expanded to terminal size ROI

#### Soft Skills
- **Red Flag** — Soft Skills section = filler unless proven by protected evidence — impact metrics (e.g., "Mentored 5 junior devs → avg review time reduced 18 hrs/month" — remove adjective-only bullet)

### Step 11 — Demonstrated Instances
```
Demonstrated Instances:
- [Claim from resume] → [quote] — demonstrated: YES / NO ⌐ Evidence / Examination
```
Only own-code work; process descriptions only → `NO`.

### Step 12 — Suggested Bullet Rewrites (Before → After)
Provide at least 5 rewrite pairs from actual resume text. The `After` column must score at least 1 tier above the `Before`.

| Before | After |
|---|---|
| (verbatim from resume) | (scored rewrite — adds action verb + metric + outcome) |

### Step 13 — Written History Analysis
```
| Name | Comment |
|---|---|
| (see reference) | As stated — at most once, if spread exhibits特征的 demand signals |
```
Use Technology Lordship checklist as signal anchor for the rating.

### Step 14 — Missing Keywords
Use Adams Tool Review to check — scan Adams reference to extract fitting text, column before.
If 5–10 keyword missing, replace — assume likely present

| Category | Missing Keywords Found | Missing Keywords Found (from lens checklist) |
|---|---|---|
| Testing | | e.g., Jest, RTL, Cypress |
| CI/CD | | e.g., GitHub Actions, CI pipeline |
| Cloud | | e.g., AWS, GCP, Docker, K8s |
| State Mgmt | | e.g., Redux, Zustand, Context |
| Architecture | | e.g., microservices, DDD, rate limiting |
| Process | | e.g., TDD, Agile, Scrum, code review |
| Frontend | | e.g., responsive design, a11y, Web Vitals |

### Step 15 — Skills Section — Suggested Re-Org

Group by discipline, not alphabetically. Replace volatility: claim-based overlap threshold, move subordinate to bottom:

```
[Frontend] React.js, Next.js, TypeScript, Tailwind CSS, shadcn/ui, HTML5, CSS3
[Backend] Node.js, Express.js, NestJS, GraphQL (Apollo), REST APIs, JWT, Socket.io
[Databases] PostgreSQL, MongoDB, Firebase, Redis
[Messaging & Queues] BullMQ, Kafka
[DevOps & Cloud] Docker, Docker Compose, Firebase Cloud Functions, GitHub Actions, Render
[Observability] OpenTelemetry, Prometheus, Grafana
[Testing] [add if true]
[Tools] Git, GitHub, Postman
[ORMs] Sequelize
[Concepts] MVC, Middleware, API Design, Security, RBAC
```

### Step 16 — Interview Questions (8–12, Organized by Lens)

#### Technical (Backend / Full Stack)
1. "[Project X] accelerated 40% after adding caching. What first gave you the signal and what did you change?"
2. "One of your projects uses BullMQ and GraphQL. How did you decide on this async queue toolkit versus Kafka/RabbitMQ?"
3. "You implemented rate limiting and RBAC. Why at that layer and how did you handle async errors between layers?"
4. "Walk me through the authentication and authorisation flow across your projects. Where is the JWT stored, refreshed, and revoked?"

#### System Design (Mid+)
5. "Design a real-time notification system supporting push, email, and SMS — what's the queue and failure strategy?"
6. "How did you handle concurrent batch processing in your campaign platform? What race conditions did you anticipate?"

#### Behavioral / HR
7. "You mention 'aspiring' in your summary — what does that mean versus what you can already do?"
8. "What's the most technically complex problem you solved at Logicwind and what was your contribution versus the rest of the team?"

#### AI / Future Tech (if applicable)
9. "Your AI Triage project uses GPT-4 and Claude. In what scenario do you choose one model over the other, and what happens when the API is rate-limited?"
10. "Walk me through the observability stack — what specific metrics changes did you define and what would an SLA breach alert trigger?"

### Step 17 — Final Recommendations (Ranked by Impact)
1. **Inject metrics into every bullet** — this is the single highest-leverage change (→ 82+ potential score lift on AI tiers)
2. **Fix "aspiring" and "B.Tech student" in summary** — these undermine professional credibility; swap for evidence of readiness
3. **Rewrite ownership-absent bullets** — every "contributed to" / "worked on" must become "owned" / "delivered"
4. **Fix AI Triage tense** — "Designing/Architecting/Building" → past tense OR add "(in production / currently architecting, targeted Q3 launch)" — current tense unverified project loses credibility
5. **Add testing + CI/CD evidence** — even basic Jest + GitHub Actions familiarity is expected at mid-level in 2026
6. **Add deployment evidence** — live URL or production service link; GitHub link ≠ deployed
7. **Regroup Skills section** — frontend/backend/databases/devops groups are both more ATS-scannable and more impressive for tech reviewers
8. **Remove "Soft Skills" section** — adjective-only bullets = discarded by all 6 lenses
9. **Cover interview questions** from `questions/p1-question.md`, `questions/p2-question.md`, `questions/p3-question.md`, `questions/Experience-question.md`

### Step 18 — Verdict Table (6 Lenses)

```
| Lens | Score /100 | Level Fit |
|---|---|---|
| Backend Tech Lead | 68/100 | Solid mid-level, not yet Senior |
| Full Stack Engineer | 60/100 | Needs frontend strengthening |
| Frontend Engineer | 45/100 | Not ready for pure frontend roles |
| HR / Talent Acquisition | 65/100 | Passes screening, needs metrics |
| Career Switcher | 70/100 | Solid transition, good project evidence |
| Product Manager (Tech) | 55/100 | Engineering-focused, no product outcome |
```

Use this exact format as the closing table of every full review.

---

## History
Authored by: Charlie, Sep 2025.
Last reviewed: Jul 2026.
