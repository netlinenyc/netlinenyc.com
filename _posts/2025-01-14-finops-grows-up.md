---
layout: post
title: "FinOps grows up"
date: 2025-01-14
category: Cloud
excerpt: "Cloud cost management has matured from spreadsheet archaeology into an engineering discipline with owners and SLOs."
---

Three years ago, cloud cost work meant a quarterly spreadsheet exercise and a round of finger-pointing. Finance would export the bill, attempt archaeology on untagged resources, and circulate a report that engineering disputed and nobody acted on. The next quarter, the same ritual. Watching the discipline mature out of that pattern has been one of the quieter satisfactions of our practice.

## What the mature version looks like

The clients doing FinOps well in 2025 share a recognizable shape, and it is organizational before it is technical.

- Unit economics are defined per product: cost per order, per active user, per pipeline run. Total spend going up is not a finding; cost per unit going up is.
- Allocation is complete because tagging is enforced at provision time, through Terraform modules and policy checks, not requested politely after the fact. Untagged resources do not deploy.
- Engineers see the cost of their own services weekly, in the tools they already use, at the granularity they can act on. A platform-wide number motivates nobody; the cost of your service, next to last week's, does.
- Commitments such as reserved instances and savings plans are managed centrally by someone with an actual forecast, rather than purchased ad hoc by whichever team noticed the discount.

The cultural marker we watch for: cost reviews happen in engineering standups, not finance meetings. When an engineer flags their own service's cost regression the way they would flag a latency regression, the discipline has landed. Cost has become a property of the system that the people who build the system own, with the same loop of measurement, ownership, and review that made reliability engineering work.

## Why this took three years

The tooling existed earlier; the organizational wiring did not. The hard problems were never technical. They were questions like who owns shared platform costs, whether a product's unit metric is orders or sessions, and whether leadership will actually let an engineering team trade a feature week for an efficiency week. Clients who answered those questions got value from ordinary tooling. Clients who bought sophisticated tooling without answering them got dashboards nobody opened. We have seen both, repeatedly, and the difference in outcomes is not close.

## The wrinkle ahead: AI workloads

The newer wrinkle is AI workloads, where GPU spend can swamp everything else on the bill. A single training run can cost what a mid-sized service costs in a month, and an inference feature's costs scale with adoption in ways product teams rarely model in advance.

Our early read is that the same principles apply: unit economics, allocation, engineer-visible spend. But the feedback loop has to be faster. A monthly review of a workload that can burn its quarterly budget in a week is not a control, it is a postmortem schedule. The teams handling this well are moving to daily spend visibility and pre-launch cost modeling for anything GPU-shaped. We will have more to say on that this year as the pattern firms up.

If your cost process still looks like the quarterly spreadsheet ritual, the path out is well mapped at this point, and shorter than it used to be. Helping clients walk it has become a steady part of our cloud practice.
