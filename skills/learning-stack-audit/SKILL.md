---
name: learning-stack-audit
description: Run a lightweight weekend or periodic alignment audit of the user's ML/robotics learning stack against the existing Learning Loop Contract and satisfaction checkpoint, without launching STORM research. Use when the user asks to audit the learning stack, do a weekend learning audit, check epistemic alignment with goals, verify they are grinding rather than optimizing process, or decide whether a process change is admissible.
---

# Learning Stack Audit

Mechanism name: **Learning Stack Audit**.

Purpose: check whether the current ML/robotics learning loop is still aligned with the user's goals, producing evidence, and resisting process-improvement procrastination. This is the lightweight counterpart to `learning-loop-storm`.

## Scope

This skill is for **alignment checks**, not research refreshes.

Do:
- inspect the current learning state;
- compare it to the existing contract and checkpoint;
- identify drift, weak evidence, or repeated failure modes;
- decide whether any process change is admissible;
- return one next learning brick.

Do not:
- run STORM;
- browse the web by default;
- rewrite the Learning Loop Contract;
- create a new learning framework;
- expand tooling unless it passes the process-change admission test.

Use `learning-loop-storm` only when the user explicitly wants a full STORM research refresh or the checkpoint has expired.

## Read first

Read these before auditing:
- `~/brain/wiki/concepts/learning-loop-contract.md`
- `~/brain/wiki/concepts/learning-stack-satisfaction-checkpoint.md`
- `~/brain/wiki/concepts/self-study-ml-engineering.md`
- `~/brain/wiki/concepts/ml-pivot-diagnostic.md`
- `~/brain/wiki/synthesis/learning-queue.md`

If present, inspect:
- `~/ml-proof-packets/retrieval.md` — the delayed-retrieval ledger
- `~/ml-proof-packets/progress.md`
- `~/ml-proof-packets/README.md`
- the current notebook, repo, or artifact the user names

## Audit protocol

1. **Orient**: identify current phase, artifact, last brick, and next recorded brick.
2. **Evidence check**: name what evidence was produced since the last audit: code, explain-back, transfer check, delayed recall, artifact cleanup, proof-packet progress, or nothing. Then compute three countable metrics from git (these are what make "repeated failure across three sessions" observable at all):
   - learning sessions this week: distinct commit-time clusters in `ml-proof-packets`;
   - meta:doing commit ratio: vault commits touching learning-stack pages/skills vs `ml-proof-packets` commits, same window — target meta:doing ≤ 1:2, ratio above 1:1 is drift evidence;
   - overdue `open` rows in `retrieval.md`, and completed retrieval checks since last audit.
3. **Alignment check**: compare the work to the target: PhD-equivalent applied ML / robotics competence with public evidence.
4. **Scope check**: decide whether robotics/domain context is sharpening the current transferable mechanism or becoming a prerequisite tunnel.
5. **Anti-procrastination check**: decide whether recent activity is learning-core work, artifact work, retrieval review, process/tooling drift, or domain-scope drift.
6. **Retention check**: read `retrieval.md` and see whether delayed recall is scheduled or overdue. If overdue, make that the next brick unless another learning-core blocker is more urgent. If the ledger is missing or stale (concepts passed with no row), that is itself a repeated-failure finding — the mechanism has decayed back into prose.
7. **Process-change admission test**: allow a process change only if it is a current-brick unblocker, repeated-failure fix, exit-gate proof-packet polish, or tool/accessibility/budget necessity.
8. **Decision**: choose one of:
   - **Aligned — grind**: keep going with the next brick.
   - **Aligned — retrieve**: do delayed recall before moving on.
   - **Minor drift — correct**: park/stop a process tangent and return to learning.
   - **Repeated failure — adjust**: make one small process change and define the evidence that will show it worked.
   - **Checkpoint expired — run STORM refresh**: only when the checkpoint's expiration conditions are met.
9. **Next brick**: give exactly one atomic action.

## Process-change admission test

A proposed process improvement is admissible only if it passes at least one gate:

- **Current-brick unblocker**: it removes friction blocking today's brick.
- **Repeated-failure fix**: the same failure appeared across at least three learning sessions.
- **Exit-gate polish**: a concept cluster passed its learning gate and needs proof-packet distillation.
- **Tool/accessibility/budget necessity**: something is broken, inaccessible, visually ambiguous, too expensive, or incompatible with the locked workflow.

If none apply, say: **park it and do the next brick**.

Scope boundaries are different from process changes. They are allowed when they preserve the stable stack by preventing drift. Treat any secondary domain interest (robotics, a specific application area, etc.) the same way: keep it as a depth spine and motivating context, but do not expand into its full prerequisite stack unless that unlocks the current proof packet or a clear role-market signal.

## Output format

Keep the audit short.

Use:

**Audit Verdict**
Aligned — grind / Aligned — retrieve / Minor drift — correct / Repeated failure — adjust / Checkpoint expired — run STORM refresh.

**Evidence**
2-4 bullets grounded in the progress log or artifact.

**Drift Check**
One paragraph naming whether process work is helping or becoming avoidance.

**Process Changes**
Allowed / Not allowed, with the admission-test reason.

**Next Brick**
Exactly one action, small enough to start immediately.

**Weekend Note**
One sentence saying what to check next weekend.

## Guardrails

- Do not reward planning as progress unless it produced learning evidence.
- Do not suggest a full research refresh unless the checkpoint has expired.
- Do not add new trackers, dashboards, or rubrics unless the admission test passes.
- Do not treat a scope correction as permission to redesign the stack.
- Do not let a secondary domain interest crowd out transferable ML foundations.
- Do not count passive intake as mastery.
- Do not count AI output as learning unless the user can defend the mechanism.
- Prefer delayed recall and artifact defense over process redesign.
- Keep the tone warm, direct, and a little strict.
