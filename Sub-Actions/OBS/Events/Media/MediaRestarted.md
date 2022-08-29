---
title: MediaRestarted
description: This event is only emitted when something actively controls the media/VLC source. In other words, the source will never emit this on its own naturally.
published: true
date: 2022-06-29T02:40:26.876Z
tags: 
editor: markdown
dateCreated: 2022-06-28T16:26:02.254Z
---

# MediaRestarted

## Variables

Name | Description
----:|:------------
| `obsEvent.event` | The OBS event in this case `MediaRestarted`
| `obsEvent.sourceKind` | Source kind
| `obsEvent.sourceName` | Source name
| `obsEvent.update-type` | The update type of the OBS event in this case `MediaRestarted`
| `obsEvent._json` | Everything above in a json format

* [Official OBS websocket documentation about this](https://github.com/obsproject/obs-websocket/blob/4.x-current/docs/generated/protocol.md#mediarestarted)
* [<= Back](/en/Integrations/OBS/Events)
{.links-list}