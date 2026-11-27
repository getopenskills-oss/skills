---
name: diagram-maker
description: Turn a description of a process, system, or data model into a clear Mermaid diagram (flowchart, sequence, ER, state, or timeline). Use when the user asks for a diagram, chart of a flow, architecture sketch, or visual explanation.
---

# Diagram Maker

## When to use
- The user asks to "draw", "diagram", "visualize", or "map out" something.
- A process, architecture, or relationship would be clearer as a picture than as prose.

## Choose the right diagram
| The user describes… | Use |
|---|---|
| Steps, decisions, branches | `flowchart` |
| Messages between actors over time | `sequenceDiagram` |
| Tables / entities and relations | `erDiagram` |
| Lifecycle of one object | `stateDiagram-v2` |
| Events in order | `timeline` |

## Process
1. List the nodes (actors, steps, entities) before drawing anything.
2. List the edges and label every edge that is not obvious.
3. Keep it to ~15 nodes. If larger, split into an overview plus detail diagrams.
4. Write the Mermaid code, then re-read it and check every node is connected and every label is accurate.

## Style rules
- Flow left-to-right (`flowchart LR`) for pipelines, top-down (`TD`) for hierarchies.
- Short node labels (≤ 5 words). Put details in edge labels or a note below.
- Use consistent IDs (`api`, `db`, `user`) and quote labels that contain special characters.
- Do not add colors or styling unless the user asks.

## Output format
1. One sentence saying what the diagram shows.
2. The diagram in a ```mermaid code block.
3. A short legend or notes only if something is not self-explanatory.
