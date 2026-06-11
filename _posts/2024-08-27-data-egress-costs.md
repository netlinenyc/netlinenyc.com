---
layout: post
title: "Data egress: the line item nobody budgets for"
date: 2024-08-27 09:03:00 -0500
author: "Arjun Mehta"
category: Cloud
excerpt: "Egress charges quietly shape architecture decisions, and they deserve a place in every design review."
---

In cost reviews this year, data egress has been the most common surprise line item. It rarely dominates a bill, which is exactly why it escapes attention: a charge that is four percent of spend does not trigger anyone's alarm. But egress grows silently, it compounds with data volume rather than with traffic, and it constrains future choices in a way most line items do not. The more data you accumulate in one provider, the more expensive every exit path becomes, whether that exit is a migration, a new analytics vendor, or a disaster recovery copy.

## Where the charges actually come from

When we trace egress costs in client environments, the same offenders recur. Almost none of them were deliberate decisions; they were defaults nobody revisited.

- Cross-region replication enabled during an early high-availability push and never re-examined as data volumes grew tenfold.
- Chatty service-to-service traffic crossing availability zones, often because placement was random rather than wrong on purpose.
- Analytics and observability exports to third-party tools, where every log line and event leaves the provider's network at metered rates.
- Backup copies shipped to another cloud "for safety" at full transfer prices, providing real resilience but at a cost nobody attributed to the resilience budget.

Each of these is defensible in isolation. The problem is that they were never priced when the decision was made, so nobody weighed the alternative.

## The strategic cost is bigger than the monthly one

The monthly charge is the visible half. The invisible half is gravity: organizations with hundreds of terabytes parked in one provider discover that any architectural change involving that data carries a five- or six-figure toll. We have watched a client defer a genuinely better analytics platform for a year because the one-time transfer cost was easier to veto than a recurring subscription. The egress fee did not just cost money; it shaped the roadmap.

Recent provider commitments to waive egress fees for customers leaving a platform entirely help at the margins, and we credit the regulatory pressure that produced them. But the waivers apply to full exits, not to the day-to-day flows above. Routine transfer pricing is unchanged, and routine transfers are where the money goes.

## What we now do about it

Our architecture review checklist includes an explicit egress estimate for every design that moves data across a region, zone, provider, or out to a vendor. The exercise takes about an hour: identify the flows, estimate monthly volume honestly rather than optimistically, and multiply by published rates. The number is rarely precise and does not need to be. It needs to exist before the decision is made.

That hour has changed real outcomes. It has moved an analytics export from streaming to compressed daily batches, collapsed a cross-zone chat between two services into colocated deployments, and in one case justified paying more for a managed service inside the provider because the alternative's transfer costs erased its sticker advantage.

Egress is not a reason to avoid moving data; it is a reason to price the movement before you commit to it. If your last architecture review did not include a transfer cost estimate, that is a one-hour gap worth closing, and it is the kind of review we run with clients regularly.
