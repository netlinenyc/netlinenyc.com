---
layout: post
title: "Showcase: full datacenter exit to Azure for a specialty manufacturer"
date: 2026-01-21 09:09:00 -0500
author: "Rohan Krishnan"
category: Migration
excerpt: "An eleven-month program moved a specialty manufacturer's entire estate to Azure ahead of a datacenter lease expiry."
---

We recently completed an eleven-month program moving a specialty manufacturer's complete IT estate to Azure, driven by a datacenter lease expiry that set an immovable deadline. Deadlines of this kind change the character of a migration: there is no option to defer the hard parts, and every scheduling decision has to assume something will go wrong, because over eleven months something always does.

## The estate

The environment was typical of the category, which is to say genuinely difficult in places. An ERP system with deep customizations accumulated over a decade sat at the center of everything: finance, inventory, and order flow all ran through it. File servers held two decades of CAD data, with terabytes of design history that engineering retrieves unpredictably and cannot lose. Shop-floor integrations connected production equipment to scheduling and quality systems, and those links could not tolerate latency surprises without risking line stoppages. And the existing backup infrastructure was of uncertain reliability, which meant we could not treat it as a safety net for anything that mattered.

## Sequencing around the ERP

We sequenced the entire program around the ERP, because it carried the most risk and the least tolerance for an extended outage. Everything that could move before it did: file servers migrated early with continuous synchronization keeping CAD data current until cutover, peripheral applications moved in waves, and the first months also fixed the foundations, including a verified backup capability in Azure, since migrating on top of unreliable backups is gambling with the whole company.

The ERP cutover itself was rehearsed three times in an isolated Azure environment, end to end, against realistic data volumes. The rehearsals were not ceremony. The first surfaced a data migration step that ran four times longer than estimated, which would have blown the production window; the second validated the fix and uncovered an integration ordering issue; the third ran clean, which is what earned the production cutover its go decision. Our rule on migrations like this is that a cutover that has not been rehearsed has not been planned, merely described.

For the shop floor, we used Azure ExpressRoute to provide private connectivity with predictable performance, and we measured rather than assumed: latency between the plant and the Azure region was tested under load before any production integration moved, and the observed bounds were written into the acceptance criteria for each cutover. Manufacturing equipment does not care about cloud architecture diagrams; it cares about round-trip times.

## Finishing early on purpose

The final rack was powered down four weeks before lease end. That buffer was not luck; it was the plan. We scheduled the program pessimistically from the start, holding back contingency weeks that optimistic timelines would have spent on paper. The buffer absorbed two vendor delays, including a licensing transfer and a hardware-dependent data extraction, that would otherwise have been crises negotiated against a landlord's deadline. Instead they were inconveniences absorbed by schedule that existed for exactly this purpose.

Deadline-driven migrations reward pessimistic scheduling, rehearsed cutovers, and an honest early look at the scariest system rather than the easiest one. For organizations facing their own lease expiry or hardware refresh cliff, the eleven months this took is a realistic figure for an estate of this shape, and planning such programs end to end is core work for our migration practice.
