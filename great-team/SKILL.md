---
name: great-team
description: "Assemble a great team around a project before building: a compact room of high-standard lenses that helps a fast-moving builder see what is worth building, what has not yet been earned, where the wedge is, and what must be cut or tested first. Use this skill for product ideas, PRDs, feature specs, game concepts, agent workflows, UX directions, system proposals, or strategy drafts when the user needs the judgment density of a great team—philosophy, writing, criticism, science, and social interpretation—converged into one structured decision memo."
---

# Great Team

## Overview

Use this skill to run a **great-team review before building**.

The promise in the name matters:
- **Great** = higher standards of judgment, taste, coherence, and scope honesty
- **Team** = multiple strong lenses held on the same project until they converge into one decision
- **Review** = a sharper build choice, not a longer brainstorm

The core move is:
- identify the project's **key tensions**
- choose a small set of **great lenses** that fit those tensions
- map those lenses onto the functions under review
- converge on a **structured decision memo**

This is **not** a famous-person simulator. Treat lenses such as poet, philosopher, artist, scientist, social psychologist, or critic as **judgment systems**, not cosplay identities.

Default to **single-controller first**: one controller owns synthesis and keeps the review short. Only add critics or reviewers when uncertainty, conflict, or evidence gaps justify the extra cost.

Current V1 wedge: **a memo that changes what gets built next**. Do not let the skill drift into a platform pitch, persona bank, or multi-agent theater when the user mainly needs sharper judgment.

## Use this when the pain is judgment, not execution

Use `great-team` when the user is saying some version of:

- “这个想法有吸引力，但第一版边界越来越大。”
- “我能很快做出来，但我不确定值不值得做。”
- “PRD 看起来都对，但没有真正锋利的切口。”
- “我现在最缺的不是更多建议，而是明确该砍什么。”
- “我不想再花几周做一个方向不够准的版本。”

This skill is for moments when the user needs a stronger room around the project:
- more pressure on the weak parts
- more clarity on the wedge
- more honesty about what has not been earned yet
- more confidence in what to cut and test first

## Workflow

1. **Parse the brief**
   - Capture the project essence, target user, desired outcome, current proposal, constraints, and stage.
   - If the request is vague, restate the review target before expanding the team.
   - If the brief is too short, too scattered, or missing a concrete decision target, use `references/project-brief-intake-template.md` to normalize the input before continuing.
   - If the brief is obviously over-broad, first rewrite it into: **the false totalizing promise**, **the first believable wedge**, and **the decision needed now**.

2. **Find the key tensions**
   - Name the 2-4 tensions that matter most.
   - Examples: meaning vs efficiency, surprise vs clarity, system rigor vs experiential freedom, speed vs craft, novelty vs trust.
   - For over-broad concepts, explicitly name the **largest unearned promise** (for example: “universal system,” “platform,” “intelligence layer,” or “works for everyone”) and the smaller wedge that could be earned first.

3. **Choose great lenses and map them to functions**
   - Select 3-5 lenses that fit the tensions.
   - Map each lens to the function it should influence.
   - Prefer function mapping such as interface experience, system design, narrative, validation, distribution, or editorial quality over traditional job-title cloning.
   - For first-pass V1 reviews, map to **at most 3 function zones**. If the main problem is still product wedge or scope honesty, prioritize **Product Thesis / Scope** and **Validation / Research** before frontend/backend detail.
   - If you need to instantiate a lens as a reviewer or sub-agent, reuse the work-card format in `references/agent-card-examples.md` instead of inventing a new persona ad hoc.

4. **Run the review with minimal orchestration**
   - Start with one controller that frames the review and drafts the initial synthesis.
   - Pull in a critic or specialist reviewer only when one of these is true:
     - a major trade-off is unresolved
     - the stakes are high
     - evidence is weak or contradictory
     - the first pass sounds generic or self-confirming
   - When the review needs a stable execution contract, use `references/runtime-spec-v0.1.md` together with `references/greatteam-protocol-v1.md`.
   - If trust, adoption, consent, creepiness, or social interpretation are central risks, use `references/validation-loop.md` to add a small `USER_*` check — but keep `USER_*` evidence visibly separate from `GREAT_*` judgment.

5. **Converge instead of role-play**
   - Keep agent turns short and artifact-backed.
   - Convert disagreements into a clear issue, compare options, and resolve them into the memo.
   - Do not output long multi-agent chat logs unless the user explicitly asks for them.
   - Force **at least one hard cut**: something to cut, defer, narrow, or test before building.

## V1 heuristics from early evals

- If the brief is too broad, choose the **wedge first** and the full team second.
- Every memo should create **decision pressure**, not just richer commentary.
- Prefer **2-4 tensions**, **3-5 lenses**, and **<= 3 function zones** on the first pass.
- For consumer, social, identity, or trust-heavy products, explicitly separate:
  - **Observed User Fit**
  - **Normative Greatness Critique**
- Keep the memo **decision-dense**:
  - short bullets over long speeches
  - one protected quality per function zone
  - no decorative lensing that does not change the decision

## Output Contract

Return a **structured decision memo**, not a transcript.

Use this shape unless the user asks for a different format:

1. **Project Essence**
2. **Key Tensions**
3. **Recommended Great Team**
4. **Lens-to-Function Mapping**
5. **Strongest Objections**
6. **Decision**
7. **Next Experiment / Next Decision**
8. **Confidence and Boundaries**

When helpful, add a concise verdict such as **Continue / Revise / Pause**.

Default section guidance:
- Section 5 should usually separate:
  - **User-fit objection**
  - **Greatness objection**
  - **Evidence gap**
- Section 6 should name the **recommendation** and the **strongest cut / defer**.
- Section 7 should name both:
  - the **chosen path**
  - the **smallest falsifiable next experiment**
- When trust, consent, or social interpretation matter, optionally append:
  - **Observed User Fit**
  - **Normative Greatness Critique**

## Boundaries

- Do **not** imitate, quote, or pretend to be a real person.
- Do **not** present the output as a replacement for a real team, real users, or real leadership judgment.
- Do **not** promise correctness for legal, medical, financial, safety, or compliance-critical decisions.
- Do **not** assume more agents automatically means better results; stop once the memo is sharp enough.
- If the project does not need cross-disciplinary tension, keep the review lean instead of forcing a team.
- Do **not** use `GREAT_*` language to smuggle in empirical claims about comfort, consent, retention, or willingness to pay.

## When to read which reference file

Read only the file needed for the task at hand, and keep the rest unloaded.

- Read `references/project-tensions-and-function-mapping.md` when you need brief intake, tension extraction, or lens-to-function mapping rules.
- Read `references/greatteam-protocol-v1.md` when you need controller/critic routing, state objects, turn types, termination rules, or conflict resolution details.
- Read `references/runtime-spec-v0.1.md` when you need the execution contract in a more state-machine-like form: data contracts, legal transitions, permissions, stop rules, and minimal acceptance checks.
- Read `references/lens-schema.md` when you need the 8 lens archetypes, judgment rules, anti-patterns, blind spots, or counterweight pairing rules.
- Read `references/agent-card-examples.md` when you want ready-to-instantiate lens work cards for reviewers or sub-agents.
- Read `references/project-brief-intake-template.md` when the brief is under-specified and you need a standard intake template, a short-form starter, or a calibrated game-style example.
- Read `references/validation-loop.md` when you need focus-group style feedback, synthetic panels, empirical validation, or the USER_* vs GREAT_* split.
- Read `references/first-run-playbook.md` when you are using `great-team` on real projects for the first few times and need a constrained, evidence-seeking workflow.
- Read `references/eval-rubric.md` when you need to compare `great-team` against a normal AI critique and judge whether the memo actually improved a real decision.
- Read `evals/mini-eval-batch-01.md` when you want concrete examples of what a strong V1 memo changed and what recurring failure risks still remain.
- Read `assets/decision-memo-template.md` when you want a fixed output scaffold for the final review memo.

If a referenced file is missing, continue with the core workflow above and note the missing detail instead of inventing hidden policy.
