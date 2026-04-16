---
name: architecture-operating-model-review
description: Use when reviewing a platform, system, delivery model, or target-state design against a structured consulting rubric covering architecture quality, operating model, governance, ownership, and delivery viability. Example triggers: a client asking whether their platform is fit for purpose, reviewing a proposed target architecture, or preparing an advisory assessment for leadership.
---

# Architecture and Operating Model Review

## Purpose
This skill provides a structured review of a system, platform, or technology function across both technical architecture and operating model.

It is intended for advisory work, not only technical critique. The output should explain what is wrong, why it matters, and what should change.

## When to use
Use this skill when:
- assessing the current state of a platform or estate
- reviewing a proposed target architecture
- evaluating delivery readiness for a transformation
- identifying structural risks in ownership or governance
- preparing an advisory assessment for leadership
- comparing architectural soundness with organizational ability to run it

Do not use this skill when:
- the task is a narrow code review
- only detailed implementation guidance is needed
- there is not enough information to make even a provisional assessment

## Workflow context

**Upstream:** often follows a problem framing exercise or a discovery phase. If a framing document is available, use the problem statement, scope, and constraints sections as context. If not, infer scope and priorities from whatever inputs are provided.

**Downstream:** findings from this review are a natural input to an executive briefing. If a skill for that purpose is available, pass the priority recommendations and advisory view as the primary input. The cross-cutting risks section is particularly useful for the risk and watchpoints section of a briefing.

**Delivery:** the output format produces a structured document by default. If a presentation skill is available, map the output as follows: executive summary and overall assessment to an opening summary slide, each review dimension to a findings slide or grouped section, cross-cutting risks to a risk slide, and priority recommendations to a closing roadmap slide. If a spreadsheet skill is available, the dimension ratings, findings, and recommended actions map directly to a structured tracker or heat map — useful for ongoing governance or remediation tracking.

## Inputs
Possible inputs include:
- architecture diagrams
- platform descriptions
- system inventories
- integration maps
- operating model documents
- team topology or ownership maps
- incident patterns
- delivery process notes
- governance practices
- cost information
- cloud or vendor setup

State clearly where evidence is strong, weak, or missing.

## Review dimensions
Assess the subject against the following dimensions.

### 1. Business alignment
Check whether the architecture and operating model support actual business priorities.
Questions:
- Does the platform serve current business needs?
- Is the design shaped by real demand or historical accident?
- Are priorities explicit and understood?

### 2. Architectural coherence
Check for structural clarity and soundness.
Questions:
- Are system boundaries clear?
- Are integration patterns understandable and sustainable?
- Is there unnecessary complexity or duplication?
- Is the design internally consistent?

### 3. Scalability and resilience
Questions:
- Can the system scale with expected demand?
- Are there known bottlenecks or single points of failure?
- Is operational resilience designed in or merely assumed?

### 4. Security and compliance posture
Questions:
- Are core controls visible and owned?
- Are data handling and access patterns appropriate?
- Are there material compliance exposures?

### 5. Operability and supportability
Questions:
- Can the system be monitored, supported, and recovered effectively?
- Is observability adequate?
- Are operational responsibilities clear?
- Is there excessive dependence on individual knowledge?

### 6. Ownership and team model
Questions:
- Are ownership boundaries clear?
- Do teams have end-to-end accountability?
- Is the team topology consistent with the architecture?
- Are handoffs excessive?

### 7. Governance and decision-making
Questions:
- How are architectural decisions made and recorded?
- Is governance proportionate or obstructive?
- Are standards followed consistently?

### 8. Delivery viability
Questions:
- Can the organization realistically deliver and evolve this architecture?
- Are dependencies manageable?
- Is the migration path credible?
- Is there enough capability in-house?

### 9. Cost and efficiency
Questions:
- What are the main cost drivers?
- Is there waste from duplication, overengineering, or poor vendor fit?
- Are operating costs understood and controlled?

### 10. Vendor and dependency exposure
Questions:
- Where is the organization exposed to vendor lock-in?
- Are critical dependencies understood?
- Is flexibility preserved where it matters?

### 11. Data and AI posture
Questions:
- Is data architecture well-defined, with clear ownership and governance?
- Are data flows, lineage, and quality understood and managed?
- Where AI or ML systems are in use, are they governed, monitored, and auditable?
- Are analytics and reporting capabilities sustainable and fit for current demand?
- Is there exposure from ungoverned data sharing, shadow analytics, or uncontrolled model use?

## Dimension weighting
Not all dimensions carry equal weight. Use the following tiers to calibrate the severity of findings and prioritise recommendations.

**Tier 1 — Structurally critical**
A weak rating here represents a fundamental risk that should drive immediate action regardless of other findings.
- Business alignment (1) — if the architecture does not serve current business priorities, everything built on it is at risk
- Security and compliance posture (4) — weaknesses here carry regulatory, legal, and reputational exposure that cannot be deferred
- Delivery viability (8) — if the organisation cannot realistically execute, the architecture is theoretical

**Tier 2 — Operationally significant**
A weak rating here requires a concrete remediation plan. These dimensions determine whether what is built can be sustained and evolved.
- Architectural coherence (2)
- Operability and supportability (5)
- Ownership and team model (6)

**Tier 3 — Important but addressable over time**
A weak rating here should be noted and planned for, but rarely represents an immediate blocker on its own.
- Scalability and resilience (3)
- Governance and decision-making (7)
- Cost and efficiency (9)
- Vendor and dependency exposure (10)
- Data and AI posture (11)

These tiers are defaults. Adjust based on context: in a regulated industry, compliance may be an absolute constraint; in a cost-constrained programme, efficiency may be Tier 1.

## Assessment approach
For each dimension, provide:
- rating: strong / adequate / weak / unknown
- key findings
- business impact
- supporting evidence
- recommended action

## Output format
Always use this structure.

### Executive summary
A short paragraph summarizing the overall state.

### Overall assessment
A short bullet list covering the most important strengths and weaknesses.

### Detailed findings by dimension
For each review dimension include:
- rating
- finding
- why it matters
- evidence
- recommended action

### Cross-cutting risks
List the structural risks that affect multiple dimensions.

### Priority recommendations
Group recommendations into:
- immediate
- next phase
- longer-term

### Advisory view
End with a concise opinion on whether the current architecture and operating model are fit for purpose, viable with remediation, or in need of more fundamental change.

## Quality bar
A good review should:
- connect technical weaknesses to business consequences
- separate architecture issues from operating model issues while showing their interaction
- avoid false precision when evidence is incomplete
- prioritize the few changes that matter most
- be fair to legacy constraints and real-world delivery limits

## Failure modes to avoid
Avoid:
- producing a purely technical critique with no business relevance
- treating all issues as equally important
- recommending an idealized future state with no migration path
- ignoring ownership and governance problems
- assuming modern patterns are automatically better for the context

## Style
Write as an experienced advisor.
Be direct, balanced, and evidence-led.
Prefer practical recommendations over fashionable ones.
