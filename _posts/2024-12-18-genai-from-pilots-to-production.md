---
layout: post
title: "GenAI in 2024: the pilots are over, the plumbing remains"
date: 2024-12-18
category: Insights
excerpt: "The clients whose AI pilots reached production this year shared one trait: they treated it as systems integration, not magic."
---

Closing out 2024, we count the year's generative AI scoreboard among our clients: many pilots, a handful in production, and a clear pattern separating the two groups. The pattern has nothing to do with model choice, budget size, or industry. It has to do with what the team believed the work was.

## The pilots that stalled

The stalled pilots treated the model as the product. A demo was built in two weeks, it impressed a steering committee, and then it sat. When asked to put it in front of customers, the team could not answer the production questions: what happens when the model is wrong, what does a request cost at projected volume, who reviews outputs that carry consequences, what data is the model actually allowed to see. The demo had been built precisely by deferring those questions, and answering them turned out to be the whole project. Several pilots quietly ended there, which in some cases was the correct outcome, just an expensive route to it.

## The ones that shipped

The clients who reached production inverted the effort. The model was treated as one component in a system, and most of the engineering went into everything around it:

- Retrieval over governed data, so the system answers from sources the organization actually trusts, with access controls intact rather than flattened into one index.
- Evaluation suites that run on every prompt change, model upgrade, and retrieval adjustment, because "it seems better" is not a regression test.
- Cost and latency budgets set before launch, with the unglamorous engineering of caching, truncation, and model-size selection done to meet them.
- Human review on consequential outputs, scoped narrowly enough that reviewers are a control rather than a bottleneck.
- Honest fallbacks when confidence is low: the system says it does not know, or routes to a person, instead of improvising.

None of this is exotic. It is ordinary systems integration, the same discipline that makes any external dependency safe to build on. The teams that already had strong engineering practices found that those practices transferred almost without modification. The model is a remarkably capable, occasionally wrong, metered external service; engineering has known how to wrap such things for decades.

## What we expect from 2025

Our expectation for the coming year: less novelty, more accountability. Budget owners who approved 2024's experiments will ask what these systems cost per month and per request, how they fail and how often, and who is watching when they do. Procurement and security teams will fold AI features into their standard questionnaires rather than treating them as exempt curiosities. Teams with real evaluation data and cost telemetry will answer easily. Teams with a demo and a hope will have a harder January.

We consider this maturation, not backlash. The technology earned the attention; now it has to earn the line item, and that is what production has always meant.

If your pilot is in the gap between demo and deployment, the work remaining is plumbing, and plumbing is estimable, schedulable, ordinary work. Scoping exactly that gap is something we have now done enough times to do quickly.
