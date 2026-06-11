---
layout: post
title: "Multi-cloud: a reality check"
date: 2024-11-06
category: Cloud
excerpt: "Most organizations claiming a multi-cloud strategy actually have a primary cloud and a collection of accidents."
---

We work across AWS, Azure, and GCP daily, so we have no platform allegiance in this debate, and no incentive to talk anyone out of any particular cloud. With that disclosure: most multi-cloud strategies we review are not strategies. They are one primary cloud plus an acquisition that came with another, or a single team's preference that calcified into architecture, or a procurement hedge from 2019 that nobody has revisited. The word "strategy" appears in the slide deck; the environment tells a different story.

## How accidental multi-cloud actually happens

The pattern is consistent enough that we can usually guess the history before the client tells it. A company standardizes on one provider. Then an acquired team arrives with its stack on another and a migration that never gets funded. A data science group picks a third for one managed service and grows roots. Within two years the organization is running three identity systems, three networking models, and three sets of security tooling, each at partial maturity, and the security team is asked to certify all of it with a headcount sized for one.

None of these decisions was unreasonable in the moment. The cost is the aggregate: every operational capability, including monitoring, incident response, access reviews, and cost allocation, must now be built and maintained in multiplicate, or left weak on the clouds that get less attention. Weak is what we usually find.

## The reasons that actually hold up

Genuine reasons to run multiple clouds exist, and we have helped clients act on each of them:

- Regulatory mandates or customer data residency requirements that a single provider cannot satisfy in every jurisdiction that matters.
- A specific managed service that is materially better for a core workload, where "materially" survives a real comparison rather than a benchmark blog post.
- Concentration risk policies in regulated industries, where the requirement is written down and audited rather than felt.

Notice what is not on the list: portability as an abstract virtue. The architecture that runs identically on any cloud is the architecture that uses none of them well. Building to the lowest common denominator means forfeiting the managed databases, queues, and serverless platforms that justify cloud pricing in the first place, and paying instead to operate your own portable substitutes. You assume the operational burden of multi-cloud on day one to hedge a migration you will probably never perform.

## What we recommend instead

Our guidance is unglamorous. Pick a primary cloud and go deep: use its managed services without guilt, build operational excellence on one platform, and let your team develop real fluency rather than three shallow familiarities. Then document, in writing, the specific conditions under which you would add a second provider, such as a named regulatory trigger, a defined workload profile, or a concrete service gap. Review that document annually. If the conditions arrive, you act deliberately, with a funded plan. If they never arrive, you have lost nothing.

Optionality you never exercise is just cost. If your environment has drifted into multi-cloud by accident rather than by decision, the useful first step is an honest inventory of what each platform is actually doing for you, and that is an assessment we are well placed to run, on whichever clouds you happen to have.
