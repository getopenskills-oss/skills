---
name: task-planner
description: "Turn a goal or a messy project into a concrete plan: milestones, ordered tasks with owners and estimates, dependencies, risks, and the very next step. Use when the user asks to plan a project, break down a big task, or make a to-do list from a goal."
---

# Task Planner

## When to use
- "Help me plan…", "break this down", "where do I start?", "make a roadmap".

## Process
1. **Clarify the outcome**: what does "done" look like, by when, with what constraints (people, budget, tools)?
2. **Work backward from done** into 3–6 milestones. Each milestone is a visible, testable result, not an activity.
3. **Break milestones into tasks** small enough to finish in half a day to two days. Start each with a verb.
4. **Order by dependency**, and mark what can run in parallel.
5. **Estimate** each task (S ≤ 2h, M ≤ 1 day, L ≤ 3 days). Anything bigger gets split.
6. **Identify risks and unknowns**, and schedule early tasks to reduce the biggest one (a spike, a prototype, a question to ask).
7. **Name the next action** — the single thing to do today.

## Output format
```
## Goal
One sentence + definition of done + deadline.

## Milestones
1. Milestone — what is true when it is reached — target date

## Tasks
| # | Task | Milestone | Size | Depends on | Owner |

## Risks
- Risk — likelihood/impact — mitigation

## Next action
The first concrete step, doable today.
```

## Rules
- Do not invent deadlines or owners; leave them blank or ask.
- Keep the plan as short as the project allows — a weekend project does not need a risk register.
- Leave buffer: plans that fill 100% of the time are already late.
