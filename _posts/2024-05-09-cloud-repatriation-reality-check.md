---
layout: post
title: "The repatriation debate needs less ideology"
date: 2024-05-09 11:56:00 -0500
author: "Priya Sharma"
category: Insights
excerpt: "Moving workloads out of the cloud makes sense for a specific profile of workload; it is not a movement, it is arithmetic."
---

The loudest infrastructure debate of 2024 is whether companies should leave the cloud. High-profile exit stories with dramatic savings figures circulate on one side; the cloud providers' own case studies circulate on the other. Both genres select their examples carefully. As usual, the interesting answer is unfashionably specific.

## The workload profile where repatriation wins

Repatriation math works for workloads that are large, steady, and predictable: a constant compute footprint, heavy storage with high egress, little use of managed services. Cloud pricing is, at its core, a premium paid for elasticity and for someone else's operations. A workload that never flexes is paying for elasticity it never uses, and a workload built on plain VMs and open-source software is barely consuming the managed-services value either.

Add the second condition, which the headline stories tend to underweight: you need the operational bench to run hardware. Procurement, datacenter or colocation contracts, capacity planning, hardware failures at 3 a.m., and the unglamorous discipline of patching all return to your payroll. If that describes your estate and you have the operational bench to run hardware, owning servers can genuinely cost less, sometimes dramatically so at scale.

## Why it does not describe most companies

It does not describe most of our clients. The typical estate we see has variable load, daily and seasonal swings where scale-to-zero and autoscaling do real financial work. It has a lean platform team, often a handful of engineers, whose time is the scarcest resource in the company and who would be consumed by hardware operations. And it leans heavily on managed databases, queues, and identity services whose self-hosted equivalents demand exactly the specialist staffing the company lacks. Variable load, lean platform teams, and heavy reliance on managed databases and queues all tilt the math back toward cloud.

The error in both ideological camps is treating the estate as one decision. Estates are portfolios. A company can correctly run its spiky customer-facing services in the cloud while correctly moving a massive, steady data-processing pipeline onto owned hardware.

## Run the numbers, per workload

Our position: run the numbers per workload, not per ideology. The comparison we build with clients includes the lines that casual analyses drop:

- Fully loaded hardware cost, including refresh cycles, colocation, power, and network, not just the server invoice.
- Egress and inter-site bandwidth, which punish some architectures in the cloud and others out of it.
- The market salary cost of the operational roles each path requires, counted honestly.
- The cloud-side number after right-sizing and committed-use discounts, because comparing owned hardware against an unoptimized cloud bill flatters repatriation every time.

We have helped clients move workloads in both directions this year, and both moves were correct. One moved a steady, storage-heavy processing estate to owned hardware and is saving meaningfully. Another retired a struggling colocation footprint into GCP because its two-person infrastructure team was the bottleneck on the entire product roadmap. The same arithmetic, applied to different facts, produced opposite answers, which is what arithmetic is supposed to do.

If your organization is feeling pressure to pick a side in this debate, the more useful exercise is a workload-level cost model with the people costs left in. Building exactly that model, without a predetermined conclusion, is a service we find ourselves delivering more often each quarter.
