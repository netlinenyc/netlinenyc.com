---
layout: post
title: "FinOps for AI workloads: faster loops, harder questions"
date: 2026-03-12 11:13:00 -0500
author: "Sarah Coleman"
category: Insights
excerpt: "AI spend breaks the monthly cost review cadence; GPU-heavy workloads need unit economics and daily feedback to stay honest."
---

A year ago we predicted AI workloads would stress-test FinOps practices. That has held up, and then some. AI line items that were rounding errors on client bills in 2024 now rival or exceed core infrastructure spend in several environments we review, and the cost behaviors involved do not resemble the workloads FinOps grew up managing.

## The patterns we keep finding

Across client environments, three patterns recur often enough to be predictable.

- Inference costs that scale with usage in ways product teams did not model. A feature priced casually during the pilot becomes a margin problem at adoption, because cost per request was never connected to revenue per request. Successful features are the dangerous ones; the cost curve follows the adoption curve, and nobody assigned an owner to that relationship.
- Fine-tuning jobs left running over weekends. A forgotten experiment on GPU instances costs what a small team costs, and the traditional monthly review discovers it three weeks too late. We have found these on first-pass audits at a majority of AI-heavy clients.
- GPU capacity reserved out of scarcity fear and then underused. Teams who were burned by capacity shortages in 2024 and 2025 over-reserved in response, and reserved-but-idle accelerators are now among the largest single waste items we see, made worse because the reservation decision felt prudent when it was made.

None of this reflects incompetence. It reflects spend that moves at a speed the existing controls were never built for.

## The discipline transfers; the cadence does not

The core FinOps principles carry over cleanly: unit economics, full allocation, engineer-visible spend, centrally managed commitments. What breaks is the clock. A monthly cost review is a perfectly good control for a steady web estate, where spend drifts by percentage points. An AI feature can burn a quarter's budget in a week, and a control loop that runs monthly against a failure mode that develops in days is not a control. It is a postmortem schedule.

Our current baseline for AI-heavy clients reflects that compression. Cost per request and per training run are defined before launch, not reconstructed after, so there is a number to defend in design review. Spend is visible daily, broken out by workload, with the engineers who own each workload seeing their own line. Hard budget alerts are wired to paging rather than to email, because an email about runaway GPU spend gets read after the money is gone. And every review carries a standing question: would a smaller model do? In our experience the honest answer is frequently yes, and the savings from right-sizing models routinely exceed what infrastructure tuning can offer, since the model choice dominates the unit cost.

## The harder questions arriving now

The maturing conversation goes past hygiene into portfolio questions: which AI features earn their cost at observed usage, which should be renegotiated down to cheaper models or tighter scopes, and which were experiments that should now end. These are product decisions wearing a cost report, and they require the unit economics to exist before they can be asked at all.

Teams that built the fast loop are having those conversations from data; teams without it are still arguing about last month's bill. Getting clients from the second group into the first has become one of the most common requests in our cloud practice, and it usually takes weeks rather than quarters.
