---
notion_id: "34343c23-a5e2-805b-b851-ef0ae06f236f"
notion_last_edited: "2026-04-15T11:30:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-15"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003576089978"
---

# Issue:

Manual Deployment task is in Draft Download in progress even though patches are downloaded

# Analysis:

There is a known issue in the customer build where downloading patches within 10 to 20 minutes may lead to clean-up and the patch is struck in download in-process untill next server restart irrespective of primary server or secondary server.

The issue is fixed in latest builds so kindly ask the customer to upgrade the server to 11.5.2600.35 or higher

[https://www.manageengine.com/products/desktop-central/service-packs.html](https://www.manageengine.com/products/desktop-central/service-packs.html)

# Log traces:

```prolog
build.number=114252821

wrapper.log
INFO   | jvm 1    | 2026/04/11 19:52:23 | Server started in :: [252023 ms]

patchdownloadmanager.log
[19:56:41:392]|[04-11-2026]|[PatchDownloadManagerLogger]|[INFO]|[379]|[f1a11f7e-9002-4aae-83d0-a920844f715c]: PatchDownloadManager - initiatePatchDownload Entered, Patches count: 7 Patches: [43574, 43604, 43606, 43692, 356857, 357221, 1424213]|
[19:56:41:455]|[04-11-2026]|[PatchDownloadManagerLogger]|[INFO]|[379]|[f1a11f7e-9002-4aae-83d0-a920844f715c]: Getting Dependency Patches: [43408, 316440]|
[19:56:41:470]|[04-11-2026]|[PatchDownloadManagerLogger]|[INFO]|[379]|[f1a11f7e-9002-4aae-83d0-a920844f715c]: Office patches list are : `[]`|
[19:56:41:470]|[04-11-2026]|[PatchDownloadManagerLogger]|[INFO]|[379]|[f1a11f7e-9002-4aae-83d0-a920844f715c]: Patches : [43574, 43604, 43606, 43692, 356857, 357221, 1424213, 43408, 316440] added in listener for the collection : 30,001|
[19:56:41:470]|[04-11-2026]|[PatchDownloadManagerLogger]|[INFO]|[379]|[f1a11f7e-9002-4aae-83d0-a920844f715c]: Patches to Download Count: 9, Patches List are : [43574, 43604, 43606, 43692, 356857, 357221, 1424213, 43408, 316440]|
[19:56:41:533]|[04-11-2026]|[PatchDownloadManagerLogger]|[INFO]|[379]|[f1a11f7e-9002-4aae-83d0-a920844f715c]: Deleted uploaded AV patches : []|
[20:07:41:093]|[04-11-2026]|[PatchDownloadManagerLogger]|[INFO]|[278]|[SERVER-04db3534-cdbf-4392-9036-ed9e2874a42f]: PMServiceHandlerServer: Shutdown abruptly, Deleting In queue patches started....|
[20:07:41:249]|[04-11-2026]|[PatchDownloadManagerLogger]|[INFO]|[278]|[SERVER-04db3534-cdbf-4392-9036-ed9e2874a42f]: PMServiceHandler: Shutdown abruptly, Deleted In queue patches ended....|
[20:07:41:249]|[04-11-2026]|[PatchDownloadManagerLogger]|[INFO]|[278]|[SERVER-04db3534-cdbf-4392-9036-ed9e2874a42f]: Inside initializePatchDownloadQueue|
```

