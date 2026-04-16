# Validation Loop

## Purpose

Use this file when the skill needs to validate whether a proposed direction is:
- understandable
- attractive or repellent
- socially plausible
- still aligned with the project’s “greatness” standard

This file is for **validation architecture**, not runtime orchestration.

## Borrowed signals vs productized rules

### Borrowed signals
- **From TinyTroupe**: archetype panels, focus-group style feedback, brainstorming, structured comparison against real feedback.
- **From Stanford `genagents`**: interview-grounded agents, agent banks, memory/reflection for better individual fit.

### Productized rules for this skill
- Keep **descriptive user evidence** separate from **normative greatness critique**.
- In V1, prefer **archetype panels** over “fake precise users”.
- Introduce interview-grounded banks only in V2/V3, and only with clear governance.

## Hard separation: `USER_*` vs `GREAT_*`

| Type | What it represents | Primary job | Evidence source | Success metric |
|---|---|---|---|---|
| **`USER_*`** | real or archetypal users | tell us how this may be interpreted, adopted, rejected, or ignored | interviews, surveys, observed patterns, archetype assumptions | fidelity to user evidence or useful approximation |
| **`GREAT_*`** | normative excellence lenses | tell us whether the direction is worthy, coherent, alive, elegant, or diluted | curated lens schema, reference works, product philosophy | quality bar, novelty, coherence, anti-generic pressure |

### Non-negotiable rule
Never present `GREAT_*` output as if it were user research.  
Never let `USER_*` evidence automatically override the project’s north star without explicit discussion.

## V1 validation loop

### Recommended V1 stack
1. **Great Team runtime** produces a draft direction.
2. Run a **small archetype panel** of `USER_*` reviewers.
3. Run a final **`GREAT_*` critique pass**.
4. Produce a decision memo that shows both sides separately.

### Archetype panel guidance

Use **4-8 panelists**, not a huge swarm.  
Example archetype mix:
- curious novice
- skeptical power user
- status-sensitive sharer
- low-attention pragmatist
- emotionally motivated adopter
- trust-sensitive user

### Fixed V1 panel tasks

Ask the panel to answer fixed tasks, not free-form roleplay:
- What do you think this product/feature is for?
- What is the first thing that makes you suspicious or uninterested?
- What would make you try it once?
- What would make you share, pay, or come back?
- What feels confusing, corny, overdesigned, or too abstract?

## Suggested V1 scoring rubric

| Dimension | Asked of `USER_*`? | Asked of `GREAT_*`? | Notes |
|---|---|---|---|
| Comprehension | Yes | No | “Do people understand what this is?” |
| Initial interest | Yes | No | “Would they try it?” |
| Trust / friction | Yes | No | “What makes them hesitate?” |
| Social interpretation | Yes | Optional | especially important for sharing/community products |
| Meaning / integrity | No | Yes | “Does this stand for something real?” |
| Distinctiveness | Optional | Yes | “Does it feel generic?” |
| Craft coherence | No | Yes | “Does the whole hang together?” |

## Report format

Always split the report into two sections:

### 1) Observed User Fit
- what users may understand
- what they may resist
- where wording or flow fails
- what assumption seems fragile

### 2) Normative Greatness Critique
- what feels generic
- what lacks earned meaning
- what should be cut or intensified
- what should remain even if it is not the easiest thing to explain

## V2 / V3 path: interview-grounded bank

Move to interview-grounded agents only when all of the following are true:
- you already have a stable V1 panel loop
- you have real interviews or structured qualitative data
- you can define a consent/governance boundary
- you can evaluate held-out tasks

### Interview-grounded bank guidance
- Keep these agents under `USER_*`, not `GREAT_*`.
- Mark each with:
  - data source
  - interview date
  - coverage notes
  - confidence boundary
- Use them for:
  - response prediction
  - message testing
  - objection forecasting
- Do **not** use them as the project’s value compass.

## Governance notes

If the skill later supports interview-grounded banks:
- keep raw material separate from shareable summaries
- allow revocation or replacement of bad records
- record provenance for every agent profile
- do not claim exact behavioral prediction outside tested tasks

## Validation handoff block

Use this compact block for handoff:

```yaml
validation_block:
  panel_type: archetype|interview_grounded
  user_reviewers: []
  great_reviewers: []
  tasks_run: []
  strongest_user_objections: []
  strongest_greatness_objections: []
  recommendation: proceed|revise|retest|stop
```
