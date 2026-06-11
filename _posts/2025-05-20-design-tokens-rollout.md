---
layout: post
title: "Rolling out design tokens without a rewrite"
date: 2025-05-20 15:03:00 -0500
author: "Sarah Coleman"
category: App Design
excerpt: "Design tokens can be introduced into a living product incrementally, starting with color and spacing in the highest-traffic screens."
---

Design tokens, the named variables that carry color, spacing, and typography decisions from design files into code, are often pitched as part of a ground-up rebuild: new design system, new component library, new everything. That framing kills more token initiatives than any technical obstacle, because few products can afford to stop and rebuild, and so the proposal dies in prioritization. It does not need to. Tokens can be introduced into a living product incrementally, with value arriving along the way rather than at the end.

## The incremental playbook

Our approach has settled into four steps, refined across several engagements.

- Extract the current de facto palette from the codebase, even if it is inconsistent. Tooling makes this mechanical: scan the stylesheets and components, and inventory every color, spacing value, and type style actually in use. The result is usually sobering, with dozens of near-identical grays and a spacing scale that is less a scale than a history.
- Define a token set that covers ninety percent of cases. Resist completeness. A compact set of semantic tokens for surfaces, text, borders, interactive states, and a real spacing scale will absorb most of the inventory. The long tail of one-off values can be handled during migration rather than designed for upfront.
- Alias old values to new tokens so nothing visually changes on day one. This is the step that makes the whole approach safe: the token layer goes in underneath the existing UI, every legacy value maps to its nearest token, and the release that introduces tokens is visually a no-op. There is no big-bang risk because there is no big bang.
- Migrate screen by screen, starting where users actually spend time. Analytics tells you which screens matter; migrate those first and the long tail whenever those files are next touched. Perfection across the entire codebase is not the goal. Coverage of the surfaces users see is.

## Proof from a recent engagement

On a recent engagement with a B2B analytics product, this playbook ran against a six-year-old React codebase with the expected sediment: three button implementations, charts styled independently of the rest of the app, and color values pasted between files for years. Extraction and token definition took about two weeks; the aliasing release shipped with zero visual diff, which we verified with screenshot comparison across the top screens.

Then came the payoff that made the case better than any argument. The client wanted dark mode, which had been estimated, reasonably, at a quarter of work back when color decisions lived in hundreds of files. After the token migration covered the high-traffic screens, a full dark mode shipped in three weeks. The work consisted of defining a second value set for the existing semantic tokens and fixing the handful of components that had not yet been migrated. Color decisions lived in exactly one place, so changing all of them at once was an ordinary task instead of an archaeology project.

That is the entire argument for tokens: they convert global visual changes from expeditions into edits, including theming, rebrands, accessibility contrast fixes, and density adjustments. If a rewrite is the price being quoted for that capability, it is worth knowing the incremental route exists. It is a route we have walked with enough products now to estimate it with confidence.
