---
title: WebSocket Server Requests
description: Documentation of requests that can be made to the Streamer.bot WebSocket Server
published: true
date: 2022-12-18T18:18:04.207Z
tags: websocket
editor: markdown
dateCreated: 2021-08-25T21:37:16.673Z
---

Requests can be made to the server in JSON format.

The basic format for a request is as follows:

```json
{
  "request": "<request>",
  "id": "<id>"
}
```


## Subscribe
⚠️ This request is **required** to enable you to listen to events

### Tab {.tabset}
#### Request

```json
{
  "request": "Subscribe",
  "id": "<message id>",
  "events": {
    "<event category>": [
      "<event name>",
  		"<event name>",
  		"...",
		]
	},
}
```

#### Example

```json
{
  "request": "Subscribe",
  "id": "my-subscribe-events-id",
  "events": {
    "Twitch": [
      "Follow",
      "Cheer",
      "Sub",
      "Resub",
      "GiftSub",
      "GiftBomb"
		]
	},
}
```

## UnSubscribe
This request allows you to unsubscribe from any message events you are currently subscribed to

### Tab {.tabset}
#### Request

```json
{
  "request": "UnSubscribe",
  "id": "<message id>",
  "events": {
    "<event category>": [
      "<event name>",
  		"<event name>",
  		"...",
		]
	},
}
```

#### Example

```json
{
  "request": "UnSubscribe",
  "id": "my-unsubscribe-events-id",
  "events": {
    "Twitch": [
      "Follow",
      "Cheer",
      "Sub",
      "Resub",
      "GiftSub",
      "GiftBomb"
		]
	},
}
```


## GetEvents
This request will get you a list of all events that may be emitted

### Tab {.tabset}
#### Request

```json
{
  "request": "GetEvents",
  "id": "<message id>",
}
```

#### Response

```json
{
  "id": "<message id>",
  "events": {
    "application": [
      "ActionAdded",
      "ActionUpdated",
      "ActionDeleted"
    ],
    "command": [
      "Message",
      "Whisper",
      "MessageCooldown",
      "BotWhisper"
    ],
    "donorDrive":[
         "Donation",
         "ProfileUpdated"
      ],
    "fileWatcher": [
      "Changed",
      "Created",
      "Deleted",
      "Renamed"
    ],
    "general": [
      "Custom"
    ],
    "hypeRate":[
         "HeartRatePulse"
      ],
    "kofi":[
         "Donation",
         "Subscription",
         "Resubscription",
         "ShopOrder",
         "Commission"
      ],
    "misc": [
      "TimedAction",
      "PyramidSuccess",
      "PyramidBroken"
    ],
    "patreon":[
         "FollowCreated",
         "FollowDeleted",
         "PledgeCreated",
         "PledgeUpdated",
         "PledgeDeleted"
      ],
      "pulsoid":[
         "HeartRatePulse"
      ],
    "quote": [
      "Added",
      "Show"
    ],
    "raw": [
      "Action",
      "SubAction"
    ],
    "shopify":[
         "OrderCreated",
         "OrderPaid"
      ],
    "speechToText": [
      "Dictation",
      "Command"
    ],
    "streamElements": [
      "Tip",
      "Merch"
    ],
    "streamlabs": [
      "Donation",
      "Merchandise"
    ],
    "tipeeeStream":[
         "Donation"
      ],
      "treatStream":[
         "Treat"
      ],
    "twitch": [
      "Follow",
      "Cheer",
      "Sub",
      "ReSub",
      "GiftSub",
      "GiftBomb",
      "Raid",
      "HypeTrainStart",
      "HypeTrainUpdate",
      "HypeTrainLevelUp",
      "HypeTrainEnd",
      "RewardRedemption",
      "RewardCreated",
      "RewardUpdated",
      "RewardDeleted",
      "CommunityGoalContribution",
      "CommunityGoalEnded",
      "StreamUpdate",
      "Whisper",
      "FirstWord",
      "SubCounterRollover",
      "BroadcastUpdate",
      "StreamUpdateGameOnConnect",
      "PresentViewers",
      "PollCreated",
      "PollUpdated",
      "PollCompleted",
      "PredictionCreated",
      "PredictionUpdated",
      "PredictionCompleted",
      "PredictionCanceled",
      "PredictionLocked",
      "ChatMessage",
      "ChatMessageDeleted",
      "UserTimedOut",
      "UserBanned",
      "Announcement",
      "AdRun",
      "BotWhisper",
      "CharityDonation",
      "CharityCompleted",
      "CoinCheer",
      "ShoutoutCreated",
      "UserUntimedOut"
    ],
    "websocketClient": [
      "Open",
      "Close",
      "Message"
    ],
    "websocketCustomServer": [
      "Open",
      "Close",
      "Message"
    ],
    "youTube":[
         "BroadcastStarted",
         "BroadcastEnded",
         "Message",
         "MessageDeleted",
         "UserBanned",
         "SuperChat",
         "SuperSticker",
         "NewSponsor",
         "MemberMileStone",
         "NewSponsorOnlyStarted",
         "NewSponsorOnlyEnded",
         "StatisticsUpdated",
         "BroadcastUpdated",
         "MembershipGift",
         "GiftMembershipReceived",
         "FirstWords"
      ]
  },
  "status": "ok"
}
```


## GetActions
This request will get you a list of all the actions you have configured in your Streamer.bot instance
### Tab {.tabset}
#### Request

```json
{
  "request": "GetActions",
  "id": "<message id>"
}
```

#### Response

```json
{
  "id": "<message id>",
  "count": 00,
  "actions": [
    {
      "id": "<action guid>",
      "name": "<action name>"
    },
  ],
  "status": "ok"
}
```

## DoAction
This request will trigger an action that you provide

### Tab {.tabset}
#### Request

```json
{
  "request": "DoAction",
  "action": {
    "id": "<guid>",
    "name": "<name>"
  },
  "args": {
    "key": "value",
  },
  "id": "<id>"
}
```

#### Response

If the action is not found, an error will be returned, if the action was dispatched it will return success.
```json
{
  "id": "<id>",
  "status": "ok"
}
```

## GetBroadcaster
This request will give the broadcaster information for Twitch/Youtube

### Tab {.tabset}
#### Request
```json
{
  "request": "GetBroadcaster",
  "id": "<id>"
}
```

#### Response
```json
{
  "platforms": {
    "twitch": {
      "broadcastUser": "ik1497",
      "broadcastUserName": "ik1497",
      "broadcastUserId": 695682330,
      "broadcasterIsAffiliate": false,
      "broadcasterIsPartner": false
    },
    "youtube": {
      "broadcastUserName": "Ik1497 Tutorials",
      "broadcastUserId": "UCl3oatIf9tYopHaZHvnH3xw",
      "broadcastUserProfileImage": "https://yt3.ggpht.com/VpC8_9WcDEKcPSvnD6p1iGT_S2_XxdeZtL6tTL2axexj0SpG-c4Wx8i5lYNbJtvmzwCnzm9Bsg=s88-c-k-c0x00ffffff-no-rj"
    }
  },
  "connected": [
    "twitch",
    "youtube"
  ],
  "disconnected": [],
  "status": "ok",
  "id": "<id>"
}
```

## GetCredits

### Tab {.tabset}
#### Request
```json
{
  "request": "GetCredits",
  "id": "<id>"
}
```

#### Response
```json
{
  "id": "credits",
  "Events": {
    "Follows": [],
    "Cheers": [],
    "Subs": [],
    "ReSubs": [],
    "GiftSubs": [],
    "GiftBombs": [],
    "Raided": [],
    "RewardRedemptions": [],
    "GoalContributions": [],
    "GameUpdates": [],
    "Pyramids": []
  },
  "HypeTrainConductor": [],
  "HypeTrainContributors": [],
  "User": {
    "Editors": [],
    "Moderator": [],
    "Subscriber": [],
    "VIPs": [],
    "Users": [],
    "regulars": []
  },
  "Custom": {},
  "TopBits": {
    "All": [],
    "Month": [],
    "Week": []
  },
  "TopChannelRewards": [],
  "status": "ok"
}
```

## TestCredits

### Tab {.tabset}
#### Request

```
{
  "request": "TestCredits",
  "id": "<id>"
}
```
  
## ClearCredits

### Tab {.tabset}
#### Request

```
{
  "request": "ClearCredits",
  "id": "<id>"
}
```

## Examples
Example Javascript code for interacting with the WebSocket Server

### Tab {.tabset}
#### Connect

Code to connect - this function is ideally called directly / indirectly from onload 
```js
function connectws() {
	if ("WebSocket" in window) {
		const ws = new WebSocket("ws://localhost:8080/");
	}
}
```

#### Reconnect

Code to attempt to reconnect (after 10 seconds) when disconnected:
```js
ws.onclose = function() { 
  // "connectws" is the function we defined previously
  setTimeout(connectws, 10000);
};
```

#### Subscribe

Code to subscribe to events - In this example: Follows, Cheers, Subs, Resubs, Gift Subs and Gift Bombs.
```js
ws.onopen = function() {
  ws.send(JSON.stringify(
  	{ 
      "request": "Subscribe", 
      "events": {
        "Twitch": [
          "Follow",
          "Cheer",
          "Sub",
          "Resub",
          "GiftSub",
          "GiftBomb"
        ] 
      },
      "id": "123"
    }
  ));
}
```

Code to Handle the above messages when received from the server:
```js
ws.onmessage = function (event) {
  // grab message and parse JSON
  const msg = event.data;
  const wsdata = JSON.parse(msg);
  
  // check for events to trigger
  if (wsdata.event.source === 'Twitch') {
    if (wsdata.event.type === 'Sub' || wsdata.event.type === 'ReSub') {
      alert(`trigger sub event for ${wsdata.data.displayName}`);
    } else if (wsdata.event.type === 'GiftSub') {
      alert(`trigger Gift sub event for ${wsdata.data.recipientDisplayName}`);
    } else if (wsdata.event.type === 'GiftBomb') {
      if (wsdata.data.isAnonymous === false) {
        alert(`trigger gift bomb event for ${wsdata.data.displayName} ${wsdata.data.gifts} subs`);
      } else {
        alert(`trigger gift bomb event for Anonymous ${wsdata.data.gifts} subs`);
      }
    } else if (wsdata.event.type === 'Follow') {
      alert(`trigger follow event for ${wsdata.data.displayName}`);
    } else if (wsdata.event.type === 'Cheer') {
      alert(`trigger cheer event for ${wsdata.data.message.displayName} ${wsdata.data.message.bits}`);
    }
  }
};
```

### End Tabset {.tabset}
---
- [<i class="mdi mdi-chevron-left"></i> **WebSocket Server *Go Back***](/Servers-Clients/WebSocket-Server)
- [<i class="mdi mdi-download-network primary--text"></i> **WebSocket Events *Reference of all events emitted over the Streamer.bot WebSocket API***](/Servers-Clients/WebSocket-Server/Events)
{.btn-grid .my-5}
