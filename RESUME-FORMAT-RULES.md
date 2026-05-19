# Resume Format & Voice Rules

> These rules were calibrated through real editing passes on actual submitted resumes. They produce clean, professional Word documents when processed through Pandoc. Follow them exactly.

---

## Format Rules

### Section Headers
- Use `**ALL CAPS BOLD**` lines, NOT `## Markdown` headings
- Pandoc renders `##` as H2 styling that looks wrong in a Word resume

### Header Layout
- Bold name on its own line
- Single dot-separated contact line (address · phone · email · LinkedIn)
- Single bold credentials line (top 3 most-relevant certs, dot-separated)
- NO H1 (`# Your Name`)

### Experience Entries
- **Date FIRST** in bold, then company, then location
- Title on next bold line
- NO squad/team name in title (put it in the first bullet if needed)

### Education Entries
- School name + location on one line (plain text)
- Bold degree on next line

### Section Order
1. Professional Summary
2. Experience
3. Skills
4. Professional Development (certifications)
5. Professional Awards
6. Education
7. Extra-Curricular

### Things to Drop
- No "References available upon request" footer (ever)
- No "Affiliations" header — use **EXTRA-CURRICULAR**
- No markdown `##` headings — use `**ALL CAPS BOLD**`

---

## Voice Rules — Resume Professional Summary

- **NO first-person.** No "I", "I've", "I'd", "I'm", "I will", etc.
- **NO contractions.** "I've" / "I'd" / "won't" do not belong here.
- **ONE paragraph, ~120 words max.** No paragraph break.
- **NO "Combines X with Y" pattern.** NO "Brings the rare combination." These are AI-tells.
- **End with 1-2 short factual sentences** ("Computer Science degree (MIT). Strong technical communicator and presenter.")
- **Lead with a role-class noun phrase** ("Platform engineer and infrastructure leader with..." not "I am a platform engineer who...")

---

## Voice Rules — Resume Bullets

- **Cap current-role bullets at 5-7.** Past-role bullets at 4 max.
- **Outcomes, not stacks.** "Cut deploy time from 45 min to 4 min" beats "Implemented Jenkins CI/CD pipeline with Docker and Kubernetes"
- **Vary lead verbs.** No three consecutive bullets starting with the same verb.
- **Em-dashes are fine** as bullet-internal separators (use sparingly).
- **Drop excessive bolding.** Bold the artifact name and the metric. Not every phrase.

---

## Voice Rules — Cover Letters (DIFFERENT from Resume)

Cover letters use the **opposite** voice from the resume PS:

- **First-person required.** "I" is expected and natural.
- **Contractions required.** At least one per paragraph. "I've" / "I'd" / "won't" are fine.
- **Personal asides required.** At least one moment that sounds like a human, not a model.
- **Em-dash limit:** ≤2 per letter, 0 per DM/outreach.
- **Vary openers.** Don't start every letter with "I'm applying for..."
- **Vary closers.** Don't end every letter with "I look forward to discussing..."
- **Vary sign-offs.** Never default to "Best regards" — cycle: "Thanks," / "Talk soon," / "Cheers," / etc.

### Banned Phrases (AI-tells — remove on sight)

- "leveraging"
- "delve into"
- "robust"
- "comprehensive" (as a praise word)
- "seamless"
- "cutting-edge"
- "landscape" (unless literally geographic)
- "Combines X with Y"
- "Brings the rare combination"
- "I'm thrilled"
- "passionate about"

### Cover Letter Structure (~350-400 words)

1. Opening: which role + 1-line "why I want this" (vary the opener style)
2. 4–6 bulleted direct mappings ("JD says X, I shipped Y")
3. Honest-disclosure section if there are gaps
4. Optional: "Happy to share [work sample] as evidence"
5. Sign off (vary)

---

## Pandoc Build

To convert any resume `.md` to `.docx`:

```bash
pandoc resumes/NN-Category-Role.md -o output/NN-Category-Role.docx --reference-doc=reference.docx
```

If you don't have a `reference.docx` with your preferred styles, Pandoc's default is acceptable for initial submissions. The format rules above ensure it looks like a proper resume regardless.

---

*These rules exist because AI models consistently produce resumes with cover-letter voice (first-person, contractions, "I'm passionate") and markdown formatting (`## headings`) that renders poorly in Word. The rules prevent both failure modes.*
