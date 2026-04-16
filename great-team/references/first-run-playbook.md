# Great Team First-Run Playbook

## Purpose

Use this file the first few times you run `great-team` on a real project.

This playbook is not the product itself. It is a practical guide for getting
high-signal outputs while the skill is still proving its wedge.

## When to use this playbook

Use it when:
- the project is still pre-build or pre-PRD
- the brief is fuzzy, over-broad, or emotionally loaded
- you want to compare `great-team` against a normal AI critique
- you are collecting early evidence that the memo changes real decisions

Do **not** use it as a substitute for implementation planning, usability testing,
or high-stakes expert review.

## First-run objective

For early runs, the goal is:

> produce a memo that changes at least one real decision about scope, priority,
> tradeoffs, or the next experiment.

If the run only feels “interesting,” count it as weak.

## Recommended first-run sequence

### Step 1: Normalize the brief

If the user gives a vague or emotionally charged idea:
- restate the project in one sentence
- identify the **decision needed now**
- identify what must not be lost
- identify the biggest current risk

If needed, use `project-brief-intake-template.md`.

### Step 2: Limit the scope of the review

For early runs, constrain the review:
- choose **2-4 key tensions**
- choose **3-5 lenses**
- map to **at most 3 function zones**
- if the brief is too broad, define the **first believable wedge** before mapping the rest

Avoid broad “review everything” passes.

### Step 3: Produce the core memo

Always produce these sections:
1. Project Essence
2. Key Tensions
3. Recommended Great Team
4. Lens-to-Function Mapping
5. Strongest Objections
6. Decision
7. Next Experiment / Next Decision
8. Confidence and Boundaries

Use `assets/decision-memo-template.md` if helpful.

### Step 3.5: Keep the memo compact

- Prefer **1-3 bullets per section** unless the project genuinely needs more.
- If a paragraph adds flavor but no decision pressure, cut it.
- The goal is not “sound profound”; the goal is “change the next build decision.”

### Step 4: Force one hard cut

Every early memo should contain **at least one** of:
- something to cut
- something to defer
- something to test before building
- something that is not yet earned

If the memo contains no hard cut, it is probably too soft.

When possible, express the cut in a sentence like:

> do **not** start with X; start with Y

### Step 5: Capture the outcome

After the run, log:
- Did the memo change a real decision?
- What was the strongest objection?
- What was cut or deferred?
- What next experiment was chosen?
- Would the user use this again?
- For socially sensitive products, what felt **creepy, shaming, manipulative, or too intimate**?

## Recommended comparison baseline

To test whether `great-team` is real, compare it against a plain baseline:

### Baseline A
“Review this idea and tell me risks, opportunities, and next steps.”

### Baseline B
A normal PRD critique or product review prompt.

### Compare on:
- Did one output identify a sharper tension?
- Did one output make a clearer cut?
- Did one output suggest a more testable next experiment?
- Did one output sound less generic?

## Early-run pass / fail guide

### Strong run
- identifies a tension the user had not named
- makes a cut the user agrees is painful but right
- proposes a small, testable next move
- changes what gets built next

### Weak run
- repeats the brief in smarter words
- adds lots of opinions but no decision pressure
- chooses too many lenses
- sounds theatrical instead of useful

## Anti-patterns on first runs

- treating lens variety as value by itself
- mapping every function zone just because the schema allows it
- using `Poet` / `Artist` too early when the actual need is scope clarity
- pretending `GREAT_*` outputs are user truth
- producing a long transcript instead of a hard memo
- using “platform,” “intelligence layer,” or “universal system” language before the wedge is earned

## Minimum first-run evidence block

```yaml
first_run_evidence:
  project_name:
  decision_needed_now:
  key_tensions: []
  lenses_used: []
  function_zones_used: []
  strongest_cut:
  strongest_objection:
  next_experiment:
  decision_changed: yes|no|partial
  user_reuse_signal: high|medium|low
```

## Suggested first 10-run program

Run `great-team` on:
1. one game concept
2. one AI tool concept
3. one SaaS/productivity concept
4. one creator or media concept
5. one weird/ambitious thesis-driven concept
6. one clearly bad or over-broad idea
7. one idea already partially implemented
8. one idea with clear user demand
9. one idea with unclear user demand
10. your own `Great Team` concept

This gives enough variety to see whether the skill generalizes or just flatters.
