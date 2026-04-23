# skill-consulting

A set of Claude Code skills for consulting work, covering problem framing, architecture and operating model review, executive briefing, and LLM-voice cleanup for written deliverables.

## Skills

### consulting-problem-framing
Turns a vague client request or early-stage conversation into a structured consulting problem statement. Produces a framing document covering business context, desired outcomes, scope, constraints, stakeholders, assumptions, success criteria, and a recommended next step.

Use it at the start of a proposal, discovery engagement, or any situation where the sponsor's desired outcome is not yet precise.

### consulting-architecture-operating-model-review
Reviews a platform, system, or delivery model against a structured consulting rubric covering 11 dimensions: business alignment, architectural coherence, scalability and resilience, security and compliance, operability, ownership, governance, delivery viability, cost efficiency, vendor exposure, and data and AI posture.

Produces an advisory-grade assessment with dimension ratings, findings, cross-cutting risks, and prioritised recommendations. Includes weighting guidance so findings are calibrated by structural importance, not treated as equally critical.

### consulting-executive-briefing
Converts raw analysis, assessment output, or technical findings into a concise executive brief suitable for sponsors, steering groups, or senior leadership. Structured around situation, implications, options, recommendation, risks, and decisions required.

Handles cases where no clear recommendation is possible, producing a deferred recommendation that states explicitly what needs to be decided and by whom.

### humanize-text
Rewrites text to remove the recognisable patterns of LLM-generated writing — contrast constructions ("it's not X, it's Y"), signal vocabulary (delve, leverage, robust, seamless), throat-clearing openings, uplift closers, bullet inflation, and bold-salad — while preserving meaning, facts, names, and the author's voice.

Useful on any consulting deliverable drafted or heavily assisted by an LLM: briefs, framings, review output, discovery notes. Ships with a companion `humanize-text` agent for long documents, which applies the same rules in an isolated context and returns only the rewritten text.

## Agents

### humanize-text
Long-document variant of the humanize-text skill. Accepts document text or a file path, applies the cleanup rules in an isolated subagent context, and returns only the rewritten version so it does not bloat the calling conversation. Use for anything above a few thousand words; use the skill directly for shorter text.

## Installation

**With apm:**
```
apm install oscarrenalias/skill-consulting#v0.1.1
```

**Without apm:** download the zip from the [latest release](https://github.com/oscarrenalias/skill-consulting/releases) and extract it into your `.claude/` or `.agents/` folder:

```
unzip skill-consulting-<version>.zip -d ~/.claude/
```

## Workflow

The three consulting skills form a natural sequence:

```
consulting-problem-framing
        ↓
consulting-architecture-operating-model-review
        ↓
consulting-executive-briefing
        ↓
humanize-text (optional cleanup pass)
```

Each skill describes its upstream and downstream context, including how output maps to slide decks or spreadsheets when a presentation or spreadsheet skill is also available. Skills are designed to be used independently — none requires the others to be installed.

The `humanize-text` skill is orthogonal to the consulting sequence and can be applied to any draft, including content produced outside these skills.
