---
notion_id: "33d43c23-a5e2-8096-a7c5-c59fdde75543"
notion_last_edited: "2026-04-09T05:33:00.000Z"
tags:
  - "checksum failure"
  - "known issue"
resolved: "False"
problem tags:
commented time: "2026-04-09T23:03:00.000+05:30"
Solved by: "ME"
Date: "2026-04-09"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003568871513"
---

**Related back to Tickets:** [[No. 7792112  Download Success but checksum failed Error  60000.]]

# Issue:

checksum failure error (60000) when downloading the Duo Windows login agent across all servers except the Patch Manager Plus central server.

# Analysis:

There is a known issue in the Cx build where the checksumType is being missed to setup for isvalrequired = 0 patches. so the agent generate the hash with wrong algorithm(MD5) and compared it with another algorithm (SHA256) so the checksum mismatch occurs,

Issue fixed on 2605.14 and above, kindly suggest build upgrade

[https://www.manageengine.com/patch-management/service-packs1.html](https://www.manageengine.com/patch-management/service-packs1.html)

# Log traces:

```prolog
DesktopCentral Product Code               -> PMP 
Local Computer Name                       -> SERVNOWMID1
DC Distribution Server Enabled            -> no 
DesktopCentral Agent Version              -> 11.5.2605.09.W 
 DesktopCentral Server Name                -> TSNPATCH1P.oaklandmi.net
```

```prolog
[ 2026-04-08 11:44:31:665 ] [ 5456 ] [INFO] PostDownloadHandling : Successfully downloaded the file /store/357732-duo-win-login-latest.exe?agentResourceIdentifier=60002&ResourceID=60002&uniqueValue=VMWARE-42%2031%20D0%20BD%20BF%2091%20DE%2055-
[ 2026-04-08 11:44:31:667 ] [ 5456 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-08 11:44:32:075 ] [ 5456 ] [INFO] Checksum from file : 1dd07cae2fc6031857c486f24c5a42fa
[ 2026-04-08 11:44:32:075 ] [ 5456 ] [INFO] Checksum to compare : a74531f270247e6e11a6f537e7e0c3abca8df0c96642ce4a37300ad517d644ee
[ 2026-04-08 11:44:32:075 ] [ 5456 ] [INFO] Download succeeded but checksum failed.
```

