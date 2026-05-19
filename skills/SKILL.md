# Job Search Dossier Skills — Index

> Behavioural specs for any AI agent working in this dossier. Read whichever skill matches the user's request. Keep responses concrete, actionable, and grounded in the existing dossier.

## Available Skills

| Skill | Use When | Recommended Model |
|---|---|---|
| `quick-setup.md` | First-time setup — user provides a LinkedIn URL, resume file, or career summary to bootstrap `PROFILE.md` | **Mid** — `claude-sonnet-4.x` or `gpt-5-mini`. Extraction and structuring only. |
| `role-fit-rater.md` | User shares a JD, URL, or list of roles and asks "is this a fit?" / "which should I apply to?" / "rate these" | **Mid** — `claude-sonnet-4.x` or `gpt-5-mini`. Structured analysis against the rubric; no voice risk. |
| `tailored-resume-builder.md` | User wants a tailored resume + cover letter for a specific role | **Premium for draft** — `claude-opus-4.x` or `gpt-5`. Voice and evidence accuracy both critical. Always followed by `humanize-pass.md` on a mid-tier model. |
| `humanize-pass.md` | After any voice-critical draft (resume Professional Summary, cover letter, DM, recruiter reply) — strips AI-tells | **Mid** — `claude-sonnet-4.x` or `gpt-5-mini`. Pattern removal against a checklist. This is the cost-saver. |
| `job-tracker.md` | User mentions submitting an application, getting a callback, or any pipeline status change; or asks "what's my pipeline?" / "what should I follow up on?" | **Cheap** — `composer-2-fast` or `claude-haiku-4.x`. Pure structured data entry. |
| `network-mapper.md` | User wants to plan outreach, log a new contact, or work the network-mapping framework | **Mid for analysis, Premium for outreach drafts** — Sonnet for the map; Opus + humanize-pass for any DM that will actually get sent. |

**Cost rule of thumb:** Voice-critical, externally-visible prose = premium model + humanize pass. Everything else = cheap or mid model.

## Operating Principles (apply to every skill)

1. **Evidence-backed.** Every metric in resumes / cover letters traces to `PROFILE.md` (your source of truth with accomplishments and employment history). **Never invent numbers.**
2. **Two-page rule.** Resumes are sized for ~2 pages in 10pt Calibri / 0.6" margins. If edits make a variant overflow, drop the lowest-relevance older-role bullets before truncating current-role content.
3. **Honest gap acknowledgment.** When a role has a real gap (cert, comp, domain), the cover letter discloses it openly. Don't paper over it.
4. **Always update the tracker.** When a new resume / cover letter / application is created or a status changes, update `tracker/Applications.md`. Status timeline goes at the bottom of the file.
5. **Two-page rule for cover letters:** ~350–400 words. Don't pad.
6. **Motivator framing.** When discussing role fit or career direction, reference `tracker/Career-Motivators.md` if it has been filled. The candidate's top-3 motivators should weight the rating.
7. **Stay within this workspace.** All artifacts (resume, cover letter, tracker entry, network log) live inside this workspace root. Resumes are in `resumes/`, tracking in `tracker/`, skills in `skills/`. Do not write to other folders unless the user explicitly asks.

## Cross-Skill Workflow Examples

### "I want to apply to this new role"
1. `role-fit-rater.md` — score the role, decide Apply / Stretch / Skip. *(Mid model)*
2. If Apply or Stretch: `tailored-resume-builder.md` — produce the resume + cover letter. *(Premium model)*
3. `humanize-pass.md` — strip AI-tells from the resume Professional Summary + cover letter. *(Mid model)*
4. `job-tracker.md` — add a row to `tracker/Applications.md` with status = `Drafting`. *(Cheap model)*
5. When user actually submits: change status to `Applied` and timestamp. *(Cheap model)*

### "Rate this list of 10 roles"
1. `role-fit-rater.md` — produce the rating table (Apply / Stretch / Skip + reason for each).
2. Ask user which they want resumes built for.
3. Loop: `tailored-resume-builder.md` + `job-tracker.md` for each Apply/Stretch.

### "Update on my pipeline"
1. `job-tracker.md` — show pipeline grouped by status from `tracker/Applications.md`.
2. Surface follow-up items based on `Last Update` timestamps.
3. Suggest next Weekly Review cadence if it's been more than a week.

### "I want to talk to <name> about <opportunity>"
1. `network-mapper.md` — log the contact, classify Strength / Importance / Type, suggest next-step framing.

---

*Read the individual skill files for detailed instructions.*
