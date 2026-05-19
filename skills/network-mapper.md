# Skill: Network Mapper

## Recommended model

**Two-tier:** Mid for the map analysis (Sonnet 4.x or GPT-5-mini); **Premium + humanize-pass** for any DM, email, or outreach message that will actually be sent. DMs are the highest-AI-detection-risk content in the dossier — both LinkedIn's ranking algorithm and the recipient's gut-check will flag a templated-feeling message faster than a resume will.

## Purpose

Apply the "Map Your Network" methodology to your job search. Every contact gets logged with **Strength × Importance × Type** and a **Next Step**. Helps keep outreach systematic and balanced (Informational / Structural / Emotional).

## When to Use This Skill

User says any of:
- "I want to reach out to <name>"
- "Add this contact to my network"
- "Who can help me with X?"
- "I'm thinking about messaging <name>"
- After any LinkedIn DM / email / call with a contact
- Weekly review — surface relationships that need updating

## Framework Reference

Source: `../frameworks/Career-Coaching-Reference.md` — Map Your Network section.

**Three classifications per contact:**

1. **Strength** — `Strong` / `Medium` / `Weak`
   - Strong: regular contact, knows each other well
   - Medium: occasional contact, don't know each other well
   - Weak: met once or twice, barely know each other

2. **Importance** to current networking objective — `Very` / `Reasonably` / `Not very`

3. **Type of support** offered — *(can be multiple)*
   - **Informational** — understands how things work, what's expected, skills needed
   - **Structural** — can make you visible to key stakeholders, well-positioned for new opportunities
   - **Emotional** — invested in your happiness/success, encouragement, helping overcome obstacles

**Goal:** balanced portfolio across all three types.

## Network.md Schema

Maintain in `../tracker/Network.md`:

### Top Section: Networking Objective

```
## Current Networking Objective

[Single sentence — e.g., "Find Senior Engineering roles at developer-tools companies in NYC/Remote, target 3 months."]

Last updated: YYYY-MM-DD
```

### Main Table

```
| ID | Date Added | Date Last Contact | Name | Role / Company | How They Help | Strength | Importance | Type | Notes / Next Step |
```

- ID = `N001`, `N002`, etc.
- Strength = `Strong` / `Medium` / `Weak`
- Importance = `Very` / `Reasonably` / `Not very`
- Type = `Informational` / `Structural` / `Emotional` (use multiple where applicable)

### Outreach Log Section

Append-only log of every conversation:

```
## Outreach Log

- 2026-05-15 · N001 <name> · Sent LinkedIn DM re: <topic>
- 2026-05-16 · N001 <name> · Replied — agreed to 20-min call next week
- 2026-05-23 · N001 <name> · 20-min call — they suggested talking to <name>
```

## Operations

### Add a contact
1. Append a row to `Network.md` with the next ID and `Date Added = today`.
2. Classify Strength / Importance / Type using the rubric above.
3. Set `Notes / Next Step` = the action you'll take next.
4. Append to Outreach Log if there's been any contact.

### Log an interaction
1. Append a line to Outreach Log.
2. Update `Date Last Contact` on the contact's row.
3. Update `Notes / Next Step` with what's owed next.

### Plan outreach round
When user says "who should I reach out to?":
1. Filter Network.md by Importance = `Very` AND Date Last Contact > 30 days ago → surface as "stale strong leads".
2. Filter by Type — if you're missing one of (Informational / Structural / Emotional), surface contacts in that Type to balance.
3. Suggest 3–5 specific outreach messages with the framing each contact needs.

### Outreach message templates

**For a Strong / Informational contact** (close colleague who knows the field):
> "Hi [name] — I'm starting to look at the next chapter and I want your honest take on [specific question]. 20 minutes when you have a window?"

**For a Medium / Structural contact** (someone who can make introductions):
> "Hi [name] — hope all's well. I'm exploring [level] roles in [domain] at [company-type]. Do you know anyone at [company] or in [community] I should talk to? Happy to return the favor."

**For a Weak / Informational contact** (someone you've met once):
> "Hi [name] — we connected at [event/topic] a while back. I'm researching [field] as I plan my next move and remembered your perspective on [specific topic]. Would 15 minutes be possible?"

## Reciprocity Rule

Networking is more effective and satisfying when reciprocal. After every conversation, ask: *what can I offer this person?* Examples:
- An intro to someone in their orbit
- A LinkedIn endorsement / recommendation
- A specific insight from your domain expertise
- A relevant article or resource
- A coffee-chat referral

Log the reciprocity action in Notes.

## Anti-Patterns

- Do **not** classify a contact higher than they actually are (overly-strong inflation makes the map useless)
- Do **not** ask for a favor without offering reciprocity — at minimum say "happy to return the favor"
- Do **not** message multiple Strong contacts the same week if you're going to need them again later
- Do **not** ghost — if a contact responded, log it and close the loop within 5 days
- Do **not** treat Network.md as a sales CRM — it's a relationship map, not a deal stage tracker

## See Also

- `../frameworks/Career-Coaching-Reference.md` — Map Your Network methodology
- `../tracker/Network.md` — the actual map data
- `job-tracker.md` — when a contact connects you to a role, link the Network ID into the Application's `Recruiter` or `Notes` column
- `../tracker/Weekly-Review.md` — weekly check-in includes networking cadence
