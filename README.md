# AI-Assisted Job Search Operating System

> A complete, open-source system for running a structured job search with AI assistance in [Cursor](https://cursor.com) (or any AI-capable IDE). Human in the loop — the AI drafts, you decide. Nothing leaves your machine without you pressing the button.

---

## What This Is

A folder of markdown files + AI agent "skills" that turn your code editor into a job-search copilot. It handles:

- **Role rating** — paste a JD, get an Apply / Stretch / Skip verdict with reasoning
- **Resume tailoring** — builds a tailored resume + cover letter for each target role
- **Voice cleanup** — strips AI-tells so your documents sound like you, not a model
- **Pipeline tracking** — tracks every role from backlog to offer with follow-up reminders
- **Network mapping** — structured outreach planning with contact classification
- **Weekly reflection** — career-coaching-style check-ins to keep direction aligned with values

## Philosophy

**Human in the loop.** Every communication (resume, cover letter, DM, application) needs your eyes, your edits, and your manual send before it goes anywhere. This system gets you 90% of the way — the last 10% is where your judgment, voice, and accuracy live. That's the part that matters.

**Evidence-backed.** The system refuses to invent metrics. Every number in every resume bullet must trace to your source-of-truth file. If a claim isn't sourced, the AI stops and asks you to confirm.

**Honest about gaps.** When a role is a stretch (missing a cert, comp is low, domain is adjacent), the cover letter discloses it openly. Recruiters trust honesty. The system is built around that principle.

---

## Quick Start

1. Clone this repo (or download the zip)
2. Open in [Cursor](https://cursor.com) or your AI IDE of choice
3. **Paste your LinkedIn URL or drop your resume** and say **"set me up"** — the system generates your profile automatically
4. Confirm your profile, add your target comp and any hard blockers
5. Fill your Career Motivators worksheet (20-30 min, optional but recommended)
6. Start rating roles: paste a JD and say "rate this role for me"

---

## What's Inside

```
START-HERE.md                   ← setup walkthrough (start here)
PROFILE.md                      ← YOUR source of truth (create this)
RESUME-FORMAT-RULES.md          ← how resumes should look
LINKEDIN-UPDATE-PLAYBOOK.md     ← step-by-step profile refresh

skills/                         ← AI agent behavioral specs
  SKILL.md                      ← index + operating principles
  quick-setup.md                ← onboarding from LinkedIn/resume
  role-fit-rater.md             ← Apply / Stretch / Skip rating
  tailored-resume-builder.md    ← resume + cover letter builder
  humanize-pass.md              ← AI-tell removal + voice rules
  job-tracker.md                ← pipeline tracking
  network-mapper.md             ← contact classification + outreach

tracker/                        ← your data lives here
  Applications.md               ← source of truth for all roles
  Pipeline.md                   ← status-grouped view
  Weekly-Review.md              ← Friday cadence template
  Career-Motivators.md          ← motivators worksheet
  Career-Story-Timeline.md      ← career timeline worksheet
  Network.md                    ← contact map

frameworks/                     ← methodology reference
  Career-Coaching-Reference.md  ← 4 frameworks explained

resumes/                        ← your resumes live here
  00-Resume-Template.md         ← blank scaffold
  09-Cover-Letter-Templates.md  ← append letters here
```

---

## How the Skills Work

The `skills/` folder contains behavioral specs that any AI model can follow. When you're in Cursor:

- Say **"Set me up"** + paste LinkedIn URL or resume → the `quick-setup` skill generates your profile
- Say **"Rate this role"** + paste a JD → the `role-fit-rater` skill scores it
- Say **"Build me a resume for this"** → the `tailored-resume-builder` skill creates one
- Say **"Humanize this"** → the `humanize-pass` skill strips AI-tells
- Say **"Update my pipeline"** → the `job-tracker` skill maintains your tracker
- Say **"Who should I reach out to?"** → the `network-mapper` skill suggests contacts

The skills reference each other and chain together automatically. Rate a role → build a resume → humanize it → track it. One flow.

---

## Requirements

- [Cursor](https://cursor.com) (recommended) or any AI-capable IDE
- Any capable AI model (Claude, GPT, etc.)
- [Pandoc](https://pandoc.org/) for `.md` → `.docx` conversion (optional but recommended)
- Python 3 + `python-docx` for formatted resume builds (optional)

---

## Contributing

Found a bug? Have an improvement? PRs welcome. The system is intentionally simple — markdown files and behavioral specs. No dependencies, no build step, no framework.

---

## Support

If this system helped you land interviews or saved you hours of resume-tailoring pain, consider buying me a coffee:

[![Buy Me a Coffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-support-yellow?style=flat-square&logo=buy-me-a-coffee)](https://buymeacoffee.com/originaldopey)

---

## License

MIT — use it, fork it, share it, adapt it. If it helps you land your next role, that's the point.

---

*Built by [Dave Richards](https://linkedin.com/in/dave--a--richards) during a career transition in May 2026. The system was operational within days of starting the search and immediately produced structured, evidence-backed applications that led to productive recruiter conversations.*
