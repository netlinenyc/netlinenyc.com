---
layout: post
title: "Showcase: HIPAA-ready AWS environment for a telehealth provider"
date: 2025-02-25
category: Migration
excerpt: "We migrated a telehealth platform onto a HIPAA-aligned AWS landing zone with auditable controls from day one."
---

We recently completed a migration for a growing telehealth provider whose platform had outgrown a single-account cloud setup assembled during their startup phase. The driver was a payer contract requiring demonstrable HIPAA safeguards.

We built a multi-account AWS landing zone with PHI workloads isolated in dedicated accounts, encryption with customer-managed keys, VPC-only data paths, centralized audit logging with retention aligned to policy, and break-glass access procedures that leave a trail. Application workloads were migrated over six weekends with maintenance windows announced to clinicians in advance.

The compliance documentation nearly wrote itself because the controls were real and inspectable. That is the order of operations we insist on: build the control, then describe it, never the reverse.
