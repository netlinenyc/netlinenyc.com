---
layout: post
title: "Mobile performance budgets that teams actually keep"
date: 2024-02-13
category: App Design
excerpt: "Performance budgets only work when they are enforced in CI and owned by the same people who ship features."
---

Every team agrees mobile performance matters. Few teams can state their cold-start time, and fewer have a number it is not allowed to exceed. That gap is where performance budgets come in.

Our working format: pick three or four metrics that map to user experience, such as cold start, time to first meaningful screen, scroll jank rate, and app size. Set thresholds from current reality plus a stretch, then enforce them in CI so a regression fails the build rather than a quarterly review.

On a recent engagement with a consumer fintech app, this approach caught two large regressions before release, both from third-party SDK updates. The budget did not make the app fast. It kept the app from quietly getting slow.
