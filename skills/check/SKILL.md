---
name: check
description: Inspect the user's current ML/robotics learning artifact and decide whether the current brick counts. Use when the user says "check", asks whether their notebook/code/progress is correct, wants a review of a learning step, or needs the next correction without AI assistance taking over the learning-core mechanism.
---

# Check

Mechanism name: **Check**.

Purpose: verify the work just done in the PhD-equivalent applied ML curriculum. This is the counterpart to `next-brick`: `next-brick` chooses the action; `check` decides whether the action actually counts.

## Read first

When checking curriculum work, read:
- `~/brain/wiki/concepts/self-study-ml-engineering.md`
- `~/brain/wiki/concepts/ml-pivot-diagnostic.md`
- `~/brain/wiki/concepts/learning-loop-contract.md`
- `~/brain/wiki/concepts/external-verification-registry.md` — if the user reports back from an external resource, this is the map of what's expected per phase

If the user names a repo or artifact, inspect it directly. Default current repo:
- `~/ml-proof-packets`

## Check protocol

1. Inspect the relevant file(s), not just the user's description.
2. Identify what changed since the last check when possible.
3. Judge against the current brick's definition of done.
4. Separate:
   - **learning-core mechanism**: concept the user must own;
   - **scaffolding/friction**: plotting, syntax, file layout, cleanup.
5. Classify remaining work as one of:
   - **learning-core**: understanding is still changing;
   - **artifact cleanup**: understanding has passed, but the notebook/repo needs clearer future-facing structure;
   - **scaffold defect**: the prompt, blank, or task shape is too vague and is blocking the user;
   - **tooling friction**: environment/editor/notebook mechanics are blocking the user.
   - **domain bridge**: the user needs compact prerequisite/domain context before the prompt is answerable.
6. If AI/autocomplete filled code, decide whether it touched:
   - **safe assistance**: syntax, boilerplate, plotting, repeated prior mechanisms, or non-target mechanics;
   - **learning-core substitution**: the current mechanism being learned.
7. If autocomplete filled the learning-core mechanism, the brick does not count until the user reconstructs, edits, or cold-defends it.
8. If there is a conceptual error, explain the smallest correction and ask for an explain-back.
9. Use probes that test real understanding: transfer to a new example, edge cases, mechanism, assumptions, failure modes, or contrast with a nearby concept.
9b. If the learning-core answer is computable (coordinates, matrix entries, numeric outputs, shapes), require an executable check: the user writes their predicted value into an `assert`/`np.allclose` cell **before** running it. A failing assert is Not Yet regardless of how good the prose reads. Run the relevant cells or ask the user to run them and show output — never grade a computable answer by prose inspection alone.
9c. If the concept has a mapped resource in `external-verification-registry.md`, prompt for it once the internal brick passes — do not treat internal-only as the final word for conceptual material. When the user reports back an external result (deep-ml pass, LeetCode solve, pset score, Kaggle leaderboard rank, mock-interview verdict), log it verbatim to the artifact repo's `retrieval.md` under "External verification log" and treat it as ground truth, not as one more prose input to weigh. **If it contradicts an earlier self-graded Pass, say so plainly and flag it as a repeated-failure candidate — do not smooth it over or re-interpret the external result to make it agree.** This is the check on `check` itself.
10. If the user passes only an easy or boundary-case probe, escalate once before counting the concept as understood.
11. If the user passes a meaningful transfer/edge/contrast probe, mark the concept as understood and stop drilling wording minutiae as learning.
12. If the user's intent is to validate or tune a draft learning-core answer, trigger this rule semantically, not by exact wording. This includes "closer?", "is this closer?", "better?", "does this count?", "is this right?", "am I getting it?", "how's this?", screenshots of draft answers, or any similar request for quick validation:
   - respond with `Pass`, `Partial`, or `Not Yet`;
   - name the smallest missing mechanism in diagnostic form;
   - provide a fill-in scaffold, contrast case, or question prompt;
   - do **not** provide a polished replacement sentence, final wording, completed formula, or completed code for the learning-core answer.
   If the answer is close enough to pass, say it passes and ask for a brief cold defense rather than rewriting it for them.
13. If the first notebook answer misses the mechanism, prefer Q/A repair before repeated notebook edits. Use dialogue to expose the misconception, connect old/new concepts, and test understanding; then ask for one repaired notebook answer.
14. If Q/A materially changes understanding, add or ask for a compressed notebook insight block, not a transcript. Capture the durable bridge: shared invariant, analogy limits, and how it applies here.
15. If cleanup remains, label it as artifact cleanup. Preserve useful original mistakes as audit trail and add correction/why beside them rather than silently erasing them.
16. If the scaffold is vague, fix the scaffold shape before asking the user to continue. A good scaffold states answer type, local context, blank semantics, ownership boundary, and any needed no-scroll context.
17. If the user lacks prerequisite domain vocabulary needed for the prompt, add a compact domain bridge to the artifact before asking for the answer. Define terms, give one concrete example, and connect the domain to the current mechanism without filling the learning-core response.
18. When the check asks the user to revise, explain, or answer something for an artifact, put the prompt/correction target into the artifact itself whenever practical. The notebook/repo is the source of truth, not the chat transcript.
19. Notebook edits from `check` may add headings, prompts, answer-shape guidance, quoted context, domain bridges, compressed insight blocks, markers, cleanup notes, and empty answer slots. They must not fill the learning-core answer.
20. Label artifact blocks by evidence role when adding or revising durable notebook content:
   - `Support`: setup, plotting helpers, primers, or scaffolds;
   - `Evidence`: user-defended implementation, explain-back, transfer checks, or reflections;
   - `Mixed`: scaffold plus user response in one block;
   - `Audit trail`: preserved mistake plus correction/why.
   Prefer evidence-role labels over exact authorship claims unless exact provenance is certain and relevant.
21. If the brick passes, say so and give exactly one next micro-step.
22. Do not silently write or fix learning-core code. Ask the user to attempt it.

## Session hooks

Use `check` as a natural soft checkpoint for learning-session tracking.

- If the checked brick passes, treat that as a **session-checkpoint candidate**.
- If the user says they are done, stopping, tired, wrapping, or at a good stopping point, treat that as a **session-stop candidate** and offer or write a concise progress-log entry.
- At session-stop candidates, include or scaffold a lightweight **capability-delta audit** when useful: what the user can now explain/apply/connect that they could not before, what evidence supports it, why it matters later, and the next retrieval/check.
- If the current notebook is the credential-facing artifact, prefer placing the capability-delta audit in the notebook as an evidence-role-labeled learning stack trace, not only in chat.
- Because capability-delta audits are progress evidence rather than learning-core answers, `check` may draft or fill them after the mechanism passes. Ask the user to verify truthfulness, not to author bookkeeping prose by default.
- When a brick passes, append or refresh the concept's row in the artifact repo's `retrieval.md` ledger (concept, passed date, next-check date per the 1-day → 1-week → module-boundary cadence, status `open`). This is mechanical bookkeeping the assistant does; the ledger is the retrieval mechanism, a prose "next retrieval" line alone does not count.
- If a commit/push happens after learning work, use git timestamps as supporting evidence for time estimates, not ground truth.
- Never report inferred time as exact. Use labels: `explicit`, `git-derived`, `chat-derived`, or `mixed estimate`.
- Prefer logging useful session evidence over making the user manage a timer.

## Output format

Keep it short.

Use:

**Check**
Pass / Partial / Not Yet — one sentence.

**What I See**
2-4 bullets grounded in the file/repo.

**Learning Edge**
One concise explanation of the live conceptual issue, if any.

**Classification**
Learning-core / Artifact cleanup / Scaffold defect / Tooling friction / Domain bridge — one sentence.

**Explain Back**
1-3 questions the user should answer before moving on.

**Next**
Exactly one next correction or next brick.

## Guardrails

- Do not praise vague effort as mastery.
- Do not pass a computable answer that has no executed check backing it.
- Do not soften or reinterpret an external verification result that contradicts a prior self-graded verdict.
- Do not accept trivial probes as proof of depth; this learning system depends on questions that can expose shallow understanding.
- Do not rewrite the notebook unless the user explicitly asks and the code is scaffolding.
- Do not give the learning-core answer before the user attempts it, unless the user is stuck and the teaching move is explicitly a worked example.
- When validating a draft learning-core answer, do not turn diagnostic feedback into a polished replacement answer. Use a fill-in scaffold or probe instead.
- Do help with tooling, plotting, file moves, git, and notebook mechanics.
- Do fix scaffold defects directly when they block progress; unclear blanks are a system failure, not the user's learning failure.
- Do centralize prompts, correction targets, and durable explain-back tasks in the notebook/repo when the artifact is meant to be a visible credential signal.
- Do use Q/A as the repair surface when understanding is still moving, then centralize only the final repaired answer and compressed durable insight in the notebook.
- Do add compact domain bridges to the artifact when unfamiliar applied-domain vocabulary blocks an otherwise valid prompt.
- Do mark the evidence-role divide clearly in durable artifacts so teaching support and user-demonstrated work are distinguishable.
- Do preserve useful mistakes during cleanup as an audit trail, then add correction/why based on understanding the user has demonstrated.
- Do stop treating cleanup as learning once the mechanism survives a meaningful probe.
- Do distinguish safe autocomplete from learning-core substitution. Autocomplete is acceptable for non-target mechanics, but learning-core autocomplete requires reconstruction or defense before it counts.
- If a concept feels familiar but dusty, use a formal mechanism refresh before pushing forward.
- Prefer concise answers; this skill should feel like a tight coach, not a lecture.
