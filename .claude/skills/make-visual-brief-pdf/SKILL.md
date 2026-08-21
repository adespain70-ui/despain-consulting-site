---
name: make-visual-brief-pdf
description: Create a clear widget-previewed one-page visual brief PDF from complex material, using Claude's native diagram widget, the approved visual recipe, and the user's existing PDF workflow. Defaults to the DeSpain Consulting brand edition (see design-system.md). Use for client operating-model maps, AI opportunity maps, discovery-call recaps, decision briefs, proposal one-pagers, and branded explainers; do not use for text-only explanations.
---

# Make Visual Brief PDF

Create one useful page, not a document-production system. Own the meaning,
diagram, handoff packet, and final visual check. Let the user's installed PDF
workflow own PDF rendering.

## Make the brief

1. Identify the audience and the one question the page must answer.
2. Separate current, proposed, unproven, held, and completed states when those
   distinctions matter. Never turn missing evidence into success.
3. Find the starting state, primary path, real branches, decisions, approval
   points, proof gates, holds, and terminal result.
4. Create the smallest diagram that preserves those relationships.
5. Write a concrete title and a one-to-three-sentence plain-language summary.

Keep labels short, connectors local, and colors meaningful. Pair color with a
status word, shape, or legend. Split a diagram that cannot be followed without
tracing long crossing or backward lines.

## Use Claude's native diagram widget

Use the native diagram or artifact widget exposed by the current Claude
client. Follow the widget's own schema and render exactly one diagram. Keep
prose below it brief and do not repeat the diagram in text.

Author inline. Do not spawn a background diagram agent or depend on another
diagram skill. If no native widget is available, use a fenced Mermaid diagram
as the portable fallback and say that it may display as source.

When the user requests a PDF or reusable asset, also create portable Mermaid
source and prepare this handoff:

- title and summary;
- version, date, and optional attribution;
- theme and brand choice;
- footer principle and URL; and
- stable output filename.

Pass that packet to the user's existing PDF workflow, such as `bangerpdf`,
through its normal interface. Do not install a renderer or invent a second PDF
pipeline.

## Apply the visual system

Read `design-system.md`. For the default AIBL student edition, read the recipe
it points to and use the bundled logo. A user-supplied brand or explicit neutral
request overrides the default for that run.

## Finish

Use the PDF workflow's native proof or preview. Inspect the entire final page
after the last change. Require readable node text, no clipping or overlap,
correct metadata and branding, one obvious reading path, and no em dash
characters. Deliver the checked PDF and reusable Mermaid source together.
