---
layout: post
title: "Showcase: replatforming a legacy clinical scheduling UI"
date: 2024-07-17
category: App Design
excerpt: "We rebuilt a fifteen-year-old scheduling interface for a healthcare network without pausing daily operations."
---

We recently completed a UI replatforming for a multi-site healthcare network whose scheduling system dated to the late 2000s. The backend logic was sound; the interface required staff training measured in weeks and could not run on tablets used at intake desks.

Rather than a risky big-bang rewrite, we used a strangler approach: a modern web frontend, built on an accessible component library, replaced the legacy screens one workflow at a time behind a routing layer. Scheduling staff switched gradually, and the old UI remained available as a fallback until each workflow proved itself.

Twelve workflows moved over five months. Training time for new staff dropped from three weeks to four days, and the tablet constraint disappeared entirely.
