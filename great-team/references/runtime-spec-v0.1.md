# GreatTeam Runtime Spec v0.1

## 1. Overview

This file is a **runtime contract** for the `great-team` skill. It compresses and operationalizes `greatteam-protocol-v1.md` into a controller-friendly spec that is closer to a **small execution state machine** than a conceptual protocol.

Use this file when a controller, critic, composer, or downstream agent needs a **stable run contract** for one review cycle.

### Relationship to `greatteam-protocol-v1.md`
- `greatteam-protocol-v1.md` explains the philosophy, shared objects, and operating sequence.
- `runtime-spec-v0.1.md` fixes the **data contracts, state transitions, permissions, and completion rules** needed to run that sequence consistently.
- If the two files disagree, use this file for **runtime execution**, and use `greatteam-protocol-v1.md` for **intent and interpretation**.

### Scope
This spec is intentionally narrow:
- one project brief
- one review cycle
- one final decision memo
- small active team, usually **3-5 lenses**

> Product note: this is a **productized inference for GreatTeam**, not an official runtime spec from CAMEL, CrewAI, AutoGen, or any external framework.

---

## 2. Core data contracts

All runtime objects should be machine-readable enough for handoff, but lightweight enough to be written by a controller in plain Markdown or YAML.

### 2.1 `NorthStarCard`

**Purpose:** lock the reason for existence, non-negotiables, and outcome bar before team composition.

| Field | Type | Required | Rule |
|---|---|---:|---|
| `project_name` | string | yes | short human label |
| `project_type` | string | yes | e.g. game, product, feature, workflow |
| `why_this_should_exist` | string | yes | one sharp sentence |
| `target_user` | string | yes | specific enough to judge fit |
| `must_not_lose` | string[] | yes | 2-5 non-negotiables |
| `success_signal` | string[] | yes | observable success criteria |
| `failure_signal` | string[] | yes | observable failure criteria |
| `confidence_boundary` | string | no | where the runtime should stop claiming confidence |

```yaml
north_star_card:
  project_name:
  project_type:
  why_this_should_exist:
  target_user:
  must_not_lose: []
  success_signal: []
  failure_signal: []
  confidence_boundary:
```

### 2.2 `TaskCard`

**Purpose:** define one bounded unit of work.

| Field | Type | Required | Rule |
|---|---|---:|---|
| `task_id` | string | yes | stable within run |
| `state` | enum | yes | current state-machine state |
| `goal` | string | yes | one bounded objective |
| `inputs` | string[] | yes | links, notes, or brief components |
| `artifact_out` | string | yes | exact output artifact |
| `acceptance_test` | string[] | yes | must be checkable |
| `turn_budget` | integer | yes | max meaningful turns |
| `blocking_unknowns` | string[] | no | unresolved external evidence |
| `assigned_lenses` | string[] | no | chosen lenses for this task |
| `owner_role` | enum | no | Builder, Critic, or Integrator |

```yaml
task_card:
  task_id:
  state:
  goal:
  inputs: []
  artifact_out:
  acceptance_test: []
  turn_budget:
  blocking_unknowns: []
  assigned_lenses: []
  owner_role:
```

### 2.3 `DecisionLedger`

**Purpose:** shared memory for facts, decisions, and unresolved risks.

| Field | Type | Required | Rule |
|---|---|---:|---|
| `verified_facts` | string[] | yes | facts only; no speculation |
| `assumptions_in_play` | string[] | yes | temporary, not yet verified |
| `decisions_made` | string[] | yes | one line per decision |
| `open_issues` | string[] | yes | issue IDs only |
| `deferred_questions` | string[] | yes | pushed out of current run |
| `waivers` | string[] | no | waived checks with rationale |

```yaml
decision_ledger:
  verified_facts: []
  assumptions_in_play: []
  decisions_made: []
  open_issues: []
  deferred_questions: []
  waivers: []
```

### 2.4 `ArtifactBoard`

**Purpose:** track the review artifact and its status.

| Field | Type | Required | Rule |
|---|---|---:|---|
| `artifact_name` | string | yes | e.g. decision_memo |
| `artifact_type` | string | yes | memo, map, review, panel, etc. |
| `current_version` | string | yes | e.g. v0, v1 |
| `owner_role` | enum | yes | current editor |
| `status` | enum | yes | draft, under_review, blocked, accepted, escalated |
| `latest_changes` | string[] | yes | delta since prior version |
| `blocking_issue_ids` | string[] | yes | active blockers only |
| `final_location` | string | no | optional file/path reference |

```yaml
artifact_board:
  artifact_name:
  artifact_type:
  current_version:
  owner_role:
  status:
  latest_changes: []
  blocking_issue_ids: []
  final_location:
```

### 2.5 `Issue`

**Purpose:** convert disagreement into a bounded object.

| Field | Type | Required | Rule |
|---|---|---:|---|
| `issue_id` | string | yes | stable within run |
| `artifact_target` | string | yes | what is blocked |
| `severity` | enum | yes | blocker, major, minor |
| `tension_axis` | string | yes | the relevant tradeoff |
| `option_a` | string | yes | first viable path |
| `option_b` | string | yes | second viable path |
| `key_tradeoff` | string | yes | what choosing changes |
| `evidence_missing` | string[] | no | what is needed to resolve cleanly |
| `owner_role` | enum | yes | usually Critic until routed |
| `status` | enum | yes | open, resolved, escalated, deferred |

```yaml
issue:
  issue_id:
  artifact_target:
  severity:
  tension_axis:
  option_a:
  option_b:
  key_tradeoff:
  evidence_missing: []
  owner_role:
  status:
```

### 2.6 `TaskTrace`

**Purpose:** compact run log for handoff and audit.

| Field | Type | Required | Rule |
|---|---|---:|---|
| `task_id` | string | yes | same as `TaskCard.task_id` |
| `visited_states` | string[] | yes | in order |
| `active_lenses` | string[] | yes | lenses actually used |
| `key_tension` | string | yes | dominant tension in run |
| `decision` | string | yes | current or final decision |
| `unresolved_risks` | string[] | yes | non-closed risks |
| `next_action` | string | yes | next step or `none` |
| `escalation_target` | string | no | human, validation loop, research, etc. |

```yaml
task_trace:
  task_id:
  visited_states: []
  active_lenses: []
  key_tension:
  decision:
  unresolved_risks: []
  next_action:
  escalation_target:
```

---

## 3. State machine

### States

| State | Primary owner | Must produce | Exit condition |
|---|---|---|---|
| `intake` | Integrator | initial `NorthStarCard` + `TaskCard` | brief is bounded enough to evaluate |
| `map_tensions` | Builder | dominant tensions + missing context | at least 1 primary tension identified |
| `compose_team` | Integrator | lens selection + function mapping | active team is small and justified |
| `draft_review` | Builder | draft decision memo or review artifact | draft exists and matches `artifact_out` |
| `critic_pass` | Critic | blocker list / cuts / issue objects | all blockers converted into issues or cleared |
| `resolve_or_escalate` | Integrator | route, decision, waiver, or escalation | all open blockers resolved, waived, or escalated |
| `finalize_memo` | Integrator | final memo + updated ledger + task trace | completion checklist passes |

### Canonical transition path

```text
intake
  -> map_tensions
  -> compose_team
  -> draft_review
  -> critic_pass
  -> resolve_or_escalate
      -> draft_review        (if one bounded revision is justified)
      -> finalize_memo       (if blockers are cleared or waived)
      -> finalize_memo       (if escalated output is the correct end state)
```

### Transition rules

1. **`intake -> map_tensions`**
   - allowed only if `NorthStarCard` has: `why_this_should_exist`, `target_user`, `must_not_lose`
2. **`map_tensions -> compose_team`**
   - allowed only if at least one dominant tension is stated in operator language
3. **`compose_team -> draft_review`**
   - allowed only if lens count is bounded and each lens has a job in the run
4. **`draft_review -> critic_pass`**
   - allowed only if required artifact exists in draft form
5. **`critic_pass -> resolve_or_escalate`**
   - mandatory if any blocker, contradiction, or missing evidence is found
6. **`resolve_or_escalate -> draft_review`**
   - allowed once per task unless new evidence appears
7. **`resolve_or_escalate -> finalize_memo`**
   - allowed if blockers are closed, waived, or escalated with rationale

### Invalid transitions
- skipping `critic_pass`
- `Builder` moving directly to `finalize_memo`
- `Critic` reopening a resolved issue without new information
- looping `draft_review <-> critic_pass` more than once without escalation

---

## 4. Role permissions

### 4.1 Builder

**Can**
- propose tensions, candidate teams, draft memos, and revisions
- update `ArtifactBoard.latest_changes`
- add assumptions to `DecisionLedger.assumptions_in_play`
- recommend cuts, alternatives, and experiments

**Cannot**
- close blocker issues alone
- mark artifact `accepted`
- promote assumptions to `verified_facts`
- suppress an unresolved issue by omission

### 4.2 Critic

**Can**
- open `Issue` objects
- mark artifact `blocked`
- request evidence or narrower scope
- test artifact against `NorthStarCard` and `acceptance_test`
- recommend escalation or waiver with reason

**Cannot**
- become the final decider by default
- rewrite the entire artifact instead of critiquing it
- reopen a closed issue without new evidence or a changed north star
- generate repetitive objections that do not change the decision surface

### 4.3 Integrator

**Can**
- create and update `TaskCard.state`
- select active lenses and route turn ownership
- merge options, accept bounded waivers, or escalate
- mark artifact `accepted` or `escalated`
- finalize `DecisionLedger` and `TaskTrace`

**Cannot**
- invent evidence to force closure
- bypass `critic_pass` for convenience
- keep debate alive without a concrete delta to artifact or issue state
- silently drop a blocker without recording the rationale in the ledger

> Product note: these permissions are a **GreatTeam contract choice**, not a universal multi-agent rule.

---

## 5. Stop conditions, escalation conditions, anti-churn rules

### 5.1 Stop conditions

Stop the run when **all** are true:
- final artifact exists
- artifact status is `accepted` or `escalated`
- every blocker issue is `resolved`, `deferred`, or `escalated`
- `DecisionLedger` records decisions, open risks, and waivers if any
- `TaskTrace.next_action` is explicit or `none`

### 5.2 Escalation conditions

Escalate when **any** are true:
- required evidence is external and unavailable inside the run
- risk exceeds the stated confidence boundary
- one revision cycle completed and blocker still stands
- team disagreement is actually a product strategy decision the runtime cannot settle
- artifact quality depends on user validation not yet run

### 5.3 Anti-churn rules

- maximum **1** revision loop after first critic pass unless new evidence appears
- maximum **2** cycles per issue before escalation
- every turn must update an artifact, an issue, the ledger, or the trace
- duplicated critique must add new evidence, a sharper cut, or a new failure mode
- no new lenses after `compose_team` unless an escalation note justifies it
- if `turn_budget` is exhausted, Integrator must choose: finalize with caveat, or escalate

---

## 6. Minimal acceptance checklist

A run counts as complete only if the final output includes:

- `Project Essence`
- `Key Tensions`
- `Recommended Great Team`
- `Lens-to-Function Mapping`
- `Strongest Objections`
- `Next Decision` or `Next Experiment`
- `Confidence and Boundaries`

And the runtime objects are minimally coherent:
- `NorthStarCard` is complete enough to explain why the project exists
- `TaskCard.acceptance_test` is either passed or explicitly waived
- `DecisionLedger.open_issues` matches actual unresolved items
- `ArtifactBoard.status` matches reality
- `TaskTrace.visited_states` reflects the actual run path

---

## 7. Compact example run

### Input brief
A builder wants review on a narrative exploration game about a flooded museum at night.

### Runtime snapshot

```yaml
north_star_card:
  project_name: Flooded Museum
  project_type: game
  why_this_should_exist: Use a flooded museum to compress memory, preservation, and loss into one playable space.
  target_user: players who want a 20-45 minute atmospheric narrative experience
  must_not_lose:
    - emotional precision
    - authorial spatial identity
    - low puzzle friction
  success_signal:
    - players can describe the relationship wound
    - at least one object or spatial shift lingers in memory
  failure_signal:
    - players only mention atmosphere
    - players do not know what to do next

task_card:
  task_id: GT-001
  state: critic_pass
  goal: produce a pre-build decision memo
  inputs:
    - short concept brief
  artifact_out: decision memo
  acceptance_test:
    - identifies central tension
    - gives bounded next experiment
    - records strongest objection
  turn_budget: 6
  assigned_lenses:
    - poet
    - writer
    - artist
    - scientist
    - editor_critic
  owner_role: Critic

issue:
  issue_id: I-01
  artifact_target: decision memo
  severity: blocker
  tension_axis: poetic ambiguity vs narrative legibility
  option_a: preserve ambiguity with minimal explicit relationship detail
  option_b: anchor the relationship wound more concretely
  key_tradeoff: mystery versus emotional precision
  evidence_missing:
    - what players must understand by minute 10
  owner_role: Critic
  status: open
```

### Run summary
1. `intake`: Integrator creates the north star and first task.
2. `map_tensions`: Builder identifies the main tension as **poetry vs legibility**.
3. `compose_team`: Integrator selects poet, writer, artist, scientist, editor-critic.
4. `draft_review`: Builder writes the first memo.
5. `critic_pass`: Critic opens `I-01` because the relationship wound is too vague.
6. `resolve_or_escalate`: Integrator routes one bounded revision.
7. `finalize_memo`: revised memo adds a sharper wound, keeps ambiguity elsewhere, and recommends a 10-15 minute vertical slice.

Result: **accepted with one open risk logged for later user validation**.
