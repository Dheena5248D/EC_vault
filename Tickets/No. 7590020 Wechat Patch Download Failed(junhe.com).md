---
notion_id: "32243c23-a5e2-80be-9757-d2adb8d4089e"
notion_last_edited: "2026-03-15T09:53:00.000Z"
tags:
  - "upload patch"
resolved: "False"
problem tags:
  - "checksum mismatch"
  - "patch upload failure"
Date: "2026-03-13"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003442536156"
---

# Problem:

A patch is failing to download and while the Cx uploads the patch manually they face checksum mismatch issue 



# Analysis

```javascript
[12:51:48:960]|[03-13-2026]|[com.me.devicemanagement.framework.server.util.ChecksumProvider]|[INFO]|[51173]|[775e8ff7-fb2a-4cd5-b042-36d9caca77eb]: SHA 256 checkSum failed for FilePath ::..\webapps\DesktopCentral\store\355516-WeChatWin_4.1.7.exe as the downloaded file's checksum ::00a96c6c67f02d8e37e52114844232fa755ccf638377f766dff09b9014ca098a is different from checksum in db ::25276e4325d3eb386dabfeed471ea4daa9187b45a34545f33bc5fe46626bd56c|
```

The checksum from the table and checksum from the exe is different





If i try to download the superseded patch i.e 356856

the same exe is downloading that is instead of downloading v 4.1.7.57 it is downloading v 4.1.7 and it fails in the checksum

```javascript
[13:25:36:958]|[03-13-2026]|[com.me.devicemanagement.framework.server.util.ChecksumProvider]|[INFO]|[46715]|[d0e90a63-c043-41fc-92f3-d5b1597b8d3f]: SHA 256 checkSum failed for FilePath ::..\webapps\DesktopCentral\store\356856-WeChatWin_4.1.7.57.exe as the downloaded file's checksum ::00a96c6c67f02d8e37e52114844232fa755ccf638377f766dff09b9014ca098a is different from checksum in db ::3e18652176b493560dfa78658f59a06a692de35c5ef732d1c4c9b89c33a00cf6|
[13:25:36:992]|[03-13-2026]|[com.me.uems.patch_mgmt.listener.WebSocketListenerImpl]|[INFO]|[46715]|[d0e90a63-c043-41fc-92f3-d5b1597b8d3f]: Message received for TaskId: 45,112, the message: {downloadStatus={"statusType":"detailed","data":{"patchID":356856,"status":223,"description":"WeChat (x64) (4.1.7.57)","language":"English","remarks":"Download blocked by firewall. Enable firewall configuration to allow download."}}}|
```

