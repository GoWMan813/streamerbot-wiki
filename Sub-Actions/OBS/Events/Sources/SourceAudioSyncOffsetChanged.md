---
title: SourceAudioSyncOffsetChanged
description: The audio sync offset of a source has changed.
published: true
date: 2022-07-06T21:21:50.128Z
tags: 
editor: markdown
dateCreated: 2022-07-06T21:21:45.222Z
---

# SourceAudioSyncOffsetChanged

## Variables

Name | Description
----:|:------------
| `obsEvent.event` | The OBS event in this case `SourceAudioSyncOffsetChanged`
| `obsEvent.sourceName` | Source name
| `obsEvent.syncOffset` | Audio sync offset of the source (in nanoseconds)
| `obsEvent.update-type` | The update type of the OBS event in this case `SourceAudioSyncOffsetChanged`
| `obsEvent._json` | Everything above in a JSON format

* [Official OBS WebSocket documentation about this](https://github.com/obsproject/obs-websocket/blob/4.x-current/docs/generated/protocol.md#sourceaudiosyncoffsetchanged)
* [<= Back](/en/Integrations/OBS/Events)
{.links-list}