---
layout: post
title: "Rolling out design tokens without a rewrite"
date: 2025-05-20
category: App Design
excerpt: "Design tokens can be introduced into a living product incrementally, starting with color and spacing in the highest-traffic screens."
---

Design tokens, the named variables that carry color, spacing, and typography decisions from design files into code, are often pitched as part of a ground-up rebuild. They do not need to be.

Our incremental playbook: extract the current de facto palette from the codebase, even if it is inconsistent; define a token set that covers ninety percent of cases; alias old values to new tokens so nothing visually changes on day one; then migrate screen by screen, starting where users actually spend time.

On a recent engagement with a B2B analytics product, this approach delivered a full dark mode, previously estimated as a quarter of work, in three weeks, because by then color decisions lived in exactly one place. That is the entire argument for tokens.
