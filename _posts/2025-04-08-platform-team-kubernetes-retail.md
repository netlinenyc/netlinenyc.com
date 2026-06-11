---
layout: post
title: "Showcase: standing up a platform team for a retail group"
date: 2025-04-08
category: Cloud
excerpt: "We helped a retail group consolidate eleven snowflake Kubernetes clusters into a paved-road platform run by a four-person team."
---

We recently concluded a nine-month engagement with a multi-brand retail group whose engineering teams had each built their own Kubernetes environment. Eleven clusters, eleven ingress configurations, eleven upgrade backlogs, and eleven slightly different answers to every security question. No single decision had been wrong; each team had solved its own problem competently in isolation. The aggregate was the problem: duplicated effort everywhere, no shared leverage, and several clusters running Kubernetes versions old enough to be out of support, because upgrades competed with feature work on every team and lost.

## The fix was organizational first

The instinct on engagements like this is to start with the technology. We started with the operating model, because consolidating eleven clusters without changing who owns infrastructure just produces one large cluster that eleven teams still neglect.

We helped the client charter a four-person platform team with a written mandate: run the shared infrastructure, publish a paved road, and treat product teams as customers. The charter mattered as much as the headcount. It defined what the platform team owns, including clusters, networking, base observability, and upgrade cadence, and what it explicitly does not, meaning anything product-specific. It also established that the paved road would be the well-supported default rather than a mandate, with teams free to deviate if they accepted the operational burden themselves.

## The paved road

With the team chartered, we consolidated workloads onto three GKE clusters and built the road:

- Standard Terraform modules for provisioning, so a new service's infrastructure is a pull request rather than a project.
- Golden CI pipelines covering build, scan, and deploy, adopted by reference so improvements propagate to every team at once.
- Baseline observability with dashboards, logging, and alerting wired in by default, replacing the previous mix of per-team tooling.
- Namespace-level tenancy with sensible defaults: resource quotas, network policies, and pod security standards that teams inherit rather than configure.

Product teams kept full ownership of their services, including deployment, on-call, and performance. They gave up only the burden of running undifferentiated infrastructure, which none of them had wanted anyway. Migration ran brand by brand over roughly five months, with the platform team handling the moves and treating each one as a chance to harden the road.

## What the results looked like

Upgrade lag went from a worst case of five minor versions to none; the platform team now tracks GKE's release channel as routine work, invisible to product teams. Three clusters carry what eleven did, with corresponding savings in both spend and attention.

The signal we value most, though, is behavioral. Two teams that had openly resisted the consolidation, and had the strongest home-built setups, now file feature requests against the platform. Teams do not file feature requests against things they are merely tolerating; they file them against products they depend on and want improved. That is the adoption signal we watch for, and it arrived around month seven.

Platform engineering succeeds or fails on this dynamic far more than on tool selection. If your organization is accumulating snowflake clusters faster than it can maintain them, the fix is a chartered team and a credible paved road, and standing those up is work we have now done across several industries.
