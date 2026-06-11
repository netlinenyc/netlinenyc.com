---
layout: post
title: "WCAG 2.2 as a forcing function for UI cleanup"
date: 2025-11-18 09:25:00 -0500
author: "Michael Reed"
category: App Design
excerpt: "Teams treating WCAG 2.2 alignment as pure compliance are missing a cheap opportunity to fix long-standing UI debt."
---

More of our clients are being asked, by enterprise customers and by counsel, to demonstrate WCAG 2.2 alignment. The requests arrive through procurement questionnaires, contract renewals, and occasionally a demand letter, and the reflexive organizational response is to treat the work as a compliance tax: scope it narrowly, fund it grudgingly, and route it around the product roadmap. We have been arguing for a different frame, because the narrow version leaves most of the value on the table.

## The overlap nobody prices in

Look at what the newer success criteria actually ask for. Focus indicators that remain visible. Interactive targets large enough to hit reliably. Dragging operations with single-pointer alternatives. Not asking users to re-enter information the system already has. Authentication that does not depend on transcribing codes or solving puzzles.

Now compare that list to the usability complaints in any mature product's backlog. The overlap is nearly total. These criteria are not an external standard bolted onto your product; they are a checklist of ordinary interaction debt, the kind that accumulates over years of shipping and that never quite wins a prioritization meeting on its own.

Every remediation we have run this year confirmed it. The work ended up fixing problems users had been quietly tolerating: tap targets too small on mobile, focus indicators removed for aesthetics years ago and never restored, forms that ask for the same information twice because two teams built two steps. None of these had ever been filed as accessibility issues. All of them were friction for every user, with users relying on assistive technology simply hitting them hardest.

## Fund it once, not twice

Here is the failure mode we want clients to avoid. The compliance project gets scoped to the letter of the audit: fix the flagged elements, generate the conformance report, declare victory. Eighteen months later, a UX initiative re-opens the same screens to fix the same interactions, because the compliance work was done with no design involvement and aimed at the report rather than the experience. The organization pays twice for one set of fixes.

Our suggestion is structural: fund the work once, as a usability project with an accessibility acceptance bar. Practically, that means:

- Audit against WCAG 2.2, but triage the findings alongside existing UX debt, since they are usually the same items wearing different labels.
- Fix at the component level, in the design system, so a corrected focus style or target size propagates everywhere rather than being patched per screen.
- Make the acceptance criteria accessibility-conformant, with keyboard paths, visible focus, and adequate targets, so the usability work produces the compliance evidence as a byproduct.
- Add automated accessibility checks to CI so the debt does not silently re-accumulate after the project ends.

The conformance documentation that enterprise customers want falls out of this approach naturally, and it describes a product that is genuinely better rather than minimally defensible.

A compliance demand is rarely welcome, but it is leverage: a funded mandate to fix things the roadmap kept deferring. Spent well, it buys both the signed conformance report and a measurably smoother product. Helping teams spend it well, rather than twice, has become a recurring part of our app design work this year.
