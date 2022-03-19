---
title: "Infrastructure as Code (IaC)"
date: 2021-06-22T20:26:22-07:00
draft: false
tags:
    - automation
    - concept
short: Infrastructure is scripted, repeatable, and versioned.
---

The idea is that all infrastructure (web servers, databases, ingresses, message queues, etc) for a given environment are represented in code and configuration. Infrastructure setup and teardown for an entire environment is automated, repeatable, and idempotent.

The two main types of IaC are declarative, and imperative. Essentially, declarative systems describe the "what", while imperative systems describe the "how".

## Vendors
The table below describes some of the most mature options for IaC.

| Name      | Primary Method | Corporate Sponsor, if any |
|-----------|------------------------|----------------------|
| [Terraform](https://www.terraform.io/) | Declarative | Hashicorp |
| [Ansible](https://www.ansible.com/) | Imperative | RedHat
| [SaltStack](https://saltproject.io/) | Imperative | |
| [Puppet](https://puppet.com/) | Imperative | |
| [Chef](https://www.chef.io/) | Imperative | |
