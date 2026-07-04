# Start here

This repo is a self-directed, AI-assisted learning loop for an applied-ML/robotics
curriculum. It's a set of Claude Code skills plus a one-time "diagnostic" prompt
that bootstraps *your own* curriculum — none of the original author's personal
content is in here, just the mechanism.

## 0. Prerequisites

- [Claude Code](https://claude.com/claude-code) (or another agent with filesystem
  access and support for `.claude/skills/`).
- A folder for your notes/curriculum — this repo assumes `~/brain/wiki/...` by
  convention. Rename freely, just be consistent (find/replace `~/brain` across
  the `skills/` folder if you move it).
- A folder for your code/notebooks — this repo assumes `~/ml-proof-packets`.
  Doesn't need to exist yet.

## 1. Install the skills

```bash
git clone <this-repo-url> ml-learning-loop
cp -r ml-learning-loop/skills/* ~/.claude/skills/
```

Restart or open a new Claude Code session so it picks up the new skills.

## 2. Run your own diagnostic

This is the one manual step — a conversation, not a skill, because it has to be
*your* answers, not a copy of someone else's. Open a fresh Claude Code session
(anywhere, filesystem access is all it needs) and paste this:

```text
I'm starting a self-directed, AI-assisted applied-ML/robotics learning loop and
need you to run an initial diagnostic with me. Interview me — ask one question
at a time, don't move on until you have a real answer — covering:

1. Target: what competence level am I aiming for (e.g. "job-ready ML engineer,"
   "PhD-equivalent applied ML," "enough to ship a specific project"), and what's
   the timeline/urgency?
2. Depth signal: is there a specific sub-domain (robotics, NLP, vision, RL,
   whatever) I want as a spine for depth, even if the goal is broader?
3. Mission domains: what application areas motivate me (why do I actually care)?
4. Background: what math/CS/programming do I already have? Be specific about
   what's solid vs. rusty vs. missing.
5. Learning style: how do I actually learn — building, explaining out loud,
   being quizzed, lectures, reading, projects, some mix?
6. Tools: what editor, notebook environment, version control, and AI coding
   assistant do I actually use?
7. Constraints: time per week, budget, any accessibility needs (e.g. color
   vision, preferred contrast/theme) that should shape how you recommend
   resources.
8. Motivation/failure modes: what makes me lose momentum? What's derailed me
   before (perfectionism, tutorial hell, no feedback loop, etc.)?
9. What counts as evidence: do I want public artifacts (notebooks, a GitHub
   repo) as the credential substitute, or something else?

When you have real answers to all of these, write two vault pages:

- `~/brain/wiki/concepts/ml-pivot-diagnostic.md` — the raw diagnostic: my
  answers to the above, dated.
- `~/brain/wiki/concepts/self-study-ml-engineering.md` — a phased curriculum
  derived from those answers: ordered phases/modules, each with what "done"
  looks like, starting from my actual current level (don't assume foundations
  I don't have, don't re-teach things I already know).

Also create empty stubs I'll fill in as I go:
- `~/brain/wiki/synthesis/learning-queue.md` — open questions/backlog.
- `~/brain/wiki/concepts/external-verification-registry.md` — a place to map
  each phase to an external oracle (a course pset, a graded problem set, a
  leaderboard, a mock interview) once I find one, so my own self-grading isn't
  the only signal.

Keep the interview tight — this should take one sitting, not a marathon.
```

## 3. Get the pedagogy contract (optional but recommended)

Run the `learning-loop-storm` skill (`/learning-loop-storm` or just ask for it).
It runs a real research pass (via the bundled `storm` skill) on how AI-assisted
mastery loops should actually work, and writes you a
`~/brain/wiki/concepts/learning-loop-contract.md` — the rules `next-brick` and
`check` follow when deciding how to teach you specifically. This step is what
makes the loop *yours* instead of a generic tutor.

## 4. Daily loop

- `/next-brick` — what to do right now, one atomic step.
- `/check` — after you've done it, verify whether it actually counts.
- `/study-scout` — stuck on a specific concept, want resources for it.
- `/learning-stack-audit` — run weekly (or whenever it feels like drift) to
  check you're still grinding, not just optimizing process.

## Updates

This is a personal set of skills, shared as-is — no roadmap, no support
guarantee. If the original author updates their skills, they may push updates
here; `git pull` and re-copy `skills/*` into `~/.claude/skills/` to pick them up.
Your own vault content (diagnostic, curriculum, contract) lives outside this
repo and is never touched by an update.
