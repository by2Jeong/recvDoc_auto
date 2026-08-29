---
name: by-mermaid-flowchart
author: JBY
description: Create, review, or restructure Mermaid flowcharts and architecture diagrams; use for readability, narrow-view layouts, excessive width, or complex branching.
---

# Mermaid diagrams

Optimize for readability in narrow viewers: prefer tall, narrow layouts.

## Layout

- Default to `flowchart TB`; use `LR` only for 2-3 nodes.
- Default subgraphs to `direction TB`; never place 4+ nodes in an `LR` row.
- Keep the widest point at 3 columns or fewer; restructure if wider.
- Merge branches with the same destination.
- Keep Korean text under about 20 characters per line; wrap with `<br/>`.
- Use only short questions in diamonds; move compound conditions to the preceding node.

## Semantics

- Decide whether the diagram is a flowchart or architecture diagram.
- Do not use start/end capsules or decision diamonds in architecture diagrams.
- Use conceptual top-level labels; omit internal variable names, implementation suffixes, and detailed conditions.
- Start each module block with its defined ID and name, e.g. `SAD-M01 · 분석대상 구분`.
- Limit the following description to 1-2 lines.

## Validate

Check width, diamond text, and line wrapping, then render:

```powershell
npx -y -p @mermaid-js/mermaid-cli mmdc -i x.mmd -o x.svg
```

Inspect the SVG. If rendering is unavailable or fails, report structural and render validation separately. Never claim visual validation without rendering and inspecting the SVG.
