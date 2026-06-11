---
layout: post
title: "Data egress: the line item nobody budgets for"
date: 2024-08-27
category: Cloud
excerpt: "Egress charges quietly shape architecture decisions, and they deserve a place in every design review."
---

In cost reviews this year, data egress has been the most common surprise line item. It rarely dominates a bill, but it grows silently and it constrains future choices: the more data you accumulate in one provider, the more expensive every exit path becomes.

The recurring offenders we find are cross-region replication nobody remembers enabling, chatty service-to-service traffic crossing availability zones, analytics exports to third-party tools, and backup copies shipped to another cloud "for safety" at full transfer rates.

Recent provider commitments to waive egress fees for customers leaving entirely help at the margins, but day-to-day transfer pricing is unchanged. Our practice now includes an explicit egress estimate in every architecture review. It takes an hour and it has changed real decisions.
