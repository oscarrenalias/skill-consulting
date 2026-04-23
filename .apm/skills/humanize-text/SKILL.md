---
name: humanize-text
description: Use when LLM-generated or LLM-assisted text needs to read like a human wrote it. Strips contrast constructions ("it's not X, it's Y"), signal vocabulary (delve, leverage, robust, seamless), throat-clearing openings, uplift closers, bullet inflation, and bold-salad, while preserving meaning, facts, names, and the author's voice. Example triggers: cleaning up a draft executive brief before sending, sharpening a discovery note, or removing AI-sounding phrasing from any written deliverable.
---

# Humanize Text

## Purpose
This skill rewrites text to remove the recognisable patterns of LLM-generated writing.

The goal is not to shorten the text, make it informal, or inject personality. The goal is to make it read as if a competent human wrote it, with the same meaning and facts.

## When to use
Use this skill when:
- a document was drafted or heavily assisted by an LLM
- a deliverable reads as AI-sounding despite being factually correct
- a consulting output (brief, framing, review) needs to pass as human-authored before sending
- cleanup is repetitive and the same transformations apply throughout the document

Do not use this skill when:
- the text is already in a clear human voice
- the task is translation, summarisation, or expansion rather than style cleanup
- the source is a spec, code listing, or reference material where precision and structure outweigh voice

## Workflow context

**Upstream:** any draft text. Most often the output of consulting-problem-framing, consulting-executive-briefing, or an LLM-assisted first draft.

**Downstream:** the rewritten text is ready for sending, presenting, or inclusion in a larger document. No further consulting skill is usually required.

**Large inputs:** for documents longer than a few thousand words, delegate to the humanize-text agent so the transformation does not bloat the calling conversation.

## Inputs
A block of text (prose, brief, memo, notes). The skill operates on the text as given; it does not fetch additional context.

Preserve as-is:
- technical terms, acronyms, and domain vocabulary
- proper nouns, numbers, dates, client names
- direct quotes
- structural elements (headings, tables, code blocks)

## Anti-patterns to remove

The following are the common tells of LLM-generated writing, in rough priority order — address them top to bottom. The first few (contrast constructions, signal vocabulary, throat-clearing openings, uplift closers) account for most of the AI-sounding quality of a draft; fixing them yields the largest improvement per edit.

### 1. Contrast constructions
- "It's not X, it's Y."
- "This isn't about X — it's about Y."
- "Not just X but Y."

These sound persuasive but usually collapse into a direct claim. Rewrite as the claim itself.

### 2. Signal vocabulary
Words that cluster in LLM text and rarely in human prose on the same topic:
- delve, dive into, navigate, unpack, unlock
- leverage, harness, foster, empower
- robust, seamless, pivotal, comprehensive, holistic, multifaceted
- tapestry, realm, journey, ecosystem, landscape
- intricate, nuanced, dynamic, vibrant
- game-changer, cutting-edge, transformative, revolutionary

Replace with concrete language. "Leverage our data" → "use our data". "A robust framework" → name what makes it robust, or drop the adjective.

### 3. Throat-clearing openings
- "It's worth noting that..."
- "It's important to understand..."
- "Let me walk you through..."
- "At its core, X is..."

Delete the opener; start with the claim.

### 4. Uplift closers
- "By embracing X, organisations can unlock Y."
- "The future of X is Y."
- "Ultimately, this positions the business for Z."

Delete, or replace with a plain statement of what follows.

### 5. Meta-commentary
- "Here's a breakdown of..."
- "To summarise..."
- "In conclusion..."
- "The key takeaway is..."

Remove, or convert directly to the content they introduce.

### 6. Sentence-start adverbs
"Crucially,", "Importantly,", "Notably,", "Interestingly,". Almost always removable. If the point is crucial, the reader will see it.

### 7. Bullet inflation
- flowing prose chopped into one-line fragments
- artificially parallel bullets ("Improve X. Enable Y. Drive Z.")
- lists with fewer than three items where two are trivial

Convert to prose when the items flow naturally. Keep bullets when items are genuinely discrete and of similar weight.

### 8. Em-dash overuse
LLMs reach for em dashes as a default separator. Cap: at most one em dash per paragraph, and only where a comma or period would not serve.

### 9. Hedge stacking
"It might possibly perhaps be a factor that could..." Pick one hedge or none.

### 10. Over-balanced sentences
Clauses that mirror each other too cleanly: "We will improve velocity, we will reduce risk, and we will delight our customers." Break the parallelism.

### 11. Bold-salad
Bolding key terms every other sentence. If everything is bold, nothing is. Keep bold rare.

### 12. Rhetorical questions as transitions
"But what does this really mean?" Delete the question; state the answer.

### 13. Closing pleasantries
"I hope this helps." "Let me know if you have any questions." "Happy to elaborate." Remove from formal outputs.

## Workflow
Follow this sequence.

### 1. Read for meaning
Identify what the author is actually saying. Separate signal (facts, claims, decisions) from noise (framing, filler, uplift).

### 2. Strip openers and closers
Remove throat-clearing intros, meta-commentary, and uplift endings first. These rarely carry meaning.

### 3. Collapse contrast constructions
Rewrite "not X, it's Y" patterns as direct claims.

### 4. Replace signal vocabulary
Substitute concrete words for LLM-favoured abstractions. If no concrete replacement is possible, remove the adjective rather than keep a vague one.

### 5. Deflate bullets
Convert bullet lists to prose where items flow. Keep bullets when items are genuinely discrete.

### 6. Remove redundant adverbs and hedges
Cut sentence-start "Crucially" / "Importantly" / "Notably". Reduce hedge stacks.

### 7. Check em-dash count
At most one per paragraph.

### 8. Preserve what matters
Keep facts, numbers, names, technical terms, structural elements, and the author's intent. Do not rephrase direct quotes.

### 9. Read the result aloud
If a sentence still sounds like a press release or a policy document written by committee, rewrite it again.

## Output format
Return the rewritten text only. No preamble, no "here's the cleaned version" header, no trailing commentary.

If the caller explicitly asks for a change log, append after the text:

```
---

## Notable changes
- <category of change>: <brief note>
```

Keep the change log to at most five bullets, organised by category of change (e.g., "removed contrast constructions", "collapsed three bullet lists into prose"), not line-by-line edits.

## Quality bar
Rewritten text should:
- carry the same meaning as the input
- preserve all facts, numbers, names, and domain terms
- contain at most one em dash per paragraph
- contain no words from the signal vocabulary list, unless the input used them in a technical sense
- begin with content, not with a throat-clearing opener
- end on a plain statement, not on uplift

## Failure modes to avoid
Avoid:
- changing facts or numbers to make sentences flow better
- stripping technical terms to sound more natural
- injecting personality, humour, or informality the author did not use
- flattening the author's voice by over-editing already-human prose
- swapping one filler phrase for a different filler phrase
- adding "I hope this is clearer" style meta-commentary to the rewritten text

## Style
The rewritten output matches the register of the input. A formal brief stays formal; a casual note stays casual. Only the LLM tells are removed.

When in doubt, leave the author's phrasing alone. It is better to under-edit than to flatten the author's voice.

## Worked example

**Before:**

> In today's rapidly evolving business landscape, it's worth noting that organisations must navigate an increasingly intricate set of challenges. This isn't just about adopting new technology — it's about fundamentally transforming how we think about value delivery. By leveraging robust frameworks and fostering a culture of innovation, leaders can unlock unprecedented opportunities. Crucially, the journey ahead requires a holistic approach. I hope this provides a useful starting point for your strategic discussions.

**After:**

> Leaders face a harder set of challenges than a few years ago. The shift required is not technology adoption; it is a change in how the business defines and measures value delivery. The next step is to agree where value currently leaks, which capabilities to build in-house, and which to source externally.

**What was applied:**
- Throat-clearing opener removed ("In today's rapidly evolving business landscape, it's worth noting that").
- Contrast construction collapsed ("This isn't just about X — it's about Y" → direct claim).
- Signal vocabulary cut (*navigate*, *intricate*, *leveraging*, *robust*, *fostering*, *unlock*, *unprecedented*, *journey*, *holistic*). Where the underlying claim was content-free filler, the sentence was replaced with substantive next-step guidance rather than reworded empty phrasing.
- Sentence-start adverb removed ("Crucially").
- Closing pleasantry removed ("I hope this provides a useful starting point").
- Em-dash count reduced from one to zero.
