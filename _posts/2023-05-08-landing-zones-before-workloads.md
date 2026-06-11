---
layout: post
title: "Build the landing zone before the first workload"
date: 2023-05-08
category: Cloud
excerpt: "Identity, network topology, logging, and guardrails should exist before the first production workload arrives."
---

The most expensive cloud mistake we see is migrating workloads into an account structure that was never designed. Retrofitting identity boundaries, network segmentation, and centralized logging after fifty workloads are live costs multiples of doing it first. We know because remediating exactly that situation is a recurring line of business for us, and we would rather it were not.

## How estates end up undesigned

No one decides to build a bad foundation. It accretes. A pilot project gets a single account with admin access for the three people involved. The pilot succeeds, a second team joins the same account, and someone adds a VPC for them. A year later there are sixty IAM users, four overlapping CIDR ranges, production and staging sharing a blast radius, and logs scattered across whatever each team turned on. Every one of those decisions was locally reasonable. The sum is an estate where answering "who can access customer data" takes a forensic exercise.

The retrofit is painful precisely because workloads are now live. Moving a production service between accounts means touching its networking, its identity, its DNS, and its CI pipeline, all under uptime constraints. What would have been a week of Terraform up front becomes a quarter of coordinated migration work later.

## Our baseline, consistent across clouds

Our landing zone baseline is consistent across AWS, Azure, and GCP, because the concepts matter more than the vendor names:

- An organization hierarchy that maps to environments and data sensitivity, so a workload's placement tells you its rules.
- Federated identity through the corporate IdP with no standing admin credentials; elevated access is requested, time-boxed, and logged.
- Hub-and-spoke or shared VPC networking with non-overlapping address space planned for the next five years, not the next quarter.
- Centralized audit and flow logs shipped to an account that workload teams cannot alter.
- Guardrail policies, encryption defaults, region restrictions, public-exposure blocks, enforced as code with Terraform rather than as a wiki page.

A competent team can stand this up in three to six weeks. That is the entire premium for never having to do the retrofit.

## Holding the line

None of this is glamorous, and clients sometimes push to skip ahead to the visible wins: the first migrated application, the demo for the board. We hold the line, because every week spent on foundations removes a future quarter of remediation. The compromise we do accept is parallelism. A pilot workload can land in a sandbox account while the landing zone is built, as long as everyone agrees in writing that the sandbox is disposable and nothing in it is production.

The other discipline is keeping the landing zone alive after launch. Guardrails that are not maintained drift into irrelevance within a year. We treat the landing zone as a product with an owner, a backlog, and a release cadence, and we review it whenever a new class of workload arrives.

Foundations are the least visible work we do and the most consequential. If your cloud estate grew before it was designed, the retrofit is harder than the greenfield, but it is well-trodden ground for our team, and it gets cheaper the sooner it starts.
