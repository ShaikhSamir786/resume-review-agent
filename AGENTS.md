# Resume Review Agent Instructions

This file provides instructions for ANY AI coding/chat agent working in this repository. Whether you are Cursor, Copilot, Claude Code, opencode, Windsurf, or any other AI assistant, these rules apply automatically.

## 0. Prerequisite: Read the Resume

Before loading any lens, read `main.tex` from the repo root. If it doesn't exist, stop and report the error. All analysis must reference specific text from the resume — never write a generic review.

## 1. Use ALL Reviewer Lenses

When asked to review, analyze, critique, or improve a resume in this repo, you MUST read and apply every reviewer lens file defined in `agents/`:

| Lens | File |
|---|---|
| **Backend Tech Lead** | `agents/backend-tech-lead-resume-reviewer.md` |
| **Full Stack Engineer** | `agents/full-stack-engineer-resume-reviewer.md` |
| **Frontend Engineer** | `agents/frontend-engineer-resume-reviewer.md` |
| **HR / Talent Acquisition** | `agents/hr-talent-acquisition-resume-reviewer.md` |
| **Career Switcher** | `agents/career-switcher-resume-reviewer.md` |
| **Product Manager (Tech)** | `agents/product-manager-resume-reviewer.md` |

**You must read each file.** Do not skip any perspective. Each lens evaluates different criteria and reveals different gaps.

In addition to these role-based lenses, also load any **section-specific lenses** auto-generated from the resume sections (e.g., `agents/technical-skills-reviewer.md`, `agents/education-reviewer.md` — see Section 4c). These section lenses evaluate depth, completeness, and relevance of individual resume sections.

**If a lens clearly doesn't apply to the candidate** (e.g., Career Switcher on a senior with no career transition), note it as "Not Applicable" and exclude it from the weighted average instead of forcing a score.

> Note: `agents/skill.md` is a deprecated general template superseded by the specific lenses above. Do not load or reference it.

## 2. Follow This Output Structure

Use `summary.md` as a reference for tone and depth.

### 2a. Header
- **Multi-Perspective Score** (weighted average across all lenses, /100)
- **Recommendation** (Strong Hire / Hire / Potential / Not Recommended)
- **Level assessment** (e.g., Entry-Level / Mid-Level / Senior / Tech Lead)

### 2b. Scorecard Table

Each lens produces a raw score /100. Map them to the categories below. Exclude "Not Applicable" lenses from all averages.

| Category | Weight | Score | Computation |
|---|---|---|---|
| Technical Balance | 25% | | avg(Backend, Full Stack, Frontend) |
| Achievement Impact | 25% | | avg(Backend, Full Stack, PM) |
| Technical Depth | 20% | | Backend Tech Lead lens score |
| Structure & Presentation | 15% | | avg(HR, Frontend) |
| ATS & HR Optimization | 10% | | HR / Talent Acquisition lens score |
| Overall Presentation | 5% | | avg(all applicable lenses) |

**Multi-Perspective Score** = weighted sum of all category scores above.

### 2c. Lens-by-Lens Analysis

For each lens, provide:
- **What's good** — specific strengths evidenced on the resume
- **What's missing** — concrete gaps relative to that role
- **Verdict** — why this score, what level they'd fit (omit numeric score here — the table in 2j is the single source of truth)

### 2d. Critical Issues (Priority Order)

List the top 5 blockers ranked by severity. Be specific. Reference the resume text.

### 2e. Suggested Rewrites (Before → After Table)

Rewrite vague/task-based bullets into quantified, ownership-driven statements. Use this format:

| Before | After |
|---|---|
| "Contributed to..." | "Delivered..." |

### 2f. Missing Keywords (by Category)

| Category | Missing Keywords |
|---|---|

### 2g. Skills Section Reorganization

Suggest grouped categories (Frontend / Backend / Databases / DevOps / etc.).

### 2h. Interview Questions

Generate probing questions for every section of the resume. Reference existing question files for depth. The files follow a consistent naming rule — scan `questions/` for the complete list:

| Naming Rule | Example |
|---|---|
| `\section{...}` → **lowercase-kebab-case** + `-question.md` | `\section{Technical Skills}` → `technical-skills-question.md` |
| Projects → `p<number>-question.md` (per project) | `p1-question.md` |

Split into:
- Technical questions (role-specific)
- System Design questions
- Behavioral / HR questions

### 2i. Final Recommendations

Numbered list of actionable changes, ranked by impact.

### 2j. Verdict by Lens Table

| Lens | Score | Level |
|---|---|---|

## 3. Automatic Application

These instructions apply to ANY resume-related request in this repo. You do not need the user to specify which perspective to use. Always use all applicable lenses (every file in `agents/` except `skill.md`).

| Request | Action |
|---|---|
| "Review this resume" | Full multi-perspective review with summary.md structure |
| "Improve this resume" | Suggested rewrites + missing keywords + critical issues |
| "What are weak points" | Critical issues from ALL lenses |
| "Generate interview questions" | Questions modeled on existing `questions/*.md` files (one per resume section) using all applicable lenses |
| "Score this resume" | Weighted scorecard from all lenses |
| "Tailor for [role]" | Re-weight lenses relevant to the target role, flag top gaps, suggest specific additions |
| "Compare this resume with [file]" | Run full review on each resume; produce side-by-side score, strength, and gap comparison |
| "Summarize changes since last review" | Diff current review against previous; call out score changes, new issues, resolved gaps |

## 4. Maintain Review & Question Files

### 4a. Summary File (`summary.md`)

After every full review, write the output to `summary.md` using the structure defined in Section 2. If `summary.md` doesn't exist, create it. If it does exist, overwrite it with the latest review.

### 4b. Question Files (`questions/`)

When the resume (`main.tex`) is updated — sections added, removed, renamed, or content changed — you MUST sync the question files:

- If `questions/` does not exist, create it.
- For each section on the resume, generate a corresponding question file using this naming convention:
  - Extract the `\section{...}` heading text from `main.tex`.
  - Convert it to **lowercase-kebab-case** (spaces → hyphens, remove special characters).
  - Append `-question.md` → e.g., `\section{Technical Skills}` → `technical-skills-question.md`.
  - **Exception**: For the **Projects** section (which contains multiple `\resumeProjectHeading` items), generate one file per project as `p<number>-question.md` (e.g., `p1-question.md`).
- Follow the tone, depth, and structure of the existing question files (categorized by role lens, system design, behavioral, fundamentals). For new sections with no existing template, generate questions covering: Architecture & Design, Tech Stack Depth, System Design, and Fundamentals — modeled on the style of the existing `p1-question.md` / `p2-question.md` files.
- Remove question files for sections that no longer exist on the resume.

### 4c. Reviewer Lens Files (`agents/`)

When sections on the resume change, auto-generate section-specific reviewer lenses in `agents/` using the same naming convention:

- For each `\section{...}` heading on the resume, generate `agents/{kebab-name}-reviewer.md` (lowercase-kebab-case, no `skill.md` clash).
  - Example: `\section{Education}` → `agents/education-reviewer.md`
  - Exception: **Projects** → skip (already evaluated via `p<number>-question.md` in questions/).
- Each generated file is a focused reviewer that evaluates only that section's content. Follow this structure:

  ```markdown
  # {Section Name} — Section Reviewer

  Evaluates the depth, completeness, relevance, and presentation of the {section name} section.

  ## Evaluation Criteria
  - *specific criteria for this section type*

  ## What to Look For
  - *specific checks*

  ## Common Issues
  - *typical gaps*
  ```

- Use the existing `agents/*.md` files as tone/structure templates. For sections with no existing template, generate criteria based on best practices for that section type (e.g., Education: degree relevance, GPA formatting, coursework alignment; Technical Skills: grouping, proficiency levels, modern tooling).
- Remove reviewer files for sections that no longer exist on the resume.
- Do **not** overwrite role-based permanent lenses (Backend Tech Lead, Full Stack, etc.) — they stay regardless of resume content.
