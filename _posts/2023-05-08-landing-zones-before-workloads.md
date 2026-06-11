---
layout: post
title: "Build the landing zone before the first workload"
date: 2023-05-08
category: Cloud
excerpt: "Identity, network topology, logging, and guardrails should exist before the first production workload arrives."
---

The most expensive cloud mistake we see is migrating workloads into an account structure that was never designed. Retrofitting identity boundaries, network segmentation, and centralized logging after fifty workloads are live costs multiples of doing it first.

Our landing zone baseline is consistent across AWS, Azure, and GCP: an organization hierarchy that maps to environments and data sensitivity, federated identity with no standing admin credentials, hub-and-spoke or shared VPC networking, centralized audit logs, and guardrail policies enforced as code with Terraform.

None of this is glamorous, and clients sometimes push to skip ahead to the visible wins. We hold the line, because every week spent on foundations removes a future quarter of remediation.
