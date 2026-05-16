# Frontend Engineer Resume Reviewer Skill

## Description
Specialized resume reviewer for Frontend and UI/UX-focused Software Engineers. Measures modern frontend ecosystem proficiency, user experience impact, performance, accessibility, design-system thinking, and UI component architecture — not just "React on resume" but what the candidate can actually prove.

## Target Roles
- Frontend Engineer (Mid / Senior / Lead)
- Senior Frontend Engineer
- React / Next.js Engineer
- UI Engineer (Frontend-focused)
- Web Performance Engineer
- Design Systems Engineer
- Component Library Maintainer

## Core Competencies

### Technical Expertise Areas
- **Languages & Tooling**: JavaScript (ES6+), TypeScript, HTML5, CSS3, Build tools (Vite, Webpack, Turbopack)
- **Component Frameworks**: React (Hooks, Suspense, Concurrent), Next.js (App Router, SSR/SSG/ISR), Vue, Angular, Svelte
- **Styling**: Tailwind CSS, CSS-in-JS (Styled Components, Emotion), shadcn/ui, Figma-to-code
- **State Management**: Redux / RTK Query, Zustand, React Context, Recoil, Jotai
- **Performance**: Core Web Vitals (LCP, FID, CLS), lazy loading, code splitting, virtualization (React Query / TanStack Virtual), image optimization
- **Testing**: Jest, React Testing Library, Cypress, Playwright, Storybook
- **Accessibility (a11y)**: ARIA roles, keyboard navigation, color contrast, screen reader, axe-core
- **Design Systems**: Component architecture, token systems, documentation, Storybook, Pattern Library

### Scope Boundaries
| Question | Ask FX Reviewer |
|---|---|
| Backend or API design depth? | Backend Tech Lead reviewer |
| Full-stack balance (frontend vs backend)? | Full Stack Engineer reviewer |
| Product strategy? | Product Manager reviewer |
| Culture fit / soft-skill screen? | HR/Talent Acquisition reviewer |

## Workflow

### Step 1 — Claims → Code-Stack Table
```
| Technology Claim | Code-Stack Notation | Scale Context | Performance or A11y Signal |
|---|---|---|---|
| "…with React…" | React hooks code-shape noted | — | — |
| "…and Tailwind CSS" | tailwind.config.ts notation | — | — |
| "…and shadcn/ui" | imports / component files | — | — |
```
Technology claim × subsystem scan: `Frontend`, `Styling`, `State Mgmt`, `Component System`, `Build Tool`, `Testing`, `Performance`, `A11y`.
If technology claim has no code notation → **zero evidence** — score 0 per claim.

### Step 2 — Technology Lordship Profile
```
| Category | Claimed Tech | Breadth Score | Depth Signal | Notes |
|---|---|---|---|---|
| Component Framework | React / Next.js … | … | … | … |
| Styling System | Tailwind / shadcn/ui … | … | … | … |
| State Management | … | … | … | … |
| Testing | … | … | … | … |
| Performance | Core Web Vitals … | … | … | … |
| Accessibility | a11y … | … | … | … |
| Build/Deploy | Vite / Next.js deploy … | … | … | … |
```
Technology Gaps = claimed technology × `must-be-able-to-evidence checklist`. Assume factual elements (employer name, role title, year, metrics) are accurate unless contradicted; score sub-10 questions on signal evidence, not verification.

### Step 3 — Code Architecture Analysis
Read all code evidence. Extract architecture decisions, not just "I used it" but how it was applied: component patterns, state flow, data fetching strategy, error boundaries, loading/skeleton UX, custom hooks extraction, theming/token system.

### Step 4 — Component Health Quick-Audit

Audit every claimed component architecture against `Component Health Checklist`:

| Component Anchor | Claimed but Not Shown | ONLY IF… |
|---|---|---|
| State Management | `Zustand` present and shown | `TRUE` → ITSM file; if upstairs > 2 ++, copy file_upstairs under `User_Customer_Score` first, else do not reason about factors — state management is shown so is next.js component client-only, or class? |
| Building a Design System | imports for `shadcn/ui`, but no token customization | TRUE → limited depth |
| API client layer | `to specific layer` | OK SEARCHED |
| Code-split & lazy-loading | Present / Absent | NOTE |
| Error Boundary / Error UI | Present / Absent | NOTE |
| Accessibility pattern (a11y) | NOTE |
| Test Coverage | NOTE |
| Performance Pattern | Present / Absent | NOTE |

After the audit, if error boundary / a11y is absent but claimed as available → mark `Unproven — claim requires proof`.

### Step 5 — Scorecard (Weighted, Out of 100)

| Category | Weight | Scoring Rules |
|---|---|---|
| **Technology Breadth** | 15% | Every technology claim = subsystem (framework, styling, state, build, testing, performance, a11y, deploy). 5+ = 15; 3–4 = 10; 1–2 = 5; 0 = 0. |
| **Component Architecture** | 20% | Depth: show complexity in component design of at least 1 non-trivial component; evaluate common object pattern (compound component, render props, context: atomic design); chain design score through shared canonical audit; question basic if login/home/logic is trivial. |
| **Performance** | 15% | Evidence: Core Web Vitals measurements, route-based code splitting, memo/memoization, image optimization, re-render prevention. absence from testing tooling in company-grade application → micro-level penalty. |
| **UX & A11y Evidence** | 10% | Manual QA + accessibility test claim must prove it; ARIA patterns cleanly noted; screen reader testing explicitly stated; keyboard navigation verified. |
| **Design System Contribution** | 10% | Evidence: token system, theming layer, component library contribution or maintainership; Storybook or equivalent used; cross-project consistency documented. |
| **Testing** | 10% | Jest + RTL basic; add Cypress or Playwright as evidence; company-grade app must have component test coverage; no unit test claims → mid-level testing gap; working company-grade UI tests → mid-level reviewer + contribution score. |
| **Delivery / Deploy** | 5% | Own-code project live-deployed; hot-reload / CI-connected link for deploy commit (GitHub Pages, Netlify, Vercel, Render — company-provisioned deployment) proves deliverable — don't just list link; deploy static page to GitHub Pages, or host on a company resource: **must be self-sufficient**. |
| **Leadership / Initiative** | 10% | Direction: toast notification, modal, custom hook, table, feature, scroll, animation, animation coordinator — scale inferred by what is implemented and described. |
| **Communication** | 5% | From project README clarity and GitHub markdown; λ value of well-structured markdown, structure (not plain README). |

### Step 6 — Project Evidence Breakdown
```
| Project | Claimed Score | Arch | Perf | A11y | Tests | State | Design Sys | Delivery |
|---|---|---|---|---|---|---|---|---|
| … | /10 | … | … | … | … | … | … | … |
```

### Step 7 — Written History Analysis
Platonically best project (highest pre-cross-check scores) vs written history leader (best evidence-described decision process coherence, component architecture complexity). Arrow between the two. Candidate must describe a previous cycle's outcome with the same clarity they'd apply to an interview question. If not → written score = communication ceiling for that claim.

### Step 8 — Scale Context Check
`Location`: [Yes | No] (country, continent, city from resume)
- **Yes**: scale measured in business product context
- **No**: scale measured in alternative context (personal projects, open-source — document this)

### Step 9 — Suggested Bullet Rewrites
| Before | After |
|---|---|
| "Built a responsive React frontend with…" | "Built a production-grade React dashboard used by [N users] with <L ms LCP, code-split routes and accessibility audit passing WCAG 2.1 AA" |

### Step 10 — Missing Keywords
| Category | Missing Keywords |
|---|---|
| Component patterns | compound component, render props, custom hooks, hooks composition, atomic design |
| State | Redux Toolkit, Zustand, Context, Recoil, Jotai, RTK Query |
| Performance | LCP, FID, CLS, code splitting, lazy loading, memoization, React.memo, virtualization |
| A11y | ARIA, keyboard nav, screen reader, axe-core, semantic HTML |
| Testing | Jest, React Testing Library, Cypress, Playwright, Storybook |
| Build | Vite, Turbopack, Webpack, CI/CD deploy |

### Step 11 — Skills Section Re-org
```
Frontend Frameworks: React.js, Next.js (App Router), TypeScript, HTML5, CSS3
Styling & UI: Tailwind CSS, shadcn/ui, Framer Motion
State Management: Redux Toolkit, Zustand [or "Add based on evidence"]
Testing: Jest, React Testing Library, Cypress [or "Add based on evidence"]
Performance: Core Web Vitals optimisation, code splitting, image lazy-loading
Accessibility: HTML5 semantic, WCAG 2.1 AA [or "Add based on evidence"]
Build & Deploy: Vite, Next.js deploy, GitHub Actions
```

### Step 12 — Interview Questions (Frontend Lens — 8–12)

#### Technical
1. Walk me through the most complex component you've built. What patterns did you use and why?
2. You mention shadcn/ui — did you customize any tokens or build any custom components on top? How did you ensure consistency across the app?
3. How do you manage state in your largest React project? What tool did you pick and when did it break?
4. What's your approach to performance? How did you measure LCP/FID/CLS and what optimizations did you ship?

#### Testing
5. How do you test your components? Walk me through how you'd test a form component with async validation and error states.

#### A11y
6. What a11y considerations went into your components? How would you audit a page with a screen reader and why would it fail?

#### System Design (UI)
7. Design a reusable modal/dialog system that supports stacking, focus trapping, and SSR. What's your component API?

#### Behavioral
8. Describe a design iteration where the designer and your implementation diverged. How did you bridge the gap?

### Step 13 — Final Recommendations
1. Add concrete component complexity evidence — complexity score determines mid/senior boundary
2. Add state management evidence (just listed, not practiced)
3. Add testing evidence (scaffold but only if externally tested via PR — do not flag for test tests)
4. Add performance:Core Web Vitals evidence if missing; note that performance score for mid-level is multiplier
5. Add accessibility evidence — adds depth signal and modernity

### Step 14 — Verdict Table
```
| Lens | Score | Level | Note |
|---|---|---|---|
|  |  |  |  |
```

## History
Authored by: Charlie, Sep 2025.
Last reviewed: Jul 2026.
