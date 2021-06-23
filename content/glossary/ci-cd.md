---
title: "CI/CD"
date: 2021-06-21T07:32:56-07:00
draft: false
---

1. Acronym. [Continuous integration](#continuous-integration) / [continuous delivery](#continuous-delivery).

1. Concept. Defines a developer workflow whereby code changes go through an automated process after check in.
   
    The first step of the process is integration. Automated tests run, as well as any configured analysis tools.

    The second step is delivery. In this case, delivery means automatic deployment of code changes to the next target environment once the integration step completes. Typically, there is more than one target environment, so this process can loop a few times as verification checks happen in each environment. The final step is when code is deployed out to production.

    One thing to note about the delivery step. After deployment to a target environment, it is common to perform some manual testing checks. As such, the delivery phase often is not fully automated. Instead, a deployment happens to a target environment and once deployment finishes, the developer triggers deployment to production or another test environment.
