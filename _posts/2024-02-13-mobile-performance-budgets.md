---
layout: post
title: "Mobile performance budgets that teams actually keep"
date: 2024-02-13
category: App Design
excerpt: "Performance budgets only work when they are enforced in CI and owned by the same people who ship features."
---

Every team agrees mobile performance matters. Few teams can state their cold-start time, and fewer have a number it is not allowed to exceed. That gap is where performance budgets come in, and where most attempts at them quietly fail.

## Why good intentions decay

Mobile apps do not get slow in one decision. They get slow in eighty small ones: an analytics SDK here, a heavier image format there, one more synchronous call on the startup path. Each change costs a few dozen milliseconds, no single review flags it, and eighteen months later the app takes four seconds to open and nobody can say when that happened. Quarterly performance reviews catch the trend after it has compounded; by then the fix is an archaeology project across hundreds of commits.

A budget converts the slow drift into discrete, attributable events. The number exists, the build measures against it, and the pull request that breaks it is standing right there.

## Our working format

Our working format: pick three or four metrics that map to user experience, such as cold start, time to first meaningful screen, scroll jank rate, and app size. Resist the urge to track twenty; a dashboard nobody can fail is a dashboard nobody reads.

Set thresholds from current reality plus a stretch, then enforce them in CI so a regression fails the build rather than a quarterly review. Two details make the enforcement workable in practice. Measure on real or representative low-end hardware, because the simulator on a developer laptop flatters everything. And run enough iterations to tame variance, gating on a median across runs, so the team trusts a red build instead of learning to rerun it until it passes.

The other half of the format is ownership. The budget belongs to the feature teams, not to a separate performance group, because the people who can breach a budget must be the people accountable for it. When a build fails, the choices are explicit: optimize the change, cut something else from the startup path to make room, or raise the budget deliberately, in a reviewed change, with a reason attached. All three are legitimate. Silent erosion is not.

## What it caught for one client

On a recent engagement with a consumer fintech app, this approach caught two large regressions before release, both from third-party SDK updates. One marketing SDK's minor version bump added several hundred milliseconds of synchronous initialization on the startup path; a fraud-prevention SDK update added meaningful app size and startup cost. Neither change came from the client's own code, neither appeared in any diff a reviewer would read, and both would have shipped to the entire user base unnoticed. The CI gate flagged both within an hour of the dependency update, while the change was still one revert away from gone.

That is the honest pitch for budgets. The budget did not make the app fast. It kept the app from quietly getting slow, which over a product's life is most of the battle.

Standing up the measurement harness, choosing the metrics, and wiring the CI gates is a few weeks of work for a typical app, and it is work we regularly fold into our app design and delivery engagements. The teams that have it never volunteer to give it back.
