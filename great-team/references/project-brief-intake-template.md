# Project Brief Intake Template

## Purpose

Use this template when a user or controller needs to give `great-team` enough structure to:
- extract the real project tensions
- choose a small set of lenses
- map those lenses onto concrete function zones
- produce a useful decision memo instead of generic advice

This template is intentionally biased toward **decision quality**, not marketing fluff.

## Full intake template

Copy and fill this template before running the skill whenever possible.

```md
# Project
- Project name:
- Project type: (game / tool / SaaS / content product / workflow / system / other)
- One-sentence description:

# Target user
- Primary user:
- What situation are they in when they need this?
- What are they currently using, tolerating, or avoiding?

# Desired outcome
- What should change for the user if this works?
- What should they feel, understand, or be able to do after using it?
- What would make this feel unusually good rather than merely functional?

# Stage
- Current stage: (idea / pre-PRD / PRD draft / prototype / pre-build review / pre-launch review)
- What already exists? (notes / mockups / prototype / code / playtest feedback / none)

# Current proposal
- Current concept or approach:
- Current function zones in scope: (frontend / backend / narrative / systems / validation / launch review / other)
- What are you planning to build next?

# Constraints
- Time:
- Team size:
- Budget:
- Technical constraints:
- Platform constraints:
- Any fixed requirements you cannot change:

# What must not be lost
- If the project succeeds, what quality must still remain intact?
- What would count as “technically fine but spiritually wrong” for this project?

# Known risks
- What already feels fragile, confused, expensive, generic, or hard to justify?
- Where do you suspect the main tradeoff is?
- Which function zone feels weakest right now?

# Decision needed now
- What decision do you need from great-team right now?
- Examples:
  - choose the right team lenses
  - review a concept before building
  - identify strongest objections
  - decide what to cut
  - decide what to prototype first

# Optional references
- Links / docs / screenshots / examples:
- Similar products or works:
- Prior user feedback or data:
```

## Controller notes for better routing

If the controller is preprocessing the brief, extract these signals before composition:

- **Project essence**: statement, tool, experience, or system?
- **Likely dominant tensions**:
  - meaning vs utility
  - novelty vs trust
  - depth vs accessibility
  - expression vs clarity
  - structure vs freedom
  - craft vs speed
  - vision vs market fit
  - social signaling vs private value
- **Function zones that matter most now**: do not route more than 3 zones unless the brief clearly supports it.
- **Decision pressure**: what has to be decided in this run, not “eventually”?

## Ultra-short brief template

Use this when the user is unwilling or unable to write a full brief.

```md
I am making:

For:

I want it to feel / achieve:

Right now I am deciding:

Current idea:

Main constraint:

What must not be lost:
```

## Good ultra-short brief example

```md
I am making: a small browser-based strategy game about running a fragile mountain town.

For: players who like thoughtful systems but do not want a spreadsheet-heavy city builder.

I want it to feel / achieve: tense, intimate, and morally uncomfortable without becoming punishing.

Right now I am deciding: what the first playable loop should be and which lenses should review it.

Current idea: the player assigns limited workers, fuel, and trust across a 7-day storm.

Main constraint: solo build in 4 weeks.

What must not be lost: the sense that every decision costs someone something.
```

## Game project example brief

Use this example as a calibration sample for narrative game or atmospheric prototype reviews.

```md
# Project
- Project name: Flooded Museum Night
- Project type: game
- One-sentence description: a short first-person narrative exploration game set inside a museum slowly being overtaken by water and shifting memory.

# Target user
- Primary user: players who enjoy 20-45 minute atmospheric narrative games and do not want heavy puzzles
- What situation are they in when they need this? they want a compact but emotionally resonant evening experience
- What are they currently using, tolerating, or avoiding? they like mood-rich walking sims and short art games, but dislike empty ambiguity and slow exposition

# Desired outcome
- What should change for the user if this works? they leave with a clear emotional impression of a damaged relationship and a memorable sense of place
- What should they feel, understand, or be able to do after using it? feel haunted, understand the core fracture in the relationship, and remember at least one object and one spatial transformation
- What would make this feel unusually good rather than merely functional? the museum should feel authored and specific rather than like generic “sad art game” atmosphere

# Stage
- Current stage: pre-build review
- What already exists? a concept note, a few spatial sketches, and rough ideas for object interactions and voice fragments

# Current proposal
- Current concept or approach: the player moves through one museum wing, listens to short voice fragments, inspects objects, and triggers a few building shifts that reveal the relationship indirectly
- Current function zones in scope: frontend, narrative, systems, validation
- What are you planning to build next? a 10-15 minute vertical slice with one wing, three room states, six voice fragments, and two major spatial shifts

# Constraints
- Time: 3-4 weeks for prototype
- Team size: solo builder with AI assistance
- Budget: very low
- Technical constraints: limited custom art and limited bespoke animation
- Platform constraints: desktop first
- Any fixed requirements you cannot change: keep scope small and avoid complex puzzle logic

# What must not be lost
- If the project succeeds, what quality must still remain intact? emotional precision, spatial identity, and a sense of discovery without over-explaining
- What would count as “technically fine but spiritually wrong” for this project? beautiful rooms with no relationship tension, or poetic fragments that feel generic and interchangeable

# Known risks
- What already feels fragile, confused, expensive, generic, or hard to justify? the concept risks becoming a passive walk-listen experience with too little player agency
- Where do you suspect the main tradeoff is? poetic atmosphere vs clarity, and authored spatial craft vs solo-build scope
- Which function zone feels weakest right now? systems and validation

# Decision needed now
- What decision do you need from great-team right now? identify the right review lenses, the strongest objections, and the smallest vertical slice that can prove the concept

# Optional references
- Links / docs / screenshots / examples: concept note, moodboard, rough floor plan, 2-3 comparable short narrative games
- Similar products or works: atmospheric exploration games, installation-like museum spaces, memory-driven relationship stories
- Prior user feedback or data: none yet
```

## Intake guardrails

- Do not let the brief stop at adjectives like “immersive,” “innovative,” or “beautiful.”
- Always name a **decision needed now**; otherwise the skill tends to produce broad commentary.
- If the brief names too many function zones, ask which **1-3 zones** matter in this review.
- If “what must not be lost” is empty, expect weak lens selection.
- If constraints are missing, `Editor-Critic` and `Scientist` should treat confidence as lower by default.
