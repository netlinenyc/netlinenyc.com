---
layout: post
title: "Showcase: HIPAA-ready AWS environment for a telehealth provider"
date: 2025-02-25
category: Migration
excerpt: "We migrated a telehealth platform onto a HIPAA-aligned AWS landing zone with auditable controls from day one."
---

We recently completed a migration for a growing telehealth provider whose platform had outgrown a single-account cloud setup assembled during their startup phase. The environment was typical of a company that had grown faster than its infrastructure: production, staging, and experiments sharing one AWS account, IAM permissions accumulated rather than designed, and protected health information flowing through systems that had never been formally scoped. The forcing event was commercial. A payer contract, large enough to change the company's trajectory, required demonstrable HIPAA safeguards, with the emphasis on demonstrable.

## The landing zone

We built a multi-account AWS landing zone, organized so that the compliance boundary is an account boundary rather than a tagging convention. The core elements:

- PHI workloads isolated in dedicated accounts, with non-PHI services, tooling, and experiments kept structurally outside the boundary, which shrinks the audit scope to what actually handles patient data.
- Encryption everywhere with customer-managed KMS keys, so key policy and rotation are under the client's control and inspectable on demand.
- VPC-only data paths for PHI, using private endpoints for AWS services so protected data never transits the public internet, even between managed services.
- Centralized audit logging into a locked-down account, with retention aligned to the client's written policy and integrity controls on the logs themselves.
- Break-glass access procedures for production emergencies that grant time-boxed elevated access and leave a complete trail, replacing the standing admin credentials that had accreted over the years.

None of these controls is exotic. The value was in assembling them coherently, as a landing zone the client's team can extend, rather than as a checklist of point fixes.

## Migrating without disrupting care

A telehealth platform has no convenient downtime; clinicians and patients use it across all hours. We migrated application workloads over six weekends, one service group at a time, with maintenance windows announced to clinicians well in advance and kept deliberately short. Each cutover had a rehearsed rollback, and we used the early, lower-risk weekends to validate the runbook before the weekends that carried the core video and scheduling services. Two cutovers surfaced surprises, including a hardcoded endpoint in a background job being the memorable one, and both were resolved within their windows. No patient-facing incident occurred during the program.

## Documentation as a byproduct, not a project

The phase clients usually dread is the compliance documentation. Here it nearly wrote itself, because the controls were real and inspectable: the encryption policy describes keys that exist, the access control narrative describes IAM boundaries you can read in Terraform, and the audit logging section links to the actual log archive configuration. When the payer's security reviewers asked follow-up questions, the answers were screenshots and configuration excerpts, not promises.

That is the order of operations we insist on: build the control, then describe it, never the reverse. Documentation written ahead of reality becomes a list of commitments someone must later scramble to honor, usually during an audit.

The client signed the payer contract, and their engineers now provision new services inside the landing zone's guardrails without our involvement, which is the real test of whether an environment was built well. For healthcare companies approaching the same threshold, this pattern is repeatable, and it is one of the engagements we know best.
