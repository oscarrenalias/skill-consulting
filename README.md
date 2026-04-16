# skill-consulting

A set of Claude Code skills for consulting work, covering problem framing, architecture and operating model review, and executive briefing.

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

The three skills form a natural sequence:

```
consulting-problem-framing
        ↓
consulting-architecture-operating-model-review
        ↓
consulting-executive-briefing
```

Each skill describes its upstream and downstream context, including how output maps to slide decks or spreadsheets when a presentation or spreadsheet skill is also available. Skills are designed to be used independently — none requires the others to be installed.
