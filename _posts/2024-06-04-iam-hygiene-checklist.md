---
layout: post
title: "IAM hygiene: the unglamorous control that decides your breach story"
date: 2024-06-04
category: Cloud
excerpt: "Most cloud incidents we review trace back to over-permissioned identities and forgotten credentials, not exotic exploits."
---

When we run cloud security reviews, identity findings outnumber everything else combined. The pattern is consistent across AWS, Azure, and GCP: human users with standing admin access, service accounts with wildcard permissions copied from a tutorial, access keys older than the employees who created them, and no review process for any of it.

## Why identity is where incidents start

The post-incident reports we are asked to review almost never feature a novel exploit. They feature a leaked access key with far more permission than its workload needed, a contractor account that survived the contract by two years, or an admin credential reused from a breached third-party service. The attacker's hardest step was finding the credential; everything after was just using permissions that should never have existed.

This is also why IAM hygiene is the highest-leverage security spend for most organizations. Sophisticated detection tooling watches for the abuse of excessive access. Hygiene removes the excessive access, which is cheaper, quieter, and works against attackers you never detect.

## How estates rot

None of the findings above come from incompetence. They come from accumulation. Permissions are granted under deadline pressure and never revisited, because revoking access risks breaking something while granting it never does. A tutorial's wildcard policy works on the first try, so it ships. An access key is created for a quick integration test and outlives three reorganizations. Each individual decision is defensible; the compounding is the problem. Without a forcing function that removes access, every cloud estate drifts monotonically toward over-permission.

## The baseline list

Our baseline hygiene list is short, and none of it is novel:

- Federate all human access through SSO with MFA; the IdP becomes the single front door, and offboarding becomes one deactivation instead of a scavenger hunt.
- Eliminate long-lived keys in favor of short-lived credentials; workload identity and role assumption exist on all three major clouds, and a credential that expires in an hour is a categorically smaller prize than one that lasts years.
- Grant roles to groups, never individuals, so access maps to function and a role change is a group membership change rather than archaeology.
- Scope service identities to what they actually call, which your audit logs will tell you; all three providers can now generate least-privilege policies from observed activity, so the tedious part has been automated.
- Review access quarterly and treat the review as a deletion exercise; a review that removes nothing was a meeting, not a control.

A motivated team can implement this list in a quarter. The federation work is the heaviest lift; the rest is policy work and calendar discipline.

## Keeping it clean

The harder problem is staying clean, because the forces that rotted the estate the first time do not retire. The durable answers are structural: provision access through code and pull requests so grants are reviewed and revocable, set expirations on anything exceptional, and alert on the creation of long-lived keys so regressions surface in hours rather than at the next review.

None of this requires new products. It requires deciding it matters, and then building the small set of habits that keep the decision true. Identity findings are where our cloud security reviews consistently find the most risk and the fastest payback, and if you have not looked at your own estate's IAM posture in a year or more, that is the place to start.
