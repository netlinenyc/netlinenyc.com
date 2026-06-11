---
layout: post
title: "DR tests that fail are the point"
date: 2023-12-07 17:21:00 -0500
author: "Rohan Krishnan"
category: Cloud
excerpt: "A disaster recovery plan that has never failed a test has probably never been tested honestly."
---

This quarter we ran disaster recovery exercises with three clients. All three failed their first test. We consider all three engagements successful, and we want to explain why that sentence is not spin.

## Three failures, three gifts

One client discovered that database backups restored cleanly but application secrets did not exist in the recovery region. The restore drill produced a healthy database and an application that could not authenticate to it. The fix was an afternoon of work replicating the secrets store; finding the gap during a real regional outage would have added hours to an incident measured in revenue per minute.

Another found that their documented four-hour RTO assumed a runbook step only one departed employee knew. The runbook said "re-point the integration layer," and nobody in the room could expand that sentence into commands. The knowledge had walked out the door eight months earlier, and the document had quietly become fiction.

The third learned their DNS failover had a manual approval no one was on call to give. The technical mechanism worked exactly as designed; the process around it assumed a person who was not part of the on-call rotation. Automation with a human bottleneck inherits the availability of the human.

## Why untested plans rot

None of these organizations was careless. All three had written plans, budgeted recovery infrastructure, and stated RTOs that leadership believed. The plans were simply built on assumptions that drifted: an employee left, a secrets manager was adopted after the runbook was written, an approval step was added during a security review. DR plans decay at the speed of organizational change, not at the speed of infrastructure change, which is why even a technically static environment needs regular testing.

A test that passes on the first attempt deserves suspicion before celebration. In our experience it usually means the scope was trimmed to what was known to work, the people who maintain the systems ran the exercise from memory rather than from the runbook, or both.

## Making the exercise honest

Every one of this quarter's findings was cheap to fix once visible. The discipline is in surfacing them on a calm Tuesday instead of during an outage. Our standing guidance:

- Test recovery at least twice a year, and treat the calendar entry as immovable as a board meeting.
- Rotate who runs the exercise, so the runbook is executed by someone who cannot fill its gaps from memory.
- Treat the runbook as code that either executes or gets fixed; every ambiguity found during a drill becomes a pull request before the drill is closed.
- Time the exercise against the stated RTO and report the real number upward, even when it is unflattering.

The goal of a DR program is not a clean test report. It is the steady conversion of unknown failure modes into known, fixed ones, twice a year, forever.

All three clients have their second exercises scheduled for spring, and we expect those to fail too, in smaller and more interesting ways. That trajectory, failures getting cheaper each round, is what a healthy recovery program looks like, and designing and running these exercises is some of the highest-leverage work in our cloud practice.
