---
notion_id: "33b43c23-a5e2-8016-be98-fdc4d7542521"
notion_last_edited: "2026-04-07T10:25:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-07"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003563637672"
---

# Issue:

CX reported that they have linux patch deployment failure issues with some patches and asking that if patch got failed, why it is still showing that "Retry in Progress" in the rmarks status.

# Analysis:

When a patch is failed we mark the patch as retry in progress untill the retry count is expired when the retry is exhausted then we mark the patch as failed.
kindly convey the retry in progress behaviour to the customer

and while analyzing the logs we cannot find any trace related to patch failure all the patches from the given configuration either already installed or not applicable.

If the user has any querry on patch failure, kindly collect the following for futhur analysis
1.) Configuration pdf in which the patch is failed
2.) affected agent logs

# Log traces:

```sql
"LocalMachineName": "oel8qa216",
"LocalMachineOsName": "Oracle Linux Server release 8.10",
"LocalMachineServicePack": "Oracle Linux Server release 8.10-Server",
"IsOsServer": "true",
M_linuxAgentVersion:"11.5.2605.13.L
```

