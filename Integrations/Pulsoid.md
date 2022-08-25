---
title: Pulsoid
description: Integrate Streamer.bot with Pulsoid
published: true
date: 2022-07-22T18:37:11.046Z
tags: v0.1.8, integrations, pulsoid
editor: markdown
dateCreated: 2022-06-01T04:14:54.410Z
---

![streamerbot.png](https://streamer.bot/img/integrations/pulsoid.png){.align-abstopright}

## Overview

No longer an extension written in C#, Pulsoid support is now a native part of **Streamer.bot**

![pulsoid-integration.png](/pulsoid-integration.png =x400)

After connecting your account, by clicking **Connect to Pulsoid** and following the prompts in your browser.  You can assign an action to the `Heart Rate` Event, and when Pulsoid broadcasts a heart beat, this action will run.

> When Pulsoid is broadcasting your heart rate, this event can fire once every second, so be sure whatever action you use runs fast enough so it won't cause a backlog in an action queue.  It is also recommended that whatever action you are running be placed in a blocking queue.
{.is-warning}

## Variables

| Name | Description |
|---:|:------------|
| `measuredAt` | Time the measurement was taken |
| `heartRate` | Heart rate value (BPM) |

---

- [<i class="mdi mdi-chevron-left"></i> **All Integrations *Go Back***](/en/Integrations)
{.btn-grid .my-5}