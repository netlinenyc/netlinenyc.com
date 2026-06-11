---
layout: post
title: "Serverless tradeoffs, honestly stated"
date: 2023-09-05
category: Cloud
excerpt: "Serverless removes a class of operational work and introduces a class of architectural constraints; both sides belong in the decision."
---

We design serverless architectures regularly, and we decline to design them regularly too. Both decisions come from the same tradeoff sheet, and we think more teams should see the whole sheet before committing. Most serverless disappointment we encounter traces to a decision made on the gains column alone.

## What you gain

The gains are real and we do not discount them. No instance patching means an entire category of operational toil and security exposure disappears; nobody is scheduling maintenance windows for OS updates on a Lambda function or a Cloud Function. Fine-grained scaling to zero means a workload that runs twice a day costs nearly nothing in between. Pay-per-use economics fit spiky traffic in a way reserved capacity never will; we have seen event-driven workloads run at a tenth the cost of their always-on equivalents. And for event-driven glue, the path from idea to production is genuinely faster: a queue trigger, a function, a deploy.

For a small team without dedicated operations staff, removing the patching and capacity-management burden can matter more than any line on the cost model.

## What you accept

The constraints column deserves equal billing, because each item shapes architecture rather than merely inconveniencing it:

- Cold-start latency on infrequently used paths, which is irrelevant for batch work and disqualifying for some interactive ones.
- Execution time and payload limits that force long jobs to be decomposed, sometimes naturally and sometimes painfully.
- Harder local testing; the emulators are approximations, and the real behavior of IAM, triggers, and quotas only exists in the cloud.
- Observability that requires deliberate investment, because the default experience of tracing a request across six functions and three queues is poor.
- A deeper coupling to one provider's primitives than containers impose, since the functions, their triggers, and their permission model are all vendor-specific.

None of these is a reason to refuse serverless. They are reasons to know your workload before choosing it. A team that designs around the limits from day one rarely regrets them; a team that discovers the fifteen-minute execution ceiling in week ten of the build does.

## Our rule of thumb

Our rule of thumb: serverless excels for asynchronous processing, scheduled jobs, and APIs with irregular load. Document pipelines, webhook handlers, nightly reconciliation, image processing, integration glue between SaaS systems — these are the workloads where the model's strengths land and its constraints barely register.

For latency-sensitive, steadily loaded services, containers on a managed platform usually cost less and surprise you less. A service handling consistent traffic all day gains nothing from scale-to-zero, pays a premium per request for it, and inherits the cold-start and observability costs anyway. The boring container, autoscaled within a narrow band, wins on every column that matters.

Most real estates we design end up hybrid: containers for the steady core, functions for the event-driven edges, and explicit reasoning about which side of the line each new workload belongs on. That last habit is the one that compounds.

When clients bring us an architecture decision like this one, the deliverable is rarely a technology endorsement. It is the filled-in tradeoff sheet for their specific workloads, which tends to make the choice obvious on its own.
