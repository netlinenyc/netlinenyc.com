---
layout: post
title: "IAM hygiene: the unglamorous control that decides your breach story"
date: 2024-06-04
category: Cloud
excerpt: "Most cloud incidents we review trace back to over-permissioned identities and forgotten credentials, not exotic exploits."
---

When we run cloud security reviews, identity findings outnumber everything else combined. The pattern is consistent across AWS, Azure, and GCP: human users with standing admin access, service accounts with wildcard permissions copied from a tutorial, access keys older than the employees who created them, and no review process for any of it.

Our baseline hygiene list is short. Federate all human access through SSO with MFA. Eliminate long-lived keys in favor of short-lived credentials. Grant roles to groups, never individuals. Scope service identities to what they actually call, which your audit logs will tell you. Review access quarterly and treat the review as a deletion exercise.

None of this requires new products. It requires deciding it matters.
