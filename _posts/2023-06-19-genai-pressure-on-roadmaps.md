---
layout: post
title: "Generative AI pressure is reshaping 2023 roadmaps"
date: 2023-06-19
category: Insights
excerpt: "Boards are asking every technology leader for an AI story; the durable answer starts with data plumbing, not demos."
---

Nearly every client conversation this quarter has included some version of the same question: what is our generative AI plan? The pressure is real, and much of it comes from above the CTO. Boards have watched six months of headlines, competitors are issuing press releases, and technology leaders are being asked for an AI story on a timeline that has little to do with their actual data readiness.

## The demo trap

The fastest way to answer the board is to ship a chatbot. Wire a model API to a web widget, point it at some documents, and you have a demo in two weeks. We have watched several organizations outside our client base do exactly this, and the pattern is consistent: the demo impresses, the pilot launches, and then reality arrives. The bot answers from stale exports because nobody built a pipeline to keep its knowledge current. It surfaces documents some employees were never supposed to see because nobody mapped permissions. It states figures confidently that disagree with the finance system because nobody defined a source of truth.

Our advice has been consistent. Resist the urge to ship a chatbot as a press release. The model is the most replaceable part of the stack; the work that determines success is everything around it.

## Data plumbing is the durable investment

The organizations that will benefit from this wave are the ones whose data is accessible, governed, and clean enough to feed a model safely. That is unglamorous integration and platform work, and it is squarely in our wheelhouse. Concretely, it means knowing where authoritative data lives and retiring the copies; carrying access controls through to anything a model can retrieve; establishing data quality checks so that what reaches a model is current and correct; and writing down which data classes may leave your boundary for a third-party API and which may not.

None of this work is wasted if a particular model or vendor disappoints, which, this early in the cycle, some will. Pipelines, governance, and clean source systems pay for themselves in ordinary analytics even before any model touches them.

## How we are running pilots

We are running short discovery sprints with several clients to identify two or three narrow, measurable use cases. Small scope, real evaluation criteria, clear data boundaries. That is how pilots survive contact with production. The shape of a good candidate use case:

- A task that is genuinely high-volume and language-heavy, such as summarizing support tickets or drafting first-pass responses, not a vague ambition to "add AI."
- A measurable baseline, so the pilot can be judged against the current process in hours saved or accuracy achieved.
- A human in the loop wherever the output reaches a customer or a regulator.
- Data inputs the organization already governs, so the pilot does not require an exception to security policy.

A pilot that passes these filters earns a path to production. One that cannot state its evaluation criteria is a demo, however polished.

The pressure to have an AI answer is not going away this year. The leaders who come out ahead will be the ones who spent the pressure on foundations. That foundational work, data platforms, integration, governance, is what we build, and it is the least regrettable line item on a 2023 roadmap.
