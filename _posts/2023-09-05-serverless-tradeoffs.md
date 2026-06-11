---
layout: post
title: "Serverless tradeoffs, honestly stated"
date: 2023-09-05
category: Cloud
excerpt: "Serverless removes a class of operational work and introduces a class of architectural constraints; both sides belong in the decision."
---

We design serverless architectures regularly, and we decline to design them regularly too. The honest tradeoff sheet looks like this.

What you gain: no instance patching, fine-grained scaling to zero, pay-per-use economics for spiky traffic, and faster paths to production for event-driven glue.

What you accept: cold-start latency on infrequently used paths, execution time and payload limits that shape your design, harder local testing, observability that requires deliberate investment, and a deeper coupling to one provider's primitives.

Our rule of thumb: serverless excels for asynchronous processing, scheduled jobs, and APIs with irregular load. For latency-sensitive, steadily loaded services, containers on a managed platform usually cost less and surprise you less.
