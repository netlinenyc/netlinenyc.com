---
layout: post
title: "SOC 2 readiness in ninety days: what it actually takes"
date: 2023-10-24
category: Insights
excerpt: "A SaaS client reached SOC 2 Type I readiness in one quarter by treating controls as engineering work, not paperwork."
---

We recently guided a New York SaaS company through SOC 2 Type I readiness in a single quarter. The trigger was familiar: a flagship enterprise prospect made SOC 2 a condition of signing, and the deal timeline did not care about the engineering roadmap. Ninety days is tight but achievable for a company of that size, provided the work is framed correctly from day one.

## Controls are engineering work

The work was less about documents and more about engineering: centralizing identity, enforcing MFA and SSO everywhere, turning on org-wide audit logging, formalizing change management through the pull-request process they already used, and standing up vendor and access reviews on a calendar.

That last point, building on what the team already did, was the biggest accelerator. The client had solid pull-request discipline; we did not impose a new change-management regime, we documented the existing one, tightened branch protections, and made approvals and CI checks mandatory rather than customary. Auditors do not require a specific process. They require that your stated process is real and evidenced, and a process the team already follows generates evidence for free.

## How the ninety days actually broke down

The quarter divided into three rough phases. The first month was a gap assessment and the identity work: every SaaS tool and cloud account moved behind SSO, MFA enforced, shared accounts eliminated, and offboarding wired into the HR workflow. Identity touches the most controls, so it went first.

The second month covered logging, monitoring, and the formalization work: org-wide audit logs centralized and retained, alerting on the events that matter, policies written, and the review calendars established. The third month was evidence collection, internal dry runs against the control list, and remediation of the stragglers, with the auditor reviewing scope before anything was final.

The compliance platform tooling helped with evidence collection, but tooling does not create controls. Engineering discipline does. We watched the platform's dashboard turn green only after the underlying work was done, never before, which is exactly the relationship it should have.

## What we tell teams facing the same deadline

Our practical advice for teams facing a customer-driven SOC 2 deadline:

- Start with access control and logging; they underpin more of the control set than anything else and take the longest to retrofit.
- Write policies that describe what you actually do, not what a template imagines; auditors test the gap between paper and practice.
- Get the auditor involved earlier than feels comfortable, ideally before remediation starts, so scope surprises surface in week three rather than week eleven.
- Assign one accountable owner internally; compliance projects with diffuse ownership stall in exactly the way this one did not.

One more expectation worth setting: Type I attests to control design at a point in time, and the Type II observation window starts afterward. The habits installed in the readiness quarter, the reviews, the logging, the disciplined change process, are what carry a company through Type II without a second fire drill.

SOC 2 has become table stakes for selling software to enterprises, and the readiness work doubles as a genuine security upgrade when it is done as engineering. That framing, and the hands-on work behind it, is how we run these engagements.
