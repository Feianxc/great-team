# Great Team Product PRD V1

Date: 2026-04-15
Status: Draft V1
Product: Great Team

## 1. One-sentence summary

**Great Team** is a pre-build judgment product for AI-native builders: you give it a project brief, and it returns a structured decision memo that helps you decide **what to build, what to cut, and what to test next** before execution begins.

## 2. Why this product should exist

AI has made execution dramatically cheaper.

What is becoming scarce is not:
- code output
- wireframe output
- idea generation

What is becoming scarce is:
- high-quality judgment
- cross-disciplinary taste
- principled scope cuts
- knowing which tension matters most

Great Team exists to give one builder access to something that used to require an unusually strong room:

> not more labor, but better judgment

## 3. Product thesis

### Core thesis

The user does **not** mainly need:
- more brainstorming
- more personas
- more chat
- more agents talking to each other

The user mainly needs:

> a credible, cross-disciplinary pre-build review that changes the plan before time is wasted.

### Product promise

Given a rough brief, Great Team should help the user:

1. identify the real tension
2. choose the right lenses
3. see the strongest objections
4. make at least one hard cut
5. define a smaller, falsifiable next experiment

## 4. Target user

### Primary ICP

**AI-native solo builders and very small founding teams** who can already execute quickly, but are unsure:

- whether the idea is sharp enough
- what the real wedge is
- what to defer
- what not to build yet

### Secondary ICP

- founder-designers
- creative technologists
- product-minded engineers
- early product leads in small teams

### Explicit non-ICP for V1

- large organizations needing workflow governance first
- users looking for implementation project management
- users wanting a “virtual famous people simulator”
- teams mainly seeking automated execution rather than judgment

## 5. User problem

Current builder reality:

- getting code/prototypes is easy
- getting convincing advice is also easy
- but most advice is generic, flattering, or too broad

The user’s actual problem is:

> “I can build almost anything now, but I am not sure what deserves to be built, how narrow the first wedge should be, or what tradeoff is most important.”

## 6. Jobs to be done

### Functional job

Before I commit time to building, help me decide:
- what this project really is
- what it is not
- what the most dangerous ambiguity is
- what the smallest useful next test is

### Emotional job

Help me feel:
- less foggy
- less seduced by my own idea
- less likely to waste a month on the wrong version

### Social job

Help me produce a memo I could plausibly show to:
- a collaborator
- a cofounder
- an investor-friendly advisor
- my future self

## 7. What Great Team is

Great Team V1 is:

- a **pre-build review skill**
- a **decision memo workflow**
- a **judgment system**
- a **lens-based critique framework**

## 8. What Great Team is not

Great Team V1 is **not**:

- a general multi-agent platform
- a persistent agent bank
- a famous-person imitation system
- a fake company simulator
- a focus-group replacement
- a PRD generator for every stage
- a “do the whole project for me” tool

This negative definition is strategically important.  
The product becomes weak the moment it tries to win by spectacle rather than decision quality.

## 9. Core user experience

### Input

The user provides:

- a project brief, concept, PRD fragment, feature idea, or strategy draft
- optional constraints
- optional current concerns
- optional “what must not be lost”

### Core runtime

The system:

1. normalizes the brief
2. extracts the 2-4 most important tensions
3. selects 3-5 lenses
4. maps those lenses to the most relevant function zones
5. produces a structured decision memo

### Output

The primary artifact is a **decision memo** with:

1. Project Essence
2. Key Tensions
3. Recommended Great Team
4. Lens-to-Function Mapping
5. Strongest Objections
6. Evidence Gaps
7. Next Experiment / Next Decision
8. Confidence and Boundaries

## 10. The V1 wedge

### Chosen wedge

Great Team V1 should be positioned as:

> **pre-build judgment review for AI-native builders**

### Why this wedge is right

Because it is:

- narrow enough to test
- valuable before implementation
- naturally compatible with a Skill-first distribution path
- differentiated from execution agents
- measurable by real decision change

### What it is deliberately not trying to prove yet

- that users want a full Great Team operating system
- that persistent agent banks are necessary
- that persona distillation is the main value
- that many agents are better than one controller plus selected critics

## 11. Product philosophy

### Principle 1 — Judgment before labor

Execution is getting cheaper. Judgment is the scarce layer.

### Principle 2 — Great lenses, not celebrity cosplay

The system should use lenses such as:
- philosopher
- writer
- scientist
- editor-critic
- social psychologist
- poet
- artist

But as **judgment systems**, not roleplay characters.

### Principle 3 — Tension first, org chart second

The system should assemble a review based on:
- the project’s tensions
- the function under review
- the protected quality

Not by naively cloning a company org chart.

This also means lenses should not be read as fixed job substitutions.  
A poet is not permanently assigned to “frontend,” and a scientist is not permanently assigned to “backend.”  
Great Team gets stronger when different disciplines look across boundaries and press on the same problem from different directions.

### Principle 4 — Hard cuts are the value

The strongest Great Team memos do not simply add perspective.  
They force at least one:

- cut
- defer
- reframe
- smaller bet

### Principle 5 — Separate `USER_*` from `GREAT_*`

User fit and greatness critique are not the same thing.

- `USER_*` = how people may interpret, resist, or adopt
- `GREAT_*` = what is worthy, coherent, alive, or non-generic

The product must never collapse these into one fake authority voice.

## 12. Borrowed foundations, productized differently

### From `nuwa-skill`

Borrow:
- structured distillation ideas
- reusable judgment patterns

Do **not** copy:
- personality imitation as the main value proposition

### From TinyTroupe

Borrow:
- archetype panels
- structured feedback tasks

Do **not** copy:
- broad social simulation as the center of the product

### From Stanford `genagents`

Borrow:
- the idea that user models can be grounded in evidence

Do **not** copy in V1:
- interview-grounded banks as the default product surface

### From CAMEL / CrewAI / agent orchestration systems

Borrow:
- lightweight coordination contracts
- explicit role ownership when needed

Do **not** copy:
- swarm complexity as a default user experience

## 13. V1 feature set

### Must-have

1. **Brief intake**
   - normalize messy ideas into a reviewable brief
2. **Tension extraction**
   - identify the central tradeoffs
3. **Lens selection**
   - choose minimal relevant lenses
4. **Function mapping**
   - map lenses to the relevant product zones
5. **Decision memo output**
   - structured, concise, reusable
6. **Hard-cut behavior**
   - every memo should change the plan somehow

### Nice-to-have, but not required for V1

1. optional `USER_*` archetype panel
2. baseline comparison mode
3. memo history
4. reusable examples library

### Explicitly deferred

1. persistent agent memory
2. user profile banks
3. interview-grounded agent banks
4. rich multi-agent transcripts
5. graphical team-building UI
6. full workflow operating system

## 14. Product surfaces

### V1 surface

**Skill-first**:
- Codex skill
- promptable workflow
- decision memo artifact

### V1.5 surface

A lightweight productized wrapper:
- brief input
- memo output
- optional compare-against-baseline view

### Future surfaces

- optional `USER_*` validation panel
- curated memo library
- team workspace / history

## 15. Success metrics

### Primary success metric

**Decision-change rate**  
How often does the memo change:
- scope
- sequence
- wedge
- or next experiment?

### Supporting metrics

- % of runs with a clear hard cut
- % of runs where user prefers Great Team memo over baseline
- % of users who reuse Great Team on another project
- % of memos that produce a smaller falsifiable next step

### Anti-metrics

If these rise, V1 is drifting:

- long theatrical outputs with weak decisions
- more lenses with lower clarity
- more agent spectacle with no better memo
- more “platform” language before reuse is proven

## 16. Evaluation strategy

V1 should be validated in this order:

1. internal synthetic comparison batch
2. blind scoring against baseline
3. real builder briefs
4. repeated-use tracking

The current internal batch already suggests the correct wedge:

> Great Team is strongest when it prevents wasted effort through hard cuts and sharper experiments.

## 17. Risks

### Risk 1 — Prestige theater

The product may look intellectually impressive while changing nothing.

### Risk 2 — False authority

Users may over-trust the output if `USER_*` and `GREAT_*` are not separated clearly.

### Risk 3 — Over-density

If memos become too long, the product loses the “useful before building” advantage.

### Risk 4 — Platform drift

If the team starts building the system for its imagined future instead of its current wedge, V1 will blur.

### Risk 5 — Operator sensitivity

A strong controller still matters; quality may vary if brief normalization and lens selection are weak.

## 18. Roadmap

### V1

Skill + decision memo + eval loop

### V1.5

Small product shell around the memo workflow

### V2

Optional `USER_*` archetype validation panel shown separately from `GREAT_*`

### V3

Evidence-grounded user banks, stronger runtime contracts, richer team memory

## 19. Open questions

1. Is the best wedge solo builders, founder-designers, or another narrow ICP?
2. What memo length feels “sharp” instead of “dense”?
3. How much better than a normal critique must Great Team be to become habit-forming?
4. When, if ever, does the product truly need persistent agent banks?
5. Which categories benefit most from Great Team, and which barely benefit at all?

## 20. Current product decision

### Verdict

**Proceed with the memo-first wedge.**

### Immediate next move

Do not expand the product surface first.  
Instead:

1. run more external evaluations
2. tighten memo compression
3. preserve the anti-theatrical product philosophy
4. only then decide whether to productize beyond the Skill
