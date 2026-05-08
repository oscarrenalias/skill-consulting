---
name: meeting-notes
description: Use when the user wants help capturing meeting notes — either live during a conversation (point-by-point as they type or speak them aloud), or by cleaning up a dump of existing raw notes. Maintains a running structured view, then offers to derive minutes, action items, and follow-ups. Example triggers: "I'm in a 1:1 with X, take notes", "keep notes here", "clean up these notes", "let me dump some notes from this meeting", "draft minutes from this".
---

# Meeting Notes

## Purpose
This skill helps the user capture and structure meeting notes, then turn them into useful downstream artefacts (minutes, action items, follow-ups). It is designed for 1:1s, counseling sessions, status meetings, workshops, client calls, and informal catch-ups.

The goal is not to transcribe. The goal is to leave the meeting with a clean structured record and a clear list of what happens next.

## When to use
Use this skill when:
- the user signals they're starting a meeting and wants notes captured live
- the user wants to dump raw notes (their own scribbles or a transcript) and have them rewritten into structure
- the user wants to derive minutes, action items, or follow-ups from notes already taken
- the user says things like "keep notes here", "I'm talking to X", "draft minutes from this"

Do not use this skill when:
- the user is asking a one-shot question (no ongoing capture needed)
- the content is a project plan, design doc, or other artefact that is not meeting-shaped
- another skill is a better fit — e.g. an executive-briefing skill for steering notes to leadership, or a problem-framing skill for turning a vague request into a problem statement

## Intake modes
The skill supports two intake modes that **can blend freely** in the same session:

1. **Live capture** — the user feeds points one at a time as the meeting happens. After each addition, show the running structured view so the user can see the notes accumulate and correct in flight.
2. **Cleanup of a dump** — the user pastes raw notes (typed scribbles, voice-to-text, an old document). Rewrite them into the same structured form.

Do not treat these as rigid branches. A common pattern is to start in cleanup mode (here is what I jotted down so far) and continue in live mode (more is happening, keep adding). Switch transparently.

## Workflow during capture

### 1. Confirm and stay quiet
When the user signals a meeting is starting, acknowledge briefly and stay out of the way. One short line is enough ("Ready when you are — go ahead."). Do not ask for an agenda, do not propose a structure up front. Structure emerges from the content.

### 2. Group as you go
As points come in, group related items under thematic headings that emerge organically. Common groupings include:
- Client / role context
- What's going well
- Concerns or risks (workload, scope, technical, interpersonal)
- Career / development topics
- Decisions made
- Open questions

Do not invent a fixed template. Let the headings come from the actual conversation.

### 3. Display the running view after each addition
After integrating each new point, show the full updated structured notes back to the user. This:
- lets them spot misinterpretations immediately
- reassures them nothing was dropped
- makes the cumulative shape visible

Keep the running view tight — terse bullets, bold for key terms (names, systems, decisions, dates), short sub-lists for related items.

### 4. Convert relative dates to absolute
"End of June" → "end of June {year}". "Thursday" → the actual date. "Next quarter" → the actual quarter label. Anchor everything so the notes are interpretable when re-read months later.

### 5. Capture the user's own opinions, not just statements of fact
Notes often include "my read" or "I think" interjections from the user. These are valuable — they mark interpretation vs. raw fact. Preserve them as such (e.g. *"My read: sounds like regular delivery challenges, not unusual."*). Do not flatten opinions into facts.

### 6. Stay editable
At any point the user may correct, retract, or reframe ("actually, change that to…", "drop the bit about X"). Apply edits silently to the running view and re-display.

## Post-processing offerings
The default end-state is the structured running view itself — for most meetings (1:1s, informal catch-ups, counseling sessions, quick syncs), that is the entire output and no further artefacts are needed.

The artefacts below are **opt-in**. Once the meeting ends, briefly mention they are available and ask which (if any) the user wants. Do not produce them by default. Do not assume that a meeting requires minutes just because it had multiple topics or decisions — minutes are for circulation to others, not for the user's own record.

### Minutes (for sending out)
A short, structured summary suitable for **circulating to attendees or stakeholders**. The full template below is intended for this circulation use case only — do not apply it to the running notes, to the final cleaned-up notes, or to informal 1:1s and catch-ups where minutes are not being sent anywhere. For those, the structured running view is enough.

Tone is neutral, professional, and brief enough to read in under a minute.

Use the following template:

```
# Meeting Summary

**Meeting:** [Title]
**Date:** [Date]
**Attendees:** [Names]
**Duration:** [Time]

## Purpose
[One sentence describing meeting objective]

## Key Discussion Points
1. [Topic 1]
   - [Key point]
   - [Key point]

2. [Topic 2]
   - [Key point]
   - [Key point]

## Decisions Made
- [ ] [Decision 1]
- [ ] [Decision 2]

## Action Items
| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| [Task] | [Name] | [Date] | Pending |

## Next Steps
- [Next meeting/milestone]

## Notes
[Any additional context or parking lot items]
```

Rules when filling the template:
- If any header field (attendees, duration, date) is unknown, write `(not captured)` rather than guessing or omitting the line.
- **Purpose** is one sentence — resist the urge to expand.
- **Key Discussion Points** should mirror the thematic groups from the running notes; aim for 3–6 topics, each with 2–4 sub-points.
- **Decisions Made** only contains things actually decided. If nothing was decided, write `None recorded.` rather than leaving the section empty or padding it.
- **Action Items** uses the same owner/due-date discipline as the standalone action-item list: flag unknowns with `(owner?)` or `(no date set)`. Default status is `Pending`.
- **Next Steps** is for milestones and the next meeting (date if known) — not for action items, which already have their own table.
- **Notes** is a parking lot for context that did not fit elsewhere (open questions, unresolved threads, side topics). Often empty.

### Action items
Extract anything that resolves to "someone will do X by Y". Format as a small table or tight list with three columns:

| Owner | Action | Due |
|---|---|---|
| Wajid | Confirm staffing extension with account leadership | Before next 1:1 (~2026-05-22) |

Rules:
- If the **owner** is unclear, flag it (`(owner?)`) rather than guessing.
- If the **due date** was not stated, mark it `(no date set)` or propose a sensible default (e.g. "before next 1:1") and flag the proposal.
- Do not invent action items the user did not actually agree to.

### Follow-ups
Items that are *not* action items — open questions, things to revisit, areas to probe further next time. These belong in a separate list because they have no owner or due date but still need to be remembered.

For recurring meetings (1:1s, weekly status), explicitly recommend the **top 1–3 things to bring up next time**, with the next meeting's date if known.

## Persistent storage
The skill itself does **not** save notes to any external system. After the post-processing artefacts are produced, ask the user whether they want the notes (and/or the minutes) persisted somewhere — for example a notebook, a knowledge base, a ticket, or a shared doc. If a suitable skill or tool is available in the current environment for that destination, offer to use it; otherwise, present the notes as text the user can copy out.

Phrase the offer as a question, not a default action. The user may want to keep the notes in-conversation only.

## Output format

### Running view (during capture)
A single structured block under a working title (often the person's name, or the meeting subject). Use markdown headings for thematic groups and bullets for points. Bold key terms.

### Final cleaned-up notes
Same shape as the running view, but tightened — duplicates merged, ordering refined so related thoughts sit together, weak phrasing sharpened. Preserve the user's voice and any explicit opinions.

### Minutes
Use the template defined under **Post-processing offerings → Minutes (for sending out)**. No preamble before or after.

### Action items
A markdown table with columns Owner | Action | Due. If only one or two items, a tight bulleted list is acceptable.

### Follow-ups
A bulleted list. For recurring meetings, end with a numbered list of the **top 1–3 follow-ups for next time**.

## Style
- Terse. Bullets, not paragraphs.
- Bold for names, systems, decisions, dates, and other key terms.
- Use the user's own framing where they have offered one ("regular delivery challenges, not unusual" — keep that phrasing).
- Distinguish facts ("staffed until end of June") from interpretations ("my read: he is hesitant").
- No throat-clearing, no LLM uplift ("Great, I've captured that!"). A silent integration plus the updated view is enough.
- Headings should describe content, not process ("Workload concerns", not "Discussion of workload").

## Failure modes to avoid
- Inventing structure before the content justifies it.
- Inflating short, clear points into long bullets.
- Producing minutes / action items / follow-ups by default without being asked — offer first.
- Applying the formal **Meeting Summary** template to a casual 1:1 or catch-up where the user just wants notes. The template is for circulated minutes only; most meetings end at the structured running view and need nothing more.
- Conflating action items and follow-ups. Action items have an owner and (ideally) a due date; follow-ups are open threads.
- Guessing owners or due dates rather than flagging them as unknown.
- Persisting notes to any external system without first asking the user.
- Letting the running view grow unboundedly — at long meetings, periodically tighten the structure.

## Quality bar
A good output:
- can be re-read months later and still make sense (absolute dates, named systems, no in-the-moment shorthand)
- separates fact from interpretation
- makes action items unambiguous (who, what, by when)
- is short enough that the user trusts it as a complete record
