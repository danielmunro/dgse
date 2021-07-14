---
title: "Observability"
date: 2021-07-05T13:03:16-07:00
draft: false
tags:
   - concept
resources:
  - { url: https://www.splunk.com/en_us/data-insider/what-is-observability.html, name: Splunk }
  - { url: https://www.dynatrace.com/news/blog/what-is-observability/, name: Dynatrace }
  - { url: https://www.honeycomb.io/blog/observability-a-manifesto/, name: Honeycomb }
---

Qualities of a platform that lend to its understandability. Such qualities are:

* Logging is in place for all services. 
    * Specifically, data ingress or egress for all services should emit a log with the canonical ID of the data.
    * Log [streams](/glossary/stream) should be collected via a log aggregator.
    * The log aggregator should allow searching across logs at a minimum.
* Alerting is configurable -- escalations are in place to people who can diagnose problems as them emerge in realtime.
* The platform is able to provide health and liveness checks.
* Graphing and support for custom events. This is one of the easiest way to correlate multiple data streams and see performance relationships in real time.
