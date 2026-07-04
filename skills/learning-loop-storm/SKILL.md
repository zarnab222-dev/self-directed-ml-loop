---
name: learning-loop-storm
description: Run a full STORM research refresh on best practices for this user's AI-assisted mastery system, then synthesize or update the Learning Loop Contract. Use when the user explicitly asks for learning-loop STORM, a research-backed pedagogy refresh, a full audit of the teaching system, or when the Learning Stack Satisfaction Checkpoint has expired. Do not use for ordinary weekend alignment checks; use learning-stack-audit instead.
---

# Learning Loop STORM Refresh

Mechanism name: **Learning Loop Contract**.

Purpose: research how a human + AI tutor should run a long-term mastery curriculum, then translate the findings into an explicit teaching contract for the user's ML/robotics pivot. This is the heavyweight research refresh, not the normal weekend alignment audit.

For lightweight weekend or periodic alignment checks, use `learning-stack-audit`.

## Inputs

- Topic default: `Best practices for AI-assisted adult self-study systems that build deep, credential-equivalent technical mastery`
- Audience default: the user's PhD-equivalent applied ML / robotics curriculum
- Depth default: 5 perspectives

## Required context

Read before running the synthesis step:
- `~/brain/wiki/concepts/self-study-ml-engineering.md`
- `~/brain/wiki/concepts/ml-pivot-diagnostic.md`
- `~/brain/wiki/concepts/claude-as-learning-tool.md` (if present)
- `~/brain/wiki/concepts/learning-stack-satisfaction-checkpoint.md` (if present)
- `~/brain/wiki/synthesis/learning-queue.md`

If any of these don't exist yet, run the initial diagnostic first — see this repo's `START-HERE.md`.

## Research harness

Use the `storm` skill bundled alongside this one.

Run STORM with the default topic unless the user narrows it. The run must be citation-grounded and should include perspectives such as:
- cognitive science / learning science researcher
- expert technical educator
- AI tutoring / human-computer interaction researcher
- deliberate practice / assessment designer
- adult self-directed learning / motivation researcher
- optional: accessibility / neurodiversity / colorblind-friendly learning design

The report must answer:
- What reliably builds durable technical mastery?
- What role should an AI tutor play versus the learner?
- How should implementation, explanation, retrieval, spaced practice, projects, and feedback be sequenced?
- What failure modes should the tutor actively guard against?
- How should progress be tracked without turning into bureaucracy?
- How should an AI tutor explain *why* it chose a teaching move?

## Synthesis step

After the STORM report exists, read:
- `references/synthesis-prompt.md`
- the STORM `report.md`
- the STORM `sources.md`
- the required context pages above

Then produce a proposed Learning Loop Contract as a new or updated vault page. Prefer a concept page:
- `~/brain/wiki/concepts/learning-loop-contract.md`

The contract should define:
- assistant role
- user role
- teaching moves and when to use them
- accountability rules
- progress-tracking protocol
- evidence basis from the STORM report
- how the assistant should explain why it chose a teaching move

## Output

Return:
- path to the STORM report
- path to the Learning Loop Contract page
- 5-bullet summary of the contract
- any weak evidence or unresolved questions

Keep chat concise. The durable output belongs in the vault.
