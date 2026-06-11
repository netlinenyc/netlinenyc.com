---
layout: post
title: "NetLine NYC launches a cloud security review practice"
date: 2023-11-15
category: Company
excerpt: "We are formalizing the security assessments we have been doing informally into a standalone practice area."
---

For the past two years, nearly every migration and platform engagement we have delivered included an informal security pass: IAM review, network exposure check, logging coverage, encryption posture. We did it because handing over an estate without looking at those four things felt negligent, and because the findings were never empty. Clients kept asking for that work on its own, so we are making it official.

## What the engagement looks like

NetLine NYC now offers cloud security reviews as a standalone engagement across AWS, Azure, and GCP. The format is a fixed-scope, two-to-three-week assessment producing a prioritized findings report and a remediation plan sized for the client's team, with optional hands-on remediation support.

The scope is deliberately bounded. We review identity and access management, network exposure and segmentation, logging and detection coverage, encryption posture, and the configuration of the highest-value data stores. We do not attempt to be a penetration test, a SOC 2 audit, or an application security review; those are different instruments, and we say so when one of them is what a client actually needs.

The deliverable is built for two audiences at once. Engineers get specific findings with reproduction details and concrete fixes, most of them expressible in Terraform. Leadership gets a one-page risk summary in plain language and a remediation plan sequenced by impact and effort, sized honestly for the team that has to execute it. A forty-item list with no sequencing is how findings reports go unread, and we have read enough of those to refuse to write one.

## Why fixed scope and fixed time

We settled on the two-to-three-week format after running variations of this work informally for two years. Open-ended security assessments expand to fill whatever budget exists, and the marginal findings past week three are rarely the ones that change a client's risk picture. The serious problems in a cloud estate, the standing admin access, the public storage bucket, the logging gap, the unrotated keys, surface early when you know where to look. A bounded engagement keeps the price predictable and keeps our attention on what matters most.

The optional remediation support exists because findings reports famously go stale in a drawer. Some clients have the bench to execute the plan themselves; others want us to pair with their engineers for a few weeks and clear the critical items together. Both are fine outcomes. An unremediated report is not.

## Staffing the practice

Two senior engineers have joined the firm to anchor the practice. Both come from backgrounds running cloud security in production environments rather than from audit, which matches how we want these reviews to read: written by people who have carried the pager, with findings that respect the operational reality of the teams receiving them.

We expect this to be a significant part of our work in 2024. The demand signal is already clear from our existing migration and platform clients, and the questions arriving in our inbox suggest it extends well beyond them.

If your organization has been running in the cloud for a few years and nobody has looked at the estate with fresh eyes, that is precisely the situation this practice was built for. We are scheduling reviews for the first quarter of 2024 now.
