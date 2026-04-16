---
name: executive-briefing
description: Use when analysis, discovery, or technical detail needs to be converted into a concise executive brief with implications, options, recommendation, risks, and decisions required. Example triggers: converting workshop findings into a steering note, translating a technical assessment for a sponsor, or drafting a decision memo for leadership.
---

# Executive Briefing

## Purpose
This skill converts raw information into a clear executive-level briefing suitable for sponsors, senior leadership, or steering groups.

The goal is not to show all analysis. The goal is to support a decision.

## When to use
Use this skill when:
- findings need to be presented to senior stakeholders
- a long discussion or assessment must be condensed
- a recommendation must be made with clear trade-offs
- a technical topic must be translated into business implications
- a decision memo, steering note, or leadership update is needed

Do not use this skill when:
- the audience needs detailed operational instructions
- the work is still too ambiguous to recommend anything
- the material is purely informational with no decision angle

## Workflow context

**Upstream:** compatible with output from any structured analysis or assessment. If an architecture review document is available, the priority recommendations, cross-cutting risks, and advisory view are the most relevant inputs. If a problem framing document is available, use the desired outcomes and success criteria to anchor the implications section.

**Downstream:** the output is typically delivered directly to leadership as a document, a slide deck, or a spoken briefing. No downstream consulting skill is usually required, but the decisions required and next steps sections may initiate a new framing or review cycle.

**Delivery:** the output format produces a structured document by default. If a presentation skill is available, each section maps to one or two slides: situation as an opening context slide, implications as a bullet slide, options as a comparison slide or table, recommendation as a standalone slide, risks and watchpoints as a risk slide, and decisions required plus next steps as a closing action slide. The options section in particular benefits from a side-by-side table format when a spreadsheet or table-capable skill is available.

## Inputs
Use whatever is available from:
- meeting notes
- workshop outputs
- assessments
- architecture reviews
- cost analysis
- risk reviews
- market or vendor research
- delivery status updates

If key facts are missing, make that visible rather than filling gaps with unwarranted confidence.

## Audience assumptions
Assume the audience:
- has limited time
- cares about outcomes, trade-offs, timing, risk, and cost
- does not need unnecessary technical depth
- expects a point of view, not just summary

## Workflow
Follow this sequence.

### 1. Distil the situation
Summarize what is happening in plain language.
Focus on the few facts that matter.

### 2. Extract implications
State what the situation means for:
- business performance
- delivery confidence
- cost
- risk
- timing
- governance
- customer or internal user impact

### 3. Define realistic options
Present a small set of viable options.
Normally use 2 to 4 options only.
Each option should include:
- what it means
- main upside
- main downside
- likely cost or effort profile
- key risk

### 4. Form a recommendation
Give a clear recommendation if the evidence supports one.
Explain why it is preferred now, not in theory.

If no clear recommendation is possible, do not force one. Instead, declare a deferred recommendation. This is appropriate when:
- two options are genuinely equal and the deciding factor is a value judgment only the sponsor can make
- a critical fact is missing and the answer would change materially depending on it
- the recommendation depends on a prior decision that has not been made

In a deferred recommendation, be explicit about:
- what is blocking the recommendation
- what information or decision is needed
- who needs to provide it
- what the recommendation would be under each scenario if that is possible to state

### 5. State the risk view
Highlight the main risks of both action and inaction.

### 6. Clarify required decisions
Be explicit about what leadership needs to approve, align on, or defer.

## Output format
Always use this structure.

### Situation
One concise paragraph.

### Implications
A short bullet list.

### Options
For each option, include:
- label
- summary
- benefits
- drawbacks
- notable risk

### Recommendation
One concise paragraph. If a clear recommendation is not possible, use this section to state what is blocking it, what would need to be true for each option to become the recommendation, and what needs to be decided first.

### Risks and watchpoints
A short bullet list.

### Decisions required
A short bullet list.

### Suggested next steps
A short bullet list with immediate actions.

## Quality bar
A good executive brief should:
- fit on roughly one page when possible
- make the decision obvious even when the choice is difficult
- surface trade-offs honestly
- avoid jargon unless essential
- distinguish facts from judgment
- be readable aloud in a steering meeting

## Failure modes to avoid
Avoid:
- dumping raw analysis without synthesis
- providing too many options
- hiding the recommendation or burying it in caveats when one is genuinely available
- forcing a recommendation when the evidence does not support one — a clear statement of what is blocking the decision is more useful than a false choice
- writing for architects when the audience is executive
- overstating certainty
- presenting risk without practical consequence

## Style
Write with restraint.
Use short paragraphs and compact bullets.
Lead with implications, not background.
Maintain a clear point of view.
