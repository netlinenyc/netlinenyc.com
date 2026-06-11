---
layout: post
title: "Design systems for small product teams"
date: 2023-02-21
category: App Design
excerpt: "A design system for a ten-person team should be a component library with rules, not a department."
---

Design systems have a reputation as a big-company investment. We disagree, with one caveat: scale the ambition down. For most of our clients, a useful design system is a tokenized color and type scale, two dozen components, and written usage rules. Not a dedicated team, not a custom documentation site.

## What "small" actually means

The large-company version of a design system comes with full-time staff, a documentation portal, contribution governance, and a roadmap of its own. A ten-person product team copying that model will spend two quarters building infrastructure and zero quarters shipping features. The system becomes the project, which is precisely backwards.

The right-sized version fits in the existing codebase. Design tokens live in one file: color, typography, spacing, radii, elevation. Components live in one package with the application that consumes them, or in a small internal library if there are multiple surfaces. Documentation is a Storybook instance and a short markdown file of rules: when to use which button variant, how forms handle errors, what empty states look like. That is the entire footprint, and it is enough.

## A case from our own work

We recently helped a NYC-based subscription business consolidate three inconsistent product surfaces onto a shared component library. The web app, the account portal, and the internal admin tool had each accumulated their own buttons, modals, and form patterns over four years of separate development. Designers were redrawing the same screens with slightly different rules; engineers were re-fixing the same bugs in three places.

The consolidation work was deliberately modest. We extracted tokens first, then rebuilt roughly twenty-five components in React against those tokens, then migrated surfaces screen by screen as feature work touched them rather than in a big-bang rewrite. The payoff showed up within a quarter: faster feature delivery, fewer visual regressions, and a design review process that argues about flows instead of paddings.

## Rules that keep a small system alive

Small systems die from neglect or from exceptions, rarely from anything else. The practices we install to prevent both:

- Version the library and publish a changelog, even if the only consumer is one app. Untracked changes are how trust erodes.
- Treat every exception as a pull request rather than a workaround. If a screen genuinely needs a new variant, it goes into the library where the next screen can use it.
- Give the system a named owner with a small, protected time budget, on the order of half a day a week, not a headcount.
- Review the component inventory quarterly and delete what nothing uses. A smaller system is easier to trust.

The discipline matters more than the tooling. A team that follows these rules with plain CSS variables will outperform a team with a sophisticated token pipeline and no enforcement.

Start small, keep it versioned, and let the system grow only as fast as real product needs pull it. If your team is staring at three inconsistent surfaces and wondering where to begin, this kind of right-sized consolidation is work we do often, and it is more affordable than most teams assume.
