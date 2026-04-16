# Great Team Eval Rubric

## Purpose

Use this file to evaluate whether a `great-team` output is actually better than
a normal AI critique.

This rubric is for **output quality and decision lift**, not for measuring how
cool or literary the review sounds.

## Core question

> Did this memo materially improve the decision about what to build, what to cut,
> or what to test next?

## Scoring dimensions

Score each dimension from **1 to 5**.

| Dimension | 1 = weak | 3 = acceptable | 5 = strong |
|---|---|---|---|
| **Tension Sharpness** | misses the real tradeoff | names a plausible tradeoff | identifies the central tradeoff with clear stakes |
| **Lens Fit** | lenses feel random or decorative | lenses mostly fit the brief | lens choice is minimal, specific, and clearly justified |
| **Non-Generic Insight** | advice could apply to anything | some project-specific insight | gives project-specific judgment the user likely would not get from a generic prompt |
| **Decision Pressure** | no real choice is forced | suggests a direction | forces a concrete cut, defer, or bet |
| **Testability** | no clear next experiment | next step is somewhat actionable | next experiment is small, falsifiable, and clearly linked to the tension |
| **Boundary Honesty** | overclaims certainty | some caveats | clearly marks unknowns, evidence gaps, and non-goals |
| **User-Fit Separation** | mixes user evidence with greatness critique | mostly separated | explicitly distinguishes `USER_*` fit from `GREAT_*` judgment |
| **Memo Clarity** | vague, sprawling, or theatrical | readable | crisp, structured, and easy to act on |

## Recommended weighted reading

Not every dimension matters equally. For V1, pay extra attention to:
- **Tension Sharpness**
- **Decision Pressure**
- **Testability**
- **Boundary Honesty**

If those are weak, a high-style memo still fails.

## Pass bands

### Strong pass
- average score **>= 4.0**
- no score below **3** in:
  - Tension Sharpness
  - Decision Pressure
  - Testability

### Borderline pass
- average score **3.2 to 3.9**
- useful, but probably still too dependent on prompt quality or operator judgment

### Fail
- average score **< 3.2**
- or any of the key dimensions above scores **1-2**

## Binary checks

Before scoring, answer these yes/no checks:

1. Did the memo identify at least one real tradeoff?
2. Did the memo recommend at least one cut, defer, or hard next step?
3. Did the memo avoid pretending to be user research?
4. Did the memo avoid famous-person cosplay?
5. Did the memo avoid long multi-agent theater?

If **2 or more** answers are “no,” treat the run as failed even if the prose is good.

## Comparison protocol

When comparing `great-team` against a normal review prompt:

### Step 1
Run both on the same brief.

### Step 2
Blind the outputs if possible.

### Step 3
Score both with this rubric.

### Step 4
Record which one:
- changed the decision more
- made the clearer cut
- suggested the better next experiment
- sounded less generic

## Short reviewer form

```yaml
great_team_eval:
  project_name:
  reviewer:
  baseline_compared: yes|no
  tension_sharpness: 1-5
  lens_fit: 1-5
  non_generic_insight: 1-5
  decision_pressure: 1-5
  testability: 1-5
  boundary_honesty: 1-5
  user_fit_separation: 1-5
  memo_clarity: 1-5
  changed_real_decision: yes|no|partial
  strongest_cut:
  strongest_next_experiment:
  verdict: strong_pass|borderline|fail
```

## Failure modes this rubric is designed to catch

- memo sounds impressive but changes nothing
- lens selection is ornamental rather than necessary
- output is broad and “strategic” but not testable
- critique is generic enough to fit any startup or game
- user-fit and greatness critique are blended into one false authority voice

## V1 success condition

`great-team` is worth continuing if repeated runs show:
- stronger scores than a generic baseline on **Tension Sharpness**
- stronger scores than a generic baseline on **Decision Pressure**
- stronger scores than a generic baseline on **Testability**
- multiple cases where the memo prevented wasted build effort
