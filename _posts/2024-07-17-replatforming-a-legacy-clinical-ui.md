---
layout: post
title: "Showcase: replatforming a legacy clinical scheduling UI"
date: 2024-07-17 12:08:00 -0500
author: "Priya Sharma"
category: App Design
excerpt: "We rebuilt a fifteen-year-old scheduling interface for a healthcare network without pausing daily operations."
---

We recently completed a UI replatforming for a multi-site healthcare network whose scheduling system dated to the late 2000s. The backend logic was sound: fifteen years of scheduling rules, payer constraints, and clinician availability handling that nobody wanted to rewrite, because it worked. The interface was the problem. It required staff training measured in weeks, it depended on keyboard sequences that existed nowhere else in the organization, and it could not run on the tablets the network had purchased for its intake desks.

## Why we ruled out a rewrite

The first conversation any team has about a system like this is whether to rewrite it whole. We argued against it, for reasons that apply broadly. A big-bang rewrite would have meant freezing the legacy system's behavior for a year while a replacement caught up, then betting daily clinical operations on a single cutover weekend. Scheduling is not a system that tolerates a bad launch; a missed appointment block is a patient who does not get seen.

The backend gave us a better option. Its scheduling logic was already exposed through a service layer that the legacy screens called. That meant the interface could be replaced without touching the rules underneath it.

## The strangler approach in practice

We built a modern web frontend on an accessible component library and put a routing layer in front of both interfaces. Each scheduling workflow, such as new-patient booking, recurring visits, or provider calendar management, was rebuilt as a discrete unit, validated against the legacy behavior, and switched over independently. The mechanics that made it work:

- The routing layer sent each staff member to the new or old screen per workflow, so pilots could run with a single site before network-wide rollout.
- The legacy UI stayed available as a fallback for every workflow until the replacement had run cleanly for two full scheduling cycles.
- We instrumented both interfaces, so we could compare task completion times rather than rely on opinion.
- A standing weekly session with scheduling staff fed real complaints into the next workflow's design instead of a backlog nobody read.

Twelve workflows moved over five months. No workflow had to be rolled back, though two were held an extra cycle while we fixed issues the pilots surfaced. Daily operations never paused.

## What changed for the client

Training time for new scheduling staff dropped from three weeks to four days, which mattered more than it sounds: the network's intake desks see meaningful seasonal turnover, and the old training burden had become a hiring constraint. The tablet limitation disappeared entirely, since the new frontend is responsive and touch-capable by default. Intake staff now schedule from the desk where the conversation happens rather than walking back to a fixed terminal.

The accessible component library earned its keep too. Focus management, contrast, and keyboard navigation came largely for free, and the network's compliance team signed off on accessibility without a separate remediation project.

The lesson we keep relearning on engagements like this is that age is not the problem; coupling is. A fifteen-year-old backend with a clean service boundary is an asset. If you are staring at a legacy interface and assuming the only path forward is a rewrite, it is worth an honest look at where the seams actually are. That assessment is a small engagement, and it is one we do often.
