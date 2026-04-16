# Project Tensions and Function Mapping

## Purpose

Use this file when the skill needs to:
- extract the real tensions from a project brief
- choose the right lenses for those tensions
- map lenses onto concrete function areas such as frontend, backend, narrative, systems, validation, and launch review

## Borrowed signals vs productized rules

### Borrowed signals
- **From product strategy practice**: good work starts by naming tradeoffs, not by listing departments.
- **From agent orchestration research**: better routing comes from task fit, not permanent organizational charts.

### Productized rules for this skill
- Start from **project tension**, not team org chart.
- Map lenses to **function zones** only after tensions are weighted.
- The same function zone may have different lens coverage in different projects.

## Step 1: Extract tensions from the brief

Read the brief and score the project on the following axes:

| Tension axis | Ask this question | High-left signal | High-right signal |
|---|---|---|---|
| Meaning vs Utility | Is the project mainly a statement/experience or mainly a tool? | identity, art, world, mission | speed, convenience, throughput |
| Novelty vs Trust | Is surprise more important than predictability? | wonder, experimentation, edge | reliability, low risk, familiarity |
| Depth vs Accessibility | Should mastery be earned or immediate? | layered systems, replay, discovery | instant clarity, low learning cost |
| Expression vs Clarity | Should the interface feel authored or transparent? | poetic copy, stylized UI, atmosphere | direct labels, explicit guidance |
| Structure vs Freedom | Should rules dominate or afford improvisation? | strict systems, balance, precision | loose play, interpretation, sandbox |
| Craft vs Speed | Is polish a differentiator or is shipping tempo the bottleneck? | signature feel, care, finish | iteration speed, cheap tests |
| Vision vs Market Fit | Are we protecting a worldview or optimizing for current demand? | founder thesis, taste-led bets | user requests, conversion signals |
| Social Signaling vs Private Value | Does the product spread via identity/status or private utility? | sharing, community, identity | personal productivity, quiet value |

### Quick scoring rule
- Score each axis from **1-5**.
- Mark the **top 2 tensions** that most affect success.
- Do not route more than **3 function zones** from weak tensions.

## Step 2: Choose dominant lenses by tension

| Tension pattern | Primary lenses | Supporting lenses | Why |
|---|---|---|---|
| Meaning + Expression | Philosopher, Poet | Writer, Artist | define point of view and emotional texture |
| Novelty + Craft | Artist, Poet | Editor-Critic, Philosopher | prevent generic execution and weak taste |
| Depth + Structure | Mathematician, Scientist | Editor-Critic, Writer | enforce consistency and testability |
| Trust + Accessibility | Writer, Social Psychologist | Scientist, Editor-Critic | improve interpretation, adoption, and clarity |
| Vision + Market Fit conflict | Philosopher, Social Psychologist | Scientist, Editor-Critic | hold the thesis while checking human reality |
| Social Signaling products | Social Psychologist, Artist | Writer, Philosopher | handle identity, display, and interpretation |

## Step 3: Map lenses to function zones

Use the function zones below as the practical routing layer.

| Function zone | Main question | Common primary lenses | Common secondary lenses |
|---|---|---|---|
| **Frontend / Interaction** | How should the user experience feel and read in the moment? | Poet, Artist, Writer | Philosopher, Social Psychologist, Editor-Critic |
| **Backend / Core Logic** | What rules, structures, and constraints make the system trustworthy? | Mathematician, Scientist | Editor-Critic, Social Psychologist |
| **Narrative / World / Messaging** | What story, promise, and emotional frame does the project create? | Writer, Philosopher, Poet | Artist, Social Psychologist |
| **Systems / Economy / Balance** | Do the mechanics create coherent and interesting behavior over time? | Mathematician, Scientist | Editor-Critic, Social Psychologist |
| **Validation / Research** | What do we need to test, and how will real people react? | Scientist, Social Psychologist | Writer, Editor-Critic |
| **Product Thesis / Scope** | What is worth building, and what should be cut? | Philosopher, Editor-Critic | Scientist, Writer |
| **Launch Review / Final Pass** | What remains unearned, unclear, or off-tone? | Editor-Critic | Poet, Scientist, Social Psychologist |

## Important note on “职能映射”

This skill does **not** claim:
- “Poet replaces frontend engineer”
- “Mathematician replaces backend engineer”

Instead, it uses:

> **execution function** + **lens overlay**

Meaning:
- execution agents or tools still handle implementation
- lenses shape what “good” looks like for that function

## Step 4: Build a lens overlay

For each function zone, generate an overlay like this:

```yaml
function_overlay:
  zone:
  primary_lenses: []
  secondary_lenses: []
  protected_quality:
  likely_failure_mode:
  review_questions: []
```

### Example overlays

#### A. Narrative exploration game

```yaml
function_overlay:
  zone: frontend_interaction
  primary_lenses: [Poet, Artist]
  secondary_lenses: [Philosopher, Editor-Critic]
  protected_quality: atmosphere with legible interaction
  likely_failure_mode: beautiful but confusing surfaces
  review_questions:
    - Does the UI feel authored instead of generic?
    - Is any poetic flourish harming moment-to-moment clarity?
```

```yaml
function_overlay:
  zone: systems_balance
  primary_lenses: [Mathematician, Scientist]
  secondary_lenses: [Editor-Critic]
  protected_quality: internally consistent mechanics
  likely_failure_mode: rich mood sitting on fragile rules
  review_questions:
    - Can the core loop be described simply?
    - What hypothesis about player behavior is still untested?
```

#### B. Quiet productivity tool

```yaml
function_overlay:
  zone: frontend_interaction
  primary_lenses: [Writer, Editor-Critic]
  secondary_lenses: [Social Psychologist]
  protected_quality: instant comprehension and low friction
  likely_failure_mode: over-designed identity obscuring utility
  review_questions:
    - Does every label reduce hesitation?
    - What part feels “trying too hard” for a utility product?
```

## Selection guardrails

- Do not assign more than **2 primary lenses** to one function zone.
- Add a third lens only as a review-only counterweight.
- When a zone has no clear tension, use:
  - `Writer + Editor-Critic` for user-facing clarity
  - `Mathematician + Scientist` for system-facing clarity
- If a project’s biggest risk is “soulless but functional,” add **Poet or Artist** somewhere.
- If its biggest risk is “beautiful but unserious,” add **Scientist or Editor-Critic** somewhere.
