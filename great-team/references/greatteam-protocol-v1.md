# GreatTeam Protocol v1

## Purpose

Use this file when the skill needs to run a small **task-centric team** with clear routing, artifacts, and stopping rules.

This is the runtime reference for the skill. It is intentionally smaller than a general-purpose multi-agent framework.

## Borrowed signals vs productized rules

### Borrowed signals
- **From CAMEL / CrewAI / AutoGen**: task contracts, coordinator/selector patterns, critic loops, shared state, and explicit termination conditions.

### Productized rules for this skill
- Use **lenses + function slots**, not permanent job titles.
- Every turn must advance either an **artifact** or a **decision**.
- The runtime exists to create **high-quality disagreement that can converge**.

## Core function slots

| Slot | Main responsibility | Must produce | Common failure mode |
|---|---|---|---|
| **Builder / Explorer** | propose options, drafts, decompositions, alternative directions | candidate artifact or concrete proposal | generates volume without constraint |
| **Critic / Challenger** | test coherence, standards, evidence, fit to north star, risk | blocker list, cuts, missing evidence, counterexample | becomes performatively negative |
| **Integrator / Selector** | pick next speaker, merge tradeoffs, decide when to stop, escalate when needed | routing decision, synthesis, final path | over-centralizes thinking or ends too early |

> One runtime may have multiple active lenses, but each turn should still be tagged as Builder, Critic, or Integrator.

## Shared objects

### 1) NorthStarCard

```yaml
north_star_card:
  project_name:
  why_this_should_exist:
  target_user:
  must_not_lose:
  success_signal:
  failure_signal:
```

### 2) TaskCard

```yaml
task_card:
  task_id:
  goal:
  inputs: []
  artifact_out:
  acceptance_test: []
  turn_budget:
  blocking_unknowns: []
```

### 3) DecisionLedger

```yaml
decision_ledger:
  verified_facts: []
  decisions_made: []
  open_issues: []
  deferred_questions: []
```

### 4) ArtifactBoard

```yaml
artifact_board:
  artifact_name:
  current_version:
  owner:
  status: draft|under_review|blocked|accepted
  latest_changes: []
```

## Allowed turn types

Only use these turn types in the runtime:

| Turn type | Use when | Output shape |
|---|---|---|
| `propose` | introducing a draft, option, or decomposition | bullet proposal with assumptions |
| `challenge` | surfacing blockers, contradictions, missing evidence | blocker list, counterexample, risk |
| `synthesize` | merging or reframing competing ideas | merged path and tradeoff notes |
| `decide` | choosing a direction or stopping a branch | chosen path + rationale |
| `escalate` | handing off to human or to a validation loop | unresolved issue + reason |

Avoid free-form chat turns with no artifact or decision target.

## Standard operating sequence

1. **Initialize**
   - Create `NorthStarCard`
   - Create `DecisionLedger`
   - Define the first `TaskCard`

2. **Route**
   - `Integrator` selects the next active lens + function slot
   - Route based on:
     1. unresolved tension
     2. artifact most in need of progress
     3. capability fit

3. **Build**
   - `Builder` creates a draft tied to `artifact_out`

4. **Critique**
   - `Critic` reviews against:
     - `NorthStarCard`
     - `acceptance_test`
     - explicit risks / anti-patterns

5. **Revise or decide**
   - `Integrator` chooses one:
     - revise once
     - merge competing options
     - decide and close
     - escalate to validation or human

6. **Write back**
   - Update `ArtifactBoard`
   - Update `DecisionLedger`

## Conflict handling

Convert conflict into a structured `Issue`, not an open-ended debate.

```yaml
issue:
  issue_id:
  artifact_target:
  tension_axis:
  option_a:
  option_b:
  key_tradeoff:
  evidence_missing: []
```

### Conflict rule
1. Each side gets **one short memo**:
   - claim
   - supporting reason
   - likely downside
   - impact on north star
2. `Critic` compares both sides against the acceptance tests.
3. `Integrator` must choose exactly one:
   - pick A
   - pick B
   - merge into a bounded experiment
4. If still unresolved after **2 cycles**, escalate.

## Termination conditions

Terminate a task when **all** are true:
- the required artifact exists
- acceptance tests are satisfied or explicitly waived
- critic has no blocker remaining
- the ledger has recorded the decision and open risks

Terminate early and escalate when **any** are true:
- the conflict depends on external evidence not yet available
- stakes exceed the skill’s confidence boundary
- the team has looped twice with no new information

## Runtime guardrails

- Default to **small teams**: 3-5 active lenses.
- Default to **single-agent-first, critics-on-demand** when uncertainty is low.
- Do not run debate as the default communication mode.
- Do not let the `Integrator` write the whole solution unless the budget is exhausted.
- Do not store private scratch reasoning in shared state; only write verified facts, decisions, and open issues.

## Recommended minimal trace

For each task, keep a compact trace:

```yaml
task_trace:
  task_id:
  active_lenses: []
  key_tension:
  artifact_out:
  decision:
  unresolved_risks: []
  next_action:
```

This trace is the preferred handoff unit for the main skill.
