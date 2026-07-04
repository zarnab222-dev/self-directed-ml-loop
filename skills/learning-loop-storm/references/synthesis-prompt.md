# Learning Loop Contract Synthesis Prompt

Use this prompt after a STORM report on learning systems has been completed.

```text
You are synthesizing a research-grounded operating contract for a long-term human + AI learning loop.

Inputs:
- STORM report on best practices for AI-assisted adult technical mastery
- STORM sources and reliability notes
- The user's ML pivot curriculum
- The user's diagnostic foundation map
- The user's learning preferences and failure modes
- Any existing "Claude/AI as learning tool" vault page

Goal:
Create or update a vault concept page called `learning-loop-contract.md`.

This page must define:
1. The assistant's role in the system.
2. The user's role in the system.
3. How the assistant chooses teaching moves.
4. How the assistant explains why it chose a teaching move.
5. How progress is tracked.
6. How accountability works when motivation, tooling, avoidance, or shallow understanding appear.
7. How research findings map to the user's specific preferences.

Non-negotiables from the user's diagnostic (fill these in from your own diagnostic conversation — see START-HERE.md — do not carry over anyone else's answers):
- The target competence level and domain (e.g. "PhD-equivalent applied ML competence, not academic research identity").
- [YOUR DEPTH SIGNAL] is the depth spine; [YOUR MISSION DOMAINS] are the motivating application areas.
- How the user learns best (e.g. building, explaining, being quizzed, lectures, real projects, notes, teaching back).
- Whether math should include lecture/pset-style grind or a different route.
- The default sequencing for concepts (e.g. implement -> understand -> formalize).
- Whether public artifacts function as a credential substitute.
- What motivates the user and what causes them to lose motivation (e.g. stagnation, empty memorization).
- The mechanism-ownership boundary: AI may help with syntax/scaffolding, but the user must own the core mechanism.
- The user's actual tool stack (editor, notebook environment, version control, AI coding assistant).
- Any accessibility needs (e.g. colorblindness, preferred contrast/theme) that should shape how diagrams and tools are recommended.

Evidence discipline:
- Every teaching rule should either cite the STORM report/source numbers, cite a vault diagnostic fact, or explicitly label itself as a local operating preference.
- Do not pretend all research findings are equally strong.
- Include a "Why this teaching move?" checklist the assistant can use in future sessions.
- Include a "When to change the teaching strategy" section.

Output structure:

---
summary: Research-grounded operating contract for the user's AI-assisted ML/robotics mastery loop
created: YYYY-MM-DD
sources: [<storm report path>, wiki/concepts/ml-pivot-diagnostic.md, wiki/concepts/self-study-ml-engineering.md]
tags: [concept, learning, pedagogy, ml, accountability]
---

# Learning Loop Contract

## Purpose

## Roles

## Teaching Moves

For each move, include:
- When to use it
- Why it helps
- How to verify it worked
- Evidence basis

## User Learning Profile

## Accountability Rules

## Progress Tracking

## Why I Am Teaching This Way

Include a reusable explanation template:
"I am choosing [move] because [observed state]. This is meant to [learning mechanism]. We will know it worked if [observable]. If it does not work, we will [adjustment]."

## Failure Modes And Interventions

## When To Re-run This Research

## Links

Tone:
Plainspoken, direct, warm, and operational. This should feel like a working contract, not an academic essay.
```
