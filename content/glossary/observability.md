---
title: "Observability"
date: 2021-07-05T13:03:16-07:00
draft: false
---

Qualities of a platform that lend to its understandability. Such qualities are:

* Logging is in place for all services. 
    * Specifically, data ingress or egress for all services should emit a log with the canonical ID of the data.
    * Log [streams](/glossary/stream) should be collected via a log aggregator.
    * The log aggregator should allow searching across logs at a minimum.
* Alerting is configurable.
    * The platform is able to provide health and liveness checks.
    * A system of alerts and escalations are in place to people who can diagnose problems as them emerge in realtime.
* Graphing and support for custom events. This is one of the easiest way to correlate multiple data streams and see performance relationships in real time.
