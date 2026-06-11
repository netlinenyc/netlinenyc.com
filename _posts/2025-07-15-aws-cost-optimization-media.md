---
layout: post
title: "Showcase: cutting an AWS bill by a third for a media company"
date: 2025-07-15 13:53:00 -0500
author: "Priya Sharma"
category: Cloud
excerpt: "A focused eight-week optimization reduced a digital media company's AWS spend by 34 percent with no architecture changes."
---

We recently completed an eight-week cost optimization for a digital media company whose AWS bill had doubled in eighteen months while traffic grew far more modestly. The divergence between those two curves is the classic signature of drift: not one bad decision, but an accumulation of provisioning choices that were each reasonable once and never revisited. Leadership's question was whether the bill reflected the business or reflected neglect. It was mostly neglect, which is the good outcome, because neglect is fixable in weeks.

## What we found

The first two weeks were diagnosis: full allocation of spend to services and teams, then a ranked list of gaps between what was provisioned and what was used. No heroics were required, and we want to underline that, because cost engagements are often imagined as deep architectural surgery. The findings were ordinary:

- A fleet of instances sized for a launch-day traffic peak that never recurred, still running at that size fourteen months later, with utilization graphs that made the case by themselves.
- Cold media assets, including years of published video and image masters with predictable, near-zero access patterns, sitting in standard storage rather than archival tiers.
- An always-on staging environment that mirrored production around the clock, used almost exclusively during business hours.
- A logging misconfiguration writing debug-level output at production volume, an expensive setting that had survived since an incident investigation a year prior.
- Commitment coverage, including reserved capacity and savings plans, purchased against the old, inflated footprint and poorly matched to actual usage.

## What we changed

Execution was deliberately conservative, because a cost project that causes an outage is a net loss. We right-sized the over-provisioned fleet in stages, watching performance at each step. Cold assets moved to archival storage tiers under lifecycle policies that will keep applying to new content. Staging now sleeps outside business hours and wakes on demand, with an override for off-hours release work. The logging configuration was corrected in an afternoon, which was the single fastest payback of the engagement. Last, and only after the cleanup settled, we restructured commitment coverage around the workloads that survived, since committing to the pre-cleanup footprint would have locked in the waste.

Sequencing matters here: optimize first, commit second. We see the reverse order often, and it converts savings instruments into anchors.

## The result, and the part that lasts

Net result: a 34 percent reduction in monthly spend, zero architecture changes, zero user-facing impact. The engineering team's day-to-day work was untouched except for the staging schedule, which nobody has complained about.

The deeper fix was procedural. We left behind a weekly cost review, a thirty-minute session where the team looks at spend by service against the prior week and asks about anything that moved. The client now runs it without us. Drift is not an event; it is a default, and the review is what keeps the curve from quietly bending upward again. Six weeks after handoff, the team caught and reversed a regression on their own, which is exactly what the process is for.

Most cloud bills that have doubled without a corresponding business reason contain a result like this one. An eight-week, low-risk pass is usually enough to find it, and it is among the most predictable engagements we run.
