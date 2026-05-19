# Skill: Quick Setup (Onboarding from LinkedIn or Resume)

## Recommended model

`claude-sonnet-4.x` or `gpt-5-mini` — extraction and structuring. Mid-tier is fine; no voice-critical generation.

## Purpose

Kickstart the dossier by extracting profile data from an existing LinkedIn profile or resume file. Generates `PROFILE.md` (the source of truth) so the user doesn't have to fill it from scratch.

## When to Use This Skill

User says any of:
- "Set me up"
- "Here's my LinkedIn" + pastes a URL
- "Here's my resume" + drops a file or pastes content
- "Import my profile"
- "Get me started"
- First time opening the dossier with no `PROFILE.md` present

## Inputs (any one of these)

1. **LinkedIn URL** — fetch the profile and extract structured data
2. **Resume file** — `.pdf`, `.docx`, or `.md` dropped into the workspace or pasted as text
3. **Raw text** — user pastes their resume content or career summary directly

## Workflow

### From LinkedIn URL

1. Fetch the LinkedIn profile (use browser tools or ask user to paste the page content if fetch is blocked).
2. Extract:
   - Name, location, headline
   - Current and past positions (title, company, dates, description)
   - Education
   - Skills
   - Certifications
   - About section
3. Generate `PROFILE.md` using the template below.
4. Ask: "Does this look right? Anything to add or correct?"

### From Resume File

1. Read the resume content.
2. Extract:
   - Name, contact info (offer to redact if user wants PROFILE.md shareable)
   - Professional summary
   - Employment history (company, title, dates, key bullets)
   - Education
   - Certifications
   - Skills
   - Awards
3. Generate `PROFILE.md` using the template below.
4. Ask: "Does this look right? Anything to add or correct?"

### From Raw Text

1. Parse whatever the user pasted — resume text, career summary, LinkedIn copy.
2. Structure into `PROFILE.md`.
3. Ask for confirmation.

## Output: PROFILE.md

Generate this file at the workspace root:

```markdown
# My Profile

**Name:** [extracted]
**Location:** [extracted]
**Target titles:** [inferred from current title + one level up — ask user to confirm]
**Target domains:** [inferred from industry history — ask user to confirm]
**Target comp:** [leave blank — ask user to fill, or infer from level if possible]
**Remote preference:** [infer from LinkedIn location settings if visible, otherwise ask]
**Hard blockers:** [ask user]
**Certifications:** [extracted]
**Citizenship/work auth:** [ask user — never assume]

## Career Summary (2-3 sentences)
[Synthesized from About section or Professional Summary — not copied verbatim]

## Key Accomplishments (the proof)
[Extracted from resume bullets or LinkedIn descriptions — pick the ones with metrics]
- [Accomplishment with metric]
- [Accomplishment with metric]
- [Accomplishment with metric]
- ...

## Employment History
- [Most Recent] Company — Title — Dates
- [Previous] Company — Title — Dates
- [Earlier] Company — Title — Dates
- ...

## Education
- [Degree] — [School] — [Year]

## Certifications
- [Cert 1]
- [Cert 2]
- ...

## Awards
- [Award 1]
- [Award 2]
- ...
```

## After PROFILE.md is Generated

1. Confirm with user: "Does this capture you accurately?"
2. Ask: "What are your target titles and comp range for this search?" (fill the blanks)
3. Ask: "Any hard blockers? (location constraints, visa needs, industries you won't work in)"
4. Suggest: "Ready to fill your Career Motivators worksheet? It takes 20 minutes and anchors your whole search direction."

## What This Skill Does NOT Do

- Does NOT scrape LinkedIn without the user's knowledge (always transparent about what's being read)
- Does NOT invent accomplishments — only extracts what's already documented
- Does NOT fill in comp targets without asking (too personal to assume)
- Does NOT skip the confirmation step — user must verify before the system uses PROFILE.md as source of truth

## Anti-Patterns

- Do **not** copy LinkedIn About section verbatim into Career Summary — synthesize it in the user's voice
- Do **not** guess at citizenship/work authorization — always ask
- Do **not** include contact info (phone, email, address) in PROFILE.md if the user hasn't explicitly provided it — some users may want to keep PROFILE.md shareable
- Do **not** proceed with role-rating or resume-building until the user has confirmed PROFILE.md is accurate

## See Also

- `../START-HERE.md` — full onboarding guide
- `../PROFILE.md` — the output this skill generates
- `role-fit-rater.md` — next step after profile is set up
- `../tracker/Career-Motivators.md` — suggested next action after setup
