# START HERE — AI-Assisted Job Search Operating System

> Open this file first. It walks you through setting up your own job search dossier using AI agent skills, structured tracking, and career-coaching methodology (BeBold).

**What this is:** A complete system for running a job search with AI assistance in Cursor (or any AI-capable IDE). It includes agent skills that automate resume tailoring, role rating, pipeline tracking, networking, and voice cleanup — plus structured career-coaching worksheets to anchor your direction.

**What it is NOT:** A job board, an ATS, or a Chrome extension. It's a folder of markdown files + AI agent instructions that turn your editor into a job-search copilot.

---

## Setup (15 minutes)

### Step 1: Fill in your profile

Create a file called `PROFILE.md` in this root folder. This is your source of truth — every skill references it.

```markdown
# My Profile

**Name:** [Your full name]
**Location:** [City, State]
**Target titles:** [e.g., Senior Software Engineer, Staff Engineer, Engineering Manager]
**Target domains:** [e.g., fintech, healthcare, developer tools, e-commerce]
**Target comp:** [$XXK+ base / $XXXK+ total comp]
**Remote preference:** [Remote / Hybrid / On-site / Flexible]
**Hard blockers:** [Things you can't do — e.g., relocate to X, need visa sponsorship, etc.]
**Certifications:** [List your current certs]
**Citizenship/work auth:** [US Citizen / Green Card / H1B / etc.]

## Career Summary (2-3 sentences)
[Who you are, what you've done, what you're known for. This feeds your resume PS and cover letters.]

## Key Accomplishments (the proof)
- [Accomplishment 1 with metric]
- [Accomplishment 2 with metric]
- [Accomplishment 3 with metric]
- [Add as many as you have — these are the bullets your resumes draw from]

## Employment History
- [Current/Most Recent] Company — Title — Dates
- [Previous] Company — Title — Dates
- [Earlier] Company — Title — Dates

## Education
- [Degree] — [School] — [Year]
```

### Step 2: Fill your Career Motivators worksheet

Open `tracker/Career-Motivators.md`. Spend 20-30 minutes allocating 25 points across 14 career motivators. This anchors your entire search direction — which roles to prioritize, which to skip.

### Step 3: Sketch your Career Story Timeline

Open `tracker/Career-Story-Timeline.md`. Plot your career highlights and low points. This tells you what to look for (and avoid) in the next role.

### Step 4: Start tracking roles

When you find a role to evaluate, tell the AI: "Rate this role for me" and paste the JD. The `role-fit-rater` skill will score it Apply / Stretch / Skip and add it to your tracker.

---

## How the System Works

```
PROFILE.md (your source of truth)
    ↓
role-fit-rater skill → Apply / Stretch / Skip verdict
    ↓
tailored-resume-builder skill → resume + cover letter
    ↓
humanize-pass skill → strips AI-tells, matches your voice
    ↓
job-tracker skill → updates Applications.md + Pipeline.md
    ↓
network-mapper skill → tracks outreach, suggests contacts
    ↓
Weekly Review (every Friday) → structured reflection + pipeline check
```

### The Skills (in `skills/`)

| Skill | What it does | When to use |
|---|---|---|
| `role-fit-rater.md` | Scores a JD against your profile → Apply / Stretch / Skip | "Is this a fit?" / "Rate these roles" |
| `tailored-resume-builder.md` | Builds a tailored resume + cover letter for a specific role | "Build me a resume for this role" |
| `humanize-pass.md` | Strips AI-tells from any draft; enforces voice rules | After any resume/cover letter/DM is generated |
| `job-tracker.md` | Maintains Applications.md and Pipeline.md | "Update my pipeline" / "What should I follow up on?" |
| `network-mapper.md` | Tracks contacts with structured classification | "Who should I reach out to?" / "Add this contact" |

### The Tracker (in `tracker/`)

| File | Purpose |
|---|---|
| `Applications.md` | Source of truth — every role you're evaluating or have applied to |
| `Pipeline.md` | Derived view — grouped by status (Active / Backlog / Closed) |
| `Weekly-Review.md` | Friday cadence — numbers, reflection, next-week targets |
| `Career-Motivators.md` | Your Top 3 career motivators (drives role-fit decisions) |
| `Career-Story-Timeline.md` | Career highlights/lows plotted on a timeline |
| `Network.md` | Contacts classified by Strength × Importance × Type |

### The Methodology (in `frameworks/`)

| File | Purpose |
|---|---|
| `Career-Coaching-Reference.md` | Four career-coaching frameworks that anchor the whole system |

---

## Weekly Cadence (Every Friday)

1. Run a pipeline check: "What should I follow up on?"
2. Open `tracker/Weekly-Review.md` and fill a new entry
3. Check: does your active pipeline align with your Top 3 motivators?
4. Set next week's targets (2–3 specific applications or outreach actions)
5. Network review: anyone stale? Any support type (Informational/Structural/Emotional) missing?

---

## Tips

- **Start small.** You don't need to fill everything at once. Do Step 1-2 today, then start rating roles.
- **Let the AI do the heavy lifting.** Paste a JD and say "rate this." Say "build me a resume for this." Say "humanize this cover letter." The skills handle the rest.
- **Be honest about gaps.** The system is built around honest disclosure — if you're missing a cert or the comp is below target, the cover letter says so openly. Recruiters trust honesty.
- **Two informational conversations per week.** Use `network-mapper` to plan outreach. 70-80% of jobs come through networking.
- **Update the tracker religiously.** It's your audit trail. Append-only status timeline means you can always see what happened and when.

---

## File Structure

```
START-HERE.md                   ← you are here
PROFILE.md                      ← YOUR source of truth (create this first)
RESUME-FORMAT-RULES.md          ← how resumes should look (format + voice)
LINKEDIN-UPDATE-PLAYBOOK.md     ← step-by-step profile refresh guide

skills/
  SKILL.md                      ← skill index + operating principles
  role-fit-rater.md             ← Apply / Stretch / Skip rating
  tailored-resume-builder.md    ← resume + cover letter builder
  humanize-pass.md              ← AI-tell removal + voice enforcement
  job-tracker.md                ← pipeline tracking
  network-mapper.md             ← BeBold networking methodology

tracker/
  Applications.md               ← source of truth for all roles
  Pipeline.md                   ← status-grouped view
  Weekly-Review.md              ← Friday cadence template
  Career-Motivators.md          ← BeBold motivators worksheet
  Career-Story-Timeline.md      ← BeBold timeline worksheet
  Network.md                    ← contact map

frameworks/
  Career-Coaching-Reference.md  ← methodology reference (4 frameworks)

resumes/
  00-Resume-Template.md         ← blank resume scaffold
  09-Cover-Letter-Templates.md  ← cover letter sections (append here)
```

---

## Credits & Philosophy

- **Career coaching frameworks:** The motivators, story timeline, and network mapping methodology draw from established career-coaching practice. The specific adaptation for AI-assisted job search is original.
- **Human in the loop:** This system gets you 90% of the way — every resume, cover letter, DM, and application still needs your eyes, your edits, and your manual send. The AI drafts; you decide. Nothing leaves your machine without you pressing the button.
- **System design:** Built as an AI-assisted job search operating system. The skills are designed to work with Claude, GPT, or any capable model inside Cursor or similar AI IDEs.

---

*Fork this, fill in your profile, and start searching. The system does the busywork; you do the thinking.*
