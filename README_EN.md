# Great Team

[![Release](https://img.shields.io/github/v/release/Feianxc/great-team)](https://github.com/Feianxc/great-team/releases)
[![License](https://img.shields.io/badge/license-MIT-black.svg)](./LICENSE)
[![Stars](https://img.shields.io/github/stars/Feianxc/great-team?style=social)](https://github.com/Feianxc/great-team)

[中文](./README.md) | **English**

**Great Team** is a pre-build judgment skill.  
It does not give you more brainstorming. It gives you a harder answer: **what this project really is, what should be cut from V1, and what should be tested before you waste time building the wrong version.**

![Great Team cover](./docs/assets/great-team-cover.svg)

## The problem it solves

What is expensive now is no longer:

- writing code
- making prototypes
- generating screens
- wiring workflows

What is expensive now is judgment:

- what this idea actually is
- what the first real wedge is
- what should not be built yet
- which risk will distort the project first
- what the smallest useful next experiment is

The real problem for many builders today is not:

> “I cannot build this.”

It is:

> **“I can build this too fast, so I can also build the wrong version too fast.”**

## When to use Great Team

Use `Great Team` when you already have execution power, but you keep running into problems like:

- the idea is attractive, but V1 keeps expanding
- the PRD looks complete, but the wedge still feels soft
- all the advice sounds reasonable, but none of it forces a decision
- what you need is not more ideation, but a clear cut
- you do not want to spend weeks building a version that is directionally wrong

## What it gives you

Feed it a product idea, PRD, feature draft, game concept, agent workflow, or strategy draft, and `Great Team` returns a structured **decision memo**:

1. Project Essence
2. Key Tensions
3. Recommended Great Team
4. Lens-to-Function Mapping
5. Strongest Objections
6. Decision
7. Next Experiment / Next Decision
8. Confidence and Boundaries

Its goal is not to sound smarter.

Its goal is:

> **to change what you build next.**

## How it differs from a normal AI critique

| Normal critique | Great Team |
|---|---|
| gives you more suggestions | forces fewer, harder decisions |
| tends to expand the space | compresses the scope first |
| often becomes generic | looks for the project’s specific tension |
| often says “you could try this” | more often says “do not start with this” |
| stays at commentary level | lands on cuts and next experiments |

## Core method

`Great Team` works in four moves:

1. identify the project’s central tensions
2. choose the right “great lenses”
3. map those lenses to the functions under review
4. converge on a decision-dense memo

These “great lenses” are not roleplay personas. They are judgment systems, such as:

- Philosopher
- Writer
- Scientist
- Editor-Critic
- Social Psychologist
- Poet
- Artist

## Minimal example

The problem with many ideas is not a lack of originality.  
It is that **V1 tries to do too much**.

`Great Team` is designed to force a judgment like:

> Do not start with the full system. Start with the first believable wedge.  
> Do not start with the platform. Start with the smallest workflow that changes a real decision.

This is what the output shape looks like:

![Great Team memo preview](./docs/assets/great-team-memo-preview.svg)

## Who it is for

- AI-native solo builders
- small founding teams
- product-minded engineers
- founder-designers
- creative technologists

They usually share one trait:

> **execution is no longer the bottleneck; judgment is.**

## What it is not

`Great Team` is not:

- a celebrity imitation engine
- multi-agent theater
- a general-purpose agent platform
- a fake company simulator
- an execution tool that builds the whole project for you

It does one thing:

> **help you make a better decision before you start building.**

## Quick start

If you open this repository in Codex, `.codex/config.toml` already points the skill to a relative path, so you can invoke it directly.

Use it like this:

```text
Use $great-team to review this idea before we build:
what is the real wedge,
what should we cut,
and what should we test first?
```

## Repository structure

```text
.
├── .codex/
│   ├── agents/
│   └── config.toml
├── docs/assets/
├── great-team/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   ├── assets/
│   ├── references/
│   ├── evals/
│   └── product/
└── README_EN.md
```

## Validation status

The repository already includes an internal mini eval batch comparing `great-team` against a normal baseline critique across 5 briefs.

The most stable signal so far is not that `great-team` “sounds better.”  
It is that it more reliably:

- finds the central tension
- makes a harder cut
- shrinks the next experiment
- prevents wasted build effort

See:

- [Great Team Product PRD V1](./great-team/product/great-team-product-prd-v1.md)
- [Mini Eval Batch 01](./great-team/evals/mini-eval-batch-01.md)

## Roadmap

The near-term goal is not to make the system bigger.  
It is to make the value harder and more repeatable:

- **v0.1**: skill + decision memo + internal validation
- **v0.2**: blind scoring + more real briefs
- **v0.3**: lighter product shell
- **later**: `USER_*` validation panel, memo history, stronger runtime

## License

MIT
