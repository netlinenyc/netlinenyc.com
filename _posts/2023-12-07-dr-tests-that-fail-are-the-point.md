---
layout: post
title: "DR tests that fail are the point"
date: 2023-12-07
category: Cloud
excerpt: "A disaster recovery plan that has never failed a test has probably never been tested honestly."
---

This quarter we ran disaster recovery exercises with three clients. All three failed their first test. We consider all three engagements successful.

One discovered that database backups restored cleanly but application secrets did not exist in the recovery region. Another found that their documented four-hour RTO assumed a runbook step only one departed employee knew. The third learned their DNS failover had a manual approval no one was on call to give.

These are exactly the findings a test exists to surface, and every one was cheap to fix once visible. Our standing guidance: test recovery at least twice a year, rotate who runs the exercise, and treat the runbook as code that either executes or gets fixed.
