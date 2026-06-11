---
layout: post
title: "Kubernetes adoption: when it actually pays off"
date: 2023-01-09
category: Cloud
excerpt: "Kubernetes earns its complexity only when an organization has enough services, teams, and release velocity to amortize it."
---

We are often asked whether Kubernetes is the right default for new workloads. Our answer: usually not at first. Kubernetes earns its operational overhead when you have multiple teams shipping multiple services with real release velocity, and when you can staff someone to own the platform. For a handful of services, managed container offerings or even plain VMs behind a load balancer are cheaper to run and easier to reason about.

## The threshold question

The decision is rarely about technology. It is about whether your organization generates enough deployment activity to amortize the cost of running an orchestrator. A team shipping two services with weekly releases gets almost nothing from Kubernetes that Cloud Run, App Runner, or a small autoscaling group would not provide. A company with eight teams, forty services, and dozens of deploys a day gets standardized rollouts, consistent service discovery, uniform observability hooks, and a common vocabulary for capacity. That second company has a Kubernetes-shaped problem.

We ask three questions in every assessment. How many independently deployed services exist today, and how many are realistically planned within eighteen months? How often do teams release, and how often do releases collide over shared infrastructure? And who, by name, will own the cluster, its upgrades, and its 2 a.m. pages? If the third question produces silence, the conversation is over regardless of the first two answers.

## What the alternatives buy you

Below the threshold, simpler platforms are not a compromise; they are the better engineering decision. Managed container services give you health checks, autoscaling, and zero-downtime deploys without asking you to understand admission controllers or CNI plugins. Plain VMs behind a load balancer remain underrated for steady workloads with infrequent releases. The bill is lower, the failure modes are fewer, and a generalist engineer can operate the whole stack.

The common counterargument is future-proofing: adopt Kubernetes now so you do not have to migrate later. In our experience the migration from a managed container platform to Kubernetes, done when the organization actually needs it, is far cheaper than two years of premature cluster operations done when it does not.

## If you do adopt it, adopt it deliberately

When clients do adopt Kubernetes, we push for managed control planes (GKE, EKS, AKS), a minimal set of cluster add-ons, and a clear upgrade cadence from day one. Most cluster incidents we see trace back to neglected upgrades and ad hoc tooling, not the orchestrator itself. Our standard guardrails:

- Use the managed control plane; running your own etcd is a hobby, not a strategy.
- Pick one ingress controller, one secrets pattern, and one observability stack, and resist additions.
- Schedule version upgrades on the calendar before the first workload lands, because clusters that fall three versions behind become migration projects.
- Define everything in Terraform and Git so the cluster can be rebuilt, not just repaired.

A minimal, current, well-owned cluster is a genuinely good platform. A sprawling, stale one is the most expensive way to run containers we know of.

If you are weighing this decision for your own estate, we run short platform assessments that put numbers on both paths before anyone writes a line of YAML. The cheapest Kubernetes mistake is the one you evaluate your way out of.
