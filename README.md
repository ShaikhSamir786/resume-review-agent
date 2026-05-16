# Resume Review Agent

**Multi-perspective AI-powered resume review system** — drop in a LaTeX resume and get scored, critiqued, and improved by 6+ expert reviewer lenses (Backend Tech Lead, Full Stack Engineer, Frontend Engineer, HR/Talent Acquisition, Career Switcher, Product Manager) plus auto-generated section-specific reviewers.

Built for any AI coding agent — opencode, Cursor, Copilot, Windsurf, Claude Code, and more.

---

## How It Works

```
main.tex (your resume)
    │
    ▼
  AI Agent reads AGENTS.md
    │
    ├── loads 6 role-based lenses from agents/
    ├── loads section-specific lenses (auto-generated)
    ├── generates weighted scorecard
    ├── writes detailed review to summary.md
    ├── syncs interview questions to questions/
    └── syncs section reviewers to agents/
```

Every review is a **multi-perspective analysis**: the same resume gets evaluated through 6 distinct career lenses simultaneously, producing a weighted score, critical issues, suggested rewrites, and interview questions.

---

## Project Structure

```
resume-review-agent/
│
├── AGENTS.md              # Master instructions for AI agents (the "brain")
├── main.tex               # The LaTeX resume to review
├── summary.md             # Latest review output (auto-generated)
├── README.md              # This file
│
├── agents/                # Reviewer lens files
│   ├── backend-tech-lead-resume-reviewer.md       # [Permanent] Deep technical + architecture
│   ├── full-stack-engineer-resume-reviewer.md     # [Permanent] Full-stack balance
│   ├── frontend-engineer-resume-reviewer.md       # [Permanent] Frontend depth
│   ├── hr-talent-acquisition-resume-reviewer.md   # [Permanent] ATS + HR screening
│   ├── career-switcher-resume-reviewer.md         # [Permanent] Career transition
│   ├── product-manager-resume-reviewer.md         # [Permanent] Product thinking
│   ├── summary-reviewer.md             # [Auto] Evaluates profile summary
│   ├── experience-reviewer.md          # [Auto] Evaluates work experience
│   ├── technical-skills-reviewer.md    # [Auto] Evaluates skills section
│   ├── education-reviewer.md           # [Auto] Evaluates education
│   └── skill.md                        # [Deprecated] Do not use
│
├── questions/              # Interview question banks (auto-generated from \section{} headings)
│   ├── {section}-question.md   # e.g., summary-question.md, experience-question.md
│   ├── p1-question.md          # Per-resumeProjectHeading (Sahara Tyre)
│   ├── p2-question.md          # Per-resumeProjectHeading (Eventifyy)
│   └── p3-question.md          # Per-resumeProjectHeading (AI Triage)
```

---

## Quick Start

### 1. Add Your Resume

Replace `main.tex` with your own LaTeX resume. The file uses `\section{}` headings — these drive auto-generation of question files and section reviewers.

### 2. Run a Review

Open the repo in any AI coding agent and say:

> "Review this resume"

The agent will automatically:
1. Read `main.tex`
2. Load all reviewer lenses from `agents/`
3. Generate a weighted scorecard
4. Write the full review to `summary.md`

### 3. Other Commands

| Say | What Happens |
|---|---|
| "Review this resume" | Full multi-perspective review → `summary.md` |
| "Improve this resume" | Suggested rewrites + missing keywords + critical issues |
| "What are weak points" | Critical issues from ALL lenses |
| "Score this resume" | Weighted scorecard from all lenses |
| "Generate interview questions" | Question bank for every resume section |
| "Tailor for [role]" | Re-weight lenses for a specific job title |
| "Compare this resume with [file]" | Side-by-side analysis with another resume |
| "Summarize changes since last review" | Diff-based summary of improvements |

---

## Scoring System

Each lens scores the resume out of 100. These feed into a weighted scorecard:

| Category | Weight | Sources |
|---|---|---|
| Technical Balance | 25% | avg(Backend, Full Stack, Frontend) |
| Achievement Impact | 25% | avg(Backend, Full Stack, PM) |
| Technical Depth | 20% | Backend Tech Lead lens |
| Structure & Presentation | 15% | avg(HR, Frontend) |
| ATS & HR Optimization | 10% | HR / Talent Acquisition lens |
| Overall Presentation | 5% | avg(all lenses) |

**Multi-Perspective Score** = weighted sum of all categories.

Lenses that don't apply (e.g., Career Switcher on a non-switcher) are excluded from averages.

---

## Adding a New Reviewer Lens

Drop a file in `agents/` following this naming convention:

```
agents/{role-name}-resume-reviewer.md
```

The agent will automatically pick it up. Each lens should define:
- Evaluation criteria / score
- What's good / what's missing
- Suggested rewrites
- Interview questions

---

## Auto-Generation Features

When `main.tex` is updated, three things sync automatically:

### Section → Question Files
`\section{Technical Skills}` → `questions/technical-skills-question.md`

### Section → Reviewer Lenses
`\section{Education}` → `agents/education-reviewer.md`

### Project → Question Files
`\resumeProjectHeading{...}` → `questions/p1-question.md`, `p2-question.md`, etc.

Stale files for removed/renamed sections are cleaned up.

---

## Requirements

- Any AI coding agent that reads markdown files (opencode, Cursor, Copilot, Windsurf, Claude Code, etc.)
- A LaTeX resume at `main.tex`
- Git (for version tracking, optional)

---

## License

MIT — use freely, adapt for your own resume review pipeline.
