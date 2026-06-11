---
layout: post
title: "Showcase: phased Azure migration for a regional insurance carrier"
date: 2023-03-14
category: Migration
excerpt: "A three-phase datacenter exit moved 140 workloads to Azure with no unplanned downtime."
---

We recently completed a phased Azure migration for a regional insurance carrier exiting two leased datacenters. The engagement covered roughly 140 workloads: policy administration, document management, and a long tail of departmental applications. The driving constraints were a fixed lease expiration, a regulator who would want to see change control on the core systems, and an internal IT team that had to keep running daily operations throughout.

## Discovery before anything moved

We spent the first six weeks on discovery and dependency mapping before a single workload moved. Automated discovery tooling gave us the inventory; interviews with application owners gave us the truth. The two disagreed often. We found batch jobs on servers nobody had claimed, a document workflow that depended on a file share three teams thought was retired, and integration points with the policy administration system that existed in no diagram.

Every workload landed in one of four buckets: rehost, replatform onto managed services, retire, or defer. About a tenth of the estate was retired outright, which is typical; nothing reduces migration cost like deleting the work.

## Three phases, in order of risk

Our approach was deliberately unexciting. Phase one rehosted low-risk workloads, departmental tools and internal reporting, to validate networking, identity, and backup patterns against the carrier's hub-and-spoke Azure landing zone. Anything we got wrong here was cheap to get wrong, and we did find issues: a DNS forwarding gap and a backup retention policy that did not match the written standard. Both were fixed before anything important depended on them.

Phase two moved the regulated core, policy administration and document management, under a defined change-control window with the carrier's compliance team in the room. Each cutover had a rehearsed runbook, a tested rollback path, and explicit success criteria agreed before the weekend started. Two cutovers were postponed when pre-checks failed; postponing was treated as the process working, not failing.

Phase three decommissioned the on-premises infrastructure and right-sized the landed estate. Rehosted VMs are almost always overprovisioned because they inherit hardware-era sizing, so we resized against observed utilization, applied reserved instances to the steady core, and shifted several services to managed equivalents. That work cut projected run costs by roughly a fifth against the initial landed bill.

## What made the weekends boring

Across all three phases there was no unplanned downtime. The reasons were unglamorous:

- Dependency maps were validated by application owners, not just scanned.
- Every cutover runbook was rehearsed at least once in a non-production pass.
- Rollback criteria were written down before each migration weekend, with a named decision-maker.
- The internal team executed alongside us from phase one, so by phase three they were leading cutovers and we were reviewing.

The lesson we keep relearning: migrations fail on dependencies, not on tooling. Six weeks of discovery and dependency mapping up front made the cutover weekends boring, which is exactly what they should be.

For organizations facing a datacenter exit with a date attached, the sequencing above is the playbook we bring, adapted to the estate in front of us. The earlier discovery starts, the more options remain open when the lease clock gets loud.
