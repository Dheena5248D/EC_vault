---
notion_id: "32043c23-a5e2-8086-ac4b-ea6b3196a949"
notion_last_edited: "2026-03-13T04:49:00.000Z"
tags:
  - "APD"
  - "upload patch"
resolved: "False"
problem tags:
Date: "2026-03-11"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003444227465"
---

# Problem

A patch 352652 is manual upload patch the cx claims that the patch is deployed and he never manually uploaded the patch



# Analysis

## Agent

As the customer stated the patch is installed in the system

```prolog
	 26-01-02 4076 Terra_Exxon Mobil_CHG_Win2k19 352652 352652 APD Deploy 21:16:43 21:20:20 SUCCESS The operation completed successfully.
	 
	 26-01-02	21:20:20	4076	352652	1767388603	6	The operation completed successfully. 	The operation completed successfully.
```

## Server

The server downloaded the patch from the vendor website



```prolog
[18:06:30:484]|[02-22-2026]|[SecurityOnelineLog]|[INFO]|[1616]|[SERVER-47cea1da-1139-4328-9154-adfcd0879058]:      [Patch Management] [        Patch Download] [                    ] [                    ] [                  ] [                         ] {download attempt by=301, patchId=352652, remarks=downloaded successfully/Awaiting Window}[[

[20:44:53:673]|[10-31-2025]|[PatchDownloadLogger]|[INFO]|[13358]|[SERVER-daa6b5ef-b471-4b3f-a232-6ed16cae5dc7]: Patch 	352652-jre-8u471-windows-x64.exe	https://javadl.oracle.com/webapps/download/AutoDL?BundleId=252627_99a6cb9582554a09bd4ac60f73f9b8e6	40352416	DLOAD_SUCCESS|
```

