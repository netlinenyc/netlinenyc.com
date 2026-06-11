---
layout: post
title: "Showcase: GCP data platform for a logistics operator"
date: 2024-01-22
category: Migration
excerpt: "We replaced a nightly batch warehouse with a streaming pipeline on GCP, cutting reporting latency from a day to minutes."
---

We recently wrapped a six-month engagement moving a regional logistics operator from an aging on-premises data warehouse to a managed platform on Google Cloud. The previous environment ran nightly batches; operations teams worked with data that was always a day old. In a business where trucks, docks, and delivery windows move by the hour, a day-old picture meant dispatchers were making routing and exception decisions partly from phone calls and spreadsheets.

## The starting point

The legacy stack was a familiar profile: an on-premises warehouse fed by overnight ETL jobs, a web of stored procedures accumulated over a decade, and two database servers that had aged out of vendor support. The nightly batch window had crept past six hours and occasionally collided with the start of the business day. Failed loads were discovered by the first analyst to open a stale dashboard. The team maintaining it was capable but small, and most of their capacity went to keeping the batches alive rather than improving anything.

## The new platform

The new platform streams shipment and telematics events through Pub/Sub into BigQuery, with dbt managing transformations and Terraform managing everything else. Scanner events, GPS pings, and order-status changes publish to Pub/Sub as they happen and land in BigQuery within seconds. dbt models build the cleaned and conformed layers on top, version-controlled and tested, replacing the stored-procedure web with transformations anyone on the team can read and review. Terraform holds the entire estate, projects, IAM, datasets, pipelines, so environments are reproducible and changes go through pull requests.

Reporting latency dropped from twenty-plus hours to under five minutes, and the client retired two database servers that had been out of vendor support. The operational difference showed up quickly: dispatchers now watch exceptions as they develop, and the daily operations meeting starts from a live dashboard instead of yesterday's extract.

## The hard part was not technical

The hardest part was not the pipeline. It was reconciling three departments' conflicting definitions of "delivered." Operations counted a shipment delivered when the driver scanned it at the door. Customer service counted it when the proof-of-delivery document was filed. Finance counted it when the shipment became billable. All three definitions were correct for their purposes, all three produced different daily totals, and for years each department's reports had quietly used its own.

We resolved it the only way that holds: in a room, with the department heads, agreeing on named, distinct metrics rather than one contested word. The platform now carries all three as explicit, documented fields, and every dashboard states which one it shows. The dbt layer enforces the definitions in code, so they cannot drift apart again without a failing test and a pull request.

Data platform projects are governance projects wearing an engineering costume. We budget for that from the first week now: glossary sessions, metric ownership, and sign-off on definitions are scheduled alongside the pipeline milestones, not discovered after them.

For organizations still running the business on nightly batches, the streaming pattern above is well within reach of a small team once it is stood up correctly, and standing it up correctly is exactly the kind of engagement we build our migration practice around.
