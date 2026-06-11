---
layout: post
title: "The accessibility findings we keep seeing"
date: 2023-07-11
category: App Design
excerpt: "Five recurring WCAG failures account for most of the remediation work in our app audits."
---

After a year of accessibility reviews across client web and mobile applications, the same five findings dominate our reports: insufficient color contrast, missing focus states, unlabeled form controls, keyboard traps in custom modals, and images without meaningful alternative text.

None of these are hard to fix. All of them are hard to fix at scale once they are embedded in dozens of screens, which is why we now bake accessibility checks into the component layer of every design system we build. A button that meets contrast and focus requirements once meets them everywhere it is used.

For teams starting from zero, we recommend an automated scan to triage, followed by manual keyboard and screen-reader passes on the top user journeys.
