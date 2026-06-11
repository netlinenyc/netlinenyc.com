---
layout: post
title: "Showcase: GCP data platform for a logistics operator"
date: 2024-01-22
category: Migration
excerpt: "We replaced a nightly batch warehouse with a streaming pipeline on GCP, cutting reporting latency from a day to minutes."
---

We recently wrapped a six-month engagement moving a regional logistics operator from an aging on-premises data warehouse to a managed platform on Google Cloud. The previous environment ran nightly batches; operations teams worked with data that was always a day old.

The new platform streams shipment and telematics events through Pub/Sub into BigQuery, with dbt managing transformations and Terraform managing everything else. Reporting latency dropped from twenty-plus hours to under five minutes, and the client retired two database servers that had been out of vendor support.

The hardest part was not the pipeline. It was reconciling three departments' conflicting definitions of "delivered." Data platform projects are governance projects wearing an engineering costume.
