---
layout: post
title: "Showcase: standing up a platform team for a retail group"
date: 2025-04-08
category: Cloud
excerpt: "We helped a retail group consolidate eleven snowflake Kubernetes clusters into a paved-road platform run by a four-person team."
---

We recently concluded a nine-month engagement with a multi-brand retail group whose engineering teams had each built their own Kubernetes environment. Eleven clusters, eleven ingress configurations, eleven upgrade backlogs.

The fix was organizational as much as technical. We helped the client charter a four-person platform team, then consolidated workloads onto three GKE clusters with a paved road: standard Terraform modules, golden CI pipelines, baseline observability, and namespace-level tenancy with sensible defaults. Product teams kept full ownership of their services; they gave up only the burden of running undifferentiated infrastructure.

Upgrade lag went from a worst case of five minor versions to none. More telling, two teams that had resisted the consolidation now file feature requests against the platform. That is the adoption signal we watch for.
