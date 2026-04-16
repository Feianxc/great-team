# Great Team Mini Eval Batch 01

Date: 2026-04-15
Reviewer: main controller synthesis
Scope: compare `great-team` against a plain baseline AI critique on 5 project briefs

## 1. Goal

Test the current V1 thesis:

> `great-team` is worth continuing if it produces decision memos that change build decisions more than a normal AI critique.

This batch focuses on the questions in `great-team/references/eval-rubric.md`:
- does the memo identify the real tension?
- does it force a concrete cut, defer, or bet?
- does it produce a smaller, falsifiable next experiment?
- does it stay honest about evidence gaps?

## 2. Method

- **Mode A:** run the brief through the current `great-team` philosophy:
  - tension-first
  - 3-5 lens selection
  - lens-to-function mapping
  - structured decision memo
- **Mode B:** plain baseline AI critique
- **Scoring:** compressed 6-dimension version of the eval rubric
  - Tension Sharpness
  - Non-Generic Insight
  - Decision Pressure
  - Testability
  - Boundary Honesty
  - Memo Clarity

### Method notes

- All 5 cases were produced with the current Great Team agent set and then synthesized here.
- Cases 4-5 were initially drafted locally and then cross-checked by dedicated mini-eval workers before this report was finalized.
- This is **not** blinded and the briefs are partly synthetic.
- So this batch is useful for **internal V1 direction**, not for market-proof claims.

## 3. Batch scoreboard

| Case | Brief | Mode A | Mode B | Clearer cut from Mode A |
|---|---|---:|---:|---|
| 1 | Narrative exploration game | 4.8 / 5 | 3.0 / 5 | Cut to a 15-minute vertical slice; no real water simulation; no systemic architectural transformation |
| 2 | Calm AI idea resurfacing tool | 4.8 / 5 | 2.8 / 5 | Do **not** start with explicit gamification; build a gentle resurfacing companion |
| 3 | Remote team weekly update SaaS | 4.8 / 5 | 2.8 / 5 | Do **not** build a generic AI weekly-report SaaS; focus on blocker intelligence + report draft |
| 4 | Voice-based social memory map app | 4.8 / 5 | 2.8 / 5 | Do **not** start with passive social graph intelligence; build a private pre-reconnection memory companion |
| 5 | Universal personalized learning system | 4.8 / 5 | 2.7 / 5 | Do **not** start with a universal learning OS; pick one source type, one learner moment, one mastery loop |

### Average

- **Mode A average:** `4.80 / 5`
- **Mode B average:** `2.82 / 5`
- **Observed lift:** `+1.96`

## 4. Case-by-case findings

## Case 1 — Narrative exploration game

### Brief
A solo-developer narrative exploration game set in a flooded museum at night, using voice fragments, object interactions, and subtle architectural shifts to reveal a lost relationship.

### Why Mode A was better

Mode A did not just praise the atmosphere. It identified the real production and design tension:

- poetic ambiguity vs emotional readability
- atmosphere craft vs solo-build scope
- subtle spatial change vs player comprehension

Then it forced a **hard scope cut**:

- only one relationship wound
- only one spatial reveal grammar
- only one short vertical slice
- no real water tech ambition
- no large systemic transformation layer

### Most valuable decision lift

Mode A changed the next move from:

> “make a beautiful prototype and test it”

to:

> “build 3 rooms / 6 voice fragments / 8 interactables and validate whether players can actually reconstruct the relationship.”

That is exactly the kind of wasted-effort prevention this skill is supposed to create.

## Case 2 — Calm AI idea resurfacing tool

### Brief
A product for people with too many ideas who capture thoughts constantly but rarely revisit them. The founder considered adding light gamification to increase re-engagement.

### Why Mode A was better

Mode A found the central product tension quickly:

- calm sanctuary vs game-like progression
- frictionless capture vs meaningful resurfacing
- private value vs productivity signaling

The critical cut was:

> **Do not begin with explicit gamification.**

Mode A reframed the product from “an idea capture system with retention mechanics” into:

> a **gentle resurfacing companion**

That shift matters because it changes what the product is optimizing for:

- not more capture
- not more organization
- but low-shame rediscovery

### Most valuable decision lift

The next experiment became a 7-day concierge MVP with one resurfaced idea per day, one reason-it-matters-now sentence, and one lightweight prompt.

That is much sharper than “add capture, summarize, and A/B test gamification.”

## Case 3 — Remote team weekly update SaaS

### Brief
A SaaS that aggregates Slack, Jira, and docs to generate weekly remote-team updates and status reports.

### Why Mode A was better

Mode A refused the obvious “AI summarizer” framing and instead named the real issue:

- trust vs novelty
- report polish vs managerial usefulness
- fragmented signals vs adoption friction

The strongest reframe was:

> this should not be a generic AI status-report product  
> it should be **async blocker intelligence + report draft**

That transformed the product from a crowded category feature into a narrower management tool with clearer value.

### Most valuable decision lift

The memo changed the question from:

> “can we automate weekly reports?”

to:

> “can we surface stalled threads, missing updates, and silent owners early enough to change a management decision?”

That is a much better test of product worth.

## Case 4 — Voice-based social memory map app

### Brief
A mobile app where users record short voice memories about people, organize them into a dynamic social map, and get contextual reminders before reconnecting with someone.

### Mode A decision change

Mode A surfaced a tension that a generic critique would likely blur:

- care vs creepiness
- memory support vs social manipulation
- private reflection vs relationship CRM
- low-friction capture vs consent and interpretation risk

The decisive cut was:

> **Do not start with passive “relationship intelligence.”**

Instead, V1 should be framed as:

> a **private pre-reconnection memory companion** for people who genuinely care but forget details

### What Mode A protected

It protected the moral shape of the product:

- no omniscient social graph fantasy
- no weak-tie sprawl in V1
- no automatic chat ingestion as the default
- no relationship scoring
- no “better networking” language that cheapens the emotional use case

### Best next experiment

Run a 14-day concierge pilot with 10-12 users focused only on people they already care about:

1. after a call or meeting, the user records a 20-60 second voice reflection
2. before the next interaction, the system returns:
   - 3 remembered specifics
   - 1 unresolved thread
   - 1 gentle re-entry prompt

**Acceptance signal:** users report that the prep card makes them more present, not more performative; a majority say they would not feel ashamed if the other person knew they had used it.  
**Failure signal:** users describe it as manipulative, invasive, or too much overhead.

### Why Mode A beat Mode B

Mode B would likely stay at the level of:

- privacy concerns
- market differentiation
- UX simplicity

Mode A was better because it made an existential product choice:

> is this a care-support tool, or a social optimization machine?

That is a Great Team style question.

## Case 5 — Universal personalized learning system

### Brief
An AI learning tool that ingests PDFs, transcripts, webpages, videos, and podcasts to generate personalized syllabi, quizzes, flashcards, projects, spaced repetition, and progress tracking for students and self-learners.

### Mode A decision change

Mode A identified the real problem immediately:

- curriculum generation vs curriculum mastery
- universal ingestion vs pedagogical sharpness
- convenience automation vs real learning transfer
- content transformation vs behavior change
- broad audience ambition vs a believable first wedge

The strongest cut was:

> **Do not build a universal personalized learning system in V1.**

Instead, the more honest wedge is:

> one source type + one learner moment + one mastery loop

The strongest version of that cut in the worker cross-check was:

> choose **students with a real course/exam deadline**, and serve only **PDF + lecture transcript** first

Example wedge:

> turn one dense PDF or transcript into a 5-day retrieval-first mastery sprint with one applied output

### What Mode A protected

It protected the product from becoming a feature buffet:

- multimodal ingestion everywhere
- syllabus generation
- daily pathing
- quizzes
- flashcards
- projects
- memory review
- progress tracking

The memo forced the team to ask:

> what is the smallest loop that causes real learning rather than the feeling of learning?

### Best next experiment

Choose one source type and one user segment, then compare:

- **baseline:** summary + flashcards
- **Mode A wedge:** retrieval-first 5-day mastery sprint with one applied task

In the sharper worker version, the test is even narrower:

- 8-10 students
- 1 course
- 1 week before an exam
- inputs limited to lecture transcript + slides / PDF

Then check:

- 48-hour recall
- completion rate
- whether the user would choose this again over a normal summarizer

### Why Mode A beat Mode B

Mode B would usually say:

- narrow your ICP
- pick a first feature set
- test demand

Mode A was better because it converted “too broad” into a precise design principle:

> do not measure success by how much content the system can transform  
> measure success by whether one small loop reliably improves recall and application

## 5. Recurring wins for Great Team

Across all 5 cases, Mode A repeatedly did five things better than baseline:

### 1) It found the real tension faster

Not “there are risks,” but:

- calm vs gamification
- poetic mood vs readable relationship
- summarization vs blocker discovery
- care vs creepiness
- universal ingestion vs actual mastery

That is the strongest repeated signal in this batch.

### 2) It forced a hard cut

In every strong case, the memo contained a decisive “do not start with X”:

- no water simulation
- no explicit gamification
- no generic AI weekly-report SaaS
- no passive relationship intelligence layer
- no universal learning OS

This appears to be the main mechanism by which `great-team` creates value.

### 3) It reduced the next experiment

Mode A consistently turned broad ambition into smaller falsifiable tests:

- 15-minute vertical slice
- 7-day concierge resurfacing
- 2-week blocker brief
- 2-week reconnection memory test
- 5-day mastery sprint

This is exactly aligned with the V1 purpose of preventing wasted build effort.

### 4) It made the product thesis more legible

Mode A repeatedly converted a category-level idea into a sharper thesis:

- “walking sim” -> one relationship wound through space
- “idea capture tool” -> gentle resurfacing companion
- “AI weekly reports” -> blocker intelligence
- “social map” -> private reconnection memory aid
- “learning system” -> one mastery loop

### 5) It stayed more honest about boundaries

Mode A more often marked:

- what is inferred from the brief
- what is not user research
- what remains unverified
- which ambitions should be deliberately deferred

That boundary honesty is essential because this skill is normative, not empirical.

## 6. Recurring concerns and failure risks

The batch is strong, but there are still real concerns.

### 1) Output density can drift upward

The best memos are sharper than baseline, but they are also denser. If left unchecked, V1 could become “high-quality but too long.” A later refinement may need stronger memo compression guidance.

### 2) The skill is still operator-sensitive

A strong controller still matters. Bad brief normalization or decorative lens selection could weaken the result quickly.

### 3) Consumer-social briefs need extra `USER_*` discipline

In socially sensitive products, the gap between:

- what is normatively admirable
- what users will actually tolerate

becomes sharper. The `USER_*` vs `GREAT_*` separation should remain visible in future live tests.

### 4) This is still internal evidence

These runs show promising decision lift, but they do **not** yet prove:

- real repeated use
- real willingness to pay
- blind preference under external scoring
- robustness across much noisier briefs

## 7. Decision after batch

### Verdict

**Continue.**

The batch supports the current V1 positioning:

> Great Team should remain a **pre-build judgment review skill** that outputs a decision memo.

It should **not** expand yet into:

- agent bank platform
- persistent persona system
- multi-agent theater product
- broad company simulation layer

### Why continue

Because the strongest evidence in this batch is not that the memos sound better.  
It is that they repeatedly:

- cut scope
- change the project thesis
- improve next experiments
- and likely prevent wasted work

That is the correct wedge.

## 8. Recommended next moves

1. **Run 5-10 more cases**
   - include uglier, lower-quality, more ambiguous briefs
   - include at least 2 briefs that do **not** benefit much from Great Team, to test restraint

2. **Add blind external scoring**
   - compare memo preference without revealing which mode produced which output

3. **Run live project trials**
   - use real founder or builder briefs
   - track whether the memo changed an actual decision within a week

4. **Only then decide whether to revise the skill body**
   - current evidence suggests the core workflow is working
   - so the next bottleneck is validation quality, not more conceptual expansion

## 9. Bonus note: internal product fit

A separate self-review of Great Team itself reached the same directional conclusion:

> V1 should stay narrow, memo-first, and anti-theatrical.

That internal consistency is encouraging, but it should not replace external validation.
