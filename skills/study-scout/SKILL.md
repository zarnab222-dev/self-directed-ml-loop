---
name: study-scout
description: Surface high-fit learning resources for the user's current ML/robotics curriculum pain point. Use when the user asks for resources, videos, animations, lectures, visual explainers, readings, practice sources, or help understanding a concept; especially when recommendations should account for the user's learning style, current artifact, curriculum phase, budget constraints, and AI-assisted mastery loop.
---

# Study Scout

Mechanism name: **Study Scout**.

Purpose: find a small, current, high-fit set of learning resources for the active curriculum brick. Do not dump a bibliography. Scout resources that reduce the user's actual confusion and turn them into an action. Resource modality must be chosen from the pain point, not from a standing preference for visuals or videos.

## Read first

Read these when the request is for the ML/robotics curriculum:
- `~/brain/wiki/concepts/self-study-ml-engineering.md`
- `~/brain/wiki/concepts/ml-pivot-diagnostic.md`
- `~/brain/wiki/concepts/learning-loop-contract.md`

If the user names or implies a current artifact, inspect it directly. Default repo:
- `~/ml-proof-packets`

## Search requirement

Use web search for resource recommendations unless the user explicitly asks for local-only suggestions. Learning resources, video availability, playlists, docs, and interactive tools change over time.

Before ranking resources, classify the pain point by modality need:
- **Spatial/geometric intuition**: prefer interactive animations, visual simulations, diagrams, and visual explainers.
- **Semantic contract / type compatibility / notation / ordering validity**: prefer compact formal notes, typed examples, contract tables, function-composition analogies, worked symbolic examples, and small artifact-local exercises. Visualizers may be harmful if they add a second notation layer.
- **Implementation mechanics**: prefer docs, minimal examples, notebooks, and practice tasks that can be copied into the artifact as scaffolding.
- **Formalization after intuition**: prefer course notes, textbook sections, and canonical references.
- **Motivation/overview**: prefer short videos only when the task is low-stakes priming, not current-brick evidence.

Prefer source types in this order only after the modality need is classified:
1. The modality that directly targets the pain point.
2. Practice problems, notebooks, or artifact-local prompts that turn the idea into evidence.
3. Course notes or primary docs that tighten vocabulary and notation.
4. Videos or animations when they fit the classified need.
5. Textbook/reference material for formalization after intuition is repaired.

For technical docs or course materials, prefer primary sources: official course pages, instructor channels, university notes, project docs, or canonical library docs.

## Fit model

Rank resources by fit, not popularity alone. Use these criteria:
- **Pain-point match:** targets the specific confusion, not the broad topic.
- **Modality fit:** matches the kind of missing brick. Do not recommend visual resources for a semantic/type-contract gap merely because the broader topic is geometric.
- **Learning-mode fit:** supports building, explaining, quizzing, notes, teaching back, or visual reasoning.
- **Mechanism clarity:** reveals the underlying mechanism instead of naming it.
- **Artifact usefulness:** can feed the current proof packet or notebook.
- **Budget fit:** free/local/reusable by default.
- **Accessibility fit:** visuals should use labels, line styles, markers, or clear colors; avoid shade-only distinctions when recommending diagrams/tools if alternatives exist.
- **Depth path:** helps move from intuition to formalism, not just passive familiarity.
- **Probeability:** supports non-trivial checks: transfer examples, edge cases, failure modes, assumptions, or contrast with a nearby concept.

Treat a momentary preference like "prioritize animations and video" as a weighting, not an absolute. Use it when it helps the classified pain point, but override it when the preference would harm the current insight. Explain the override briefly.

## Workflow

1. Identify the active brick and pain point in one phrase.
2. Inspect local artifact context if relevant.
3. Classify the modality need: spatial/geometric, semantic contract/type compatibility, implementation mechanics, formalization, or motivation/overview.
4. Search the web with focused queries; include the concept, modality, and level. Example: `linear algebra shear matrix animation`, `robotics frame transform subscript cancellation`, `function composition type mismatch tutorial`, `ROS tf2 transform tree frame semantics`.
5. Select 3-6 resources total.
6. Group them into a tiny learning path:
   - **Start here**: the fastest resource to repair intuition.
   - **Then build**: resource or prompt that turns the idea into an artifact/action.
   - **Formalize**: resource that tightens vocabulary/math after the intuition lands.
7. For each resource, include why it fits and exactly how to use it.
8. End with one suggested next action and one explain-back prompt that is hard enough to expose shallow understanding.

## Output format

Keep it concise.

Use:

**Pain Point**
One sentence naming the current confusion and the modality need.

**Resource Stack**
3-6 bullets. Each bullet must include:
- linked title
- type: animation, video, notes, practice, docs, etc.
- why this fits
- how to use it in 10-30 minutes

**Use Order**
Numbered sequence of 2-4 steps.

**Explain Back**
One non-trivial question the user should answer after using the resources. Prefer transfer, edge-case, contrast, or failure-mode questions over recall.

**AI Role**
One sentence describing how AI assistance should help after the user engages with the resources.

## Guardrails

- Do not return a large list.
- Do not optimize for passive consumption.
- Do not optimize for a preferred resource modality when it conflicts with the pain point.
- Do not offer easy comprehension checks as proof of learning.
- Do not recommend paid resources unless clearly necessary or unusually high leverage.
- Do not let resources replace the current artifact; they support the brick.
- Do not use AI-generated summaries as if they are sources.
- Do not assume videos are current or available without checking.
- If no good visual resource exists, or if a visual resource would add misleading notation/friction, say so and recommend the best alternative.
