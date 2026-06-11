---
layout: post
title: "The accessibility findings we keep seeing"
date: 2023-07-11
category: App Design
excerpt: "Five recurring WCAG failures account for most of the remediation work in our app audits."
---

After a year of accessibility reviews across client web and mobile applications, the same five findings dominate our reports: insufficient color contrast, missing focus states, unlabeled form controls, keyboard traps in custom modals, and images without meaningful alternative text. Different industries, different tech stacks, different teams, and yet the findings list could be photocopied between engagements.

## Why the same five, everywhere

None of these failures comes from indifference. They come from defaults. Brand palettes are chosen for aesthetics and locked in before anyone runs a contrast check, so light gray text on white ships everywhere the palette ships. CSS resets strip the browser's focus outline because a designer found it ugly, and nothing replaces it. Custom dropdowns and modals are built from divs that look right and announce nothing, because the native elements were harder to style. Form labels become placeholder text that vanishes the moment a user starts typing. Alt text fields exist in the CMS and stay empty because no process requires them.

In other words, these are systemic outcomes, and systemic outcomes need systemic fixes.

## Fix the component, fix the application

None of these are hard to fix. All of them are hard to fix at scale once they are embedded in dozens of screens, which is why we now bake accessibility checks into the component layer of every design system we build. A button that meets contrast and focus requirements once meets them everywhere it is used. A modal that traps and returns focus correctly does so on every screen that opens it. A form field component that refuses to render without a label turns a manual audit finding into a build error.

This is the quiet argument for component libraries that we find most persuasive. Screen-by-screen remediation of a mature application is a long grind. Remediating twenty-five components and migrating screens onto them as feature work touches them is a fraction of the cost, and the fixes cannot regress one screen at a time.

## A starting sequence for teams at zero

For teams starting from zero, we recommend an automated scan to triage, followed by manual keyboard and screen-reader passes on the top user journeys. The workable order:

- Run an automated scanner such as axe or Lighthouse across the main flows; it will catch contrast, labeling, and alt-text issues cheaply.
- Unplug the mouse and complete your top three user journeys by keyboard alone; this surfaces focus and trap issues no scanner reliably finds.
- Repeat those journeys with VoiceOver or NVDA and listen to what the application actually announces.
- Fix at the component level wherever a finding repeats, and add the automated scan to CI so the floor cannot drop again.

Automated tooling typically catches less than half of real-world barriers, which is why the manual passes are not optional. But the combination, run on a handful of critical journeys rather than every screen, gives a small team a defensible and improving baseline within weeks.

Accessibility debt behaves like any other debt: cheapest to avoid, manageable to pay down early, expensive to ignore. Audits and component-level remediation of exactly this kind are a steady part of our design practice, and the five findings above are where we would tell any team to look first.
