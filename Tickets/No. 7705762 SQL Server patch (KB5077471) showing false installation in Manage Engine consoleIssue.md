---
notion_id: "33343c23-a5e2-8060-92d3-da4449fabff0"
notion_last_edited: "2026-03-31T11:40:00.000Z"
tags:
  - "patch-scan"
resolved: "False"
problem tags:
  - "patch not deployed in apd"
  - "meta-data files not modified"
Date: "2026-03-30"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003521128248"
---

# Issue:

SQL server security patch which is showing false installation in Manage Engine console but not installed in the server.

# Analysis:

The patch 28658 is tried to install via `MyConfiguration3464` and got error code 15 which means it requires reboot before deployment on 05:42:47, and then the machine restarted on 06:08:30, so the collection retried the collection again but while installing the patch the machine is restarted in between the deployment process so in next refresh cycle the patch is detected that it is being installed on the previous cycle and sent the post req to the server

The patch 28658 is found on the machine so it is marked available and sent the patch scan results to server and then the patch is marked as installed in the server,

Due to the installation is interrupted by a reboot it is suspected that there is partial installation so repairing the application from control panel can remove the partial installation so it then the patch scan can find the patch as missing and then the Cx can redeploy the patch. 

# Log traces:

```javascript
26-03-22	29790	MyConfiguration3464	43694		40177		Install Patch	05:36:07	05:42:47	FAILURE	[i18n]A system restart is required before patch deployment due to pending file operations[/i18n]
26-03-22	29790	MyConfiguration3464	43694		40177		Install Patch	06:26:26	
26-03-22	29790	MyConfiguration3464	43694		40177		Install Patch	06:39:08	06:39:08	SUCCESS	[i18n]dc.db.agent.patchinstall.prev_post_fail[/i18n]
```

```javascript
26-03-22	Machine_Shutdown_Notification	06:08:30	
26-03-22	Machine_Bootup_Notification	06:09:42

26-03-22	Machine_Shutdown_Notification	06:32:57	
26-03-22	Service_Startup_Bootup_Notification	06:33:48
```

```javascript
26-03-22		06:08:30		Restart		The process C:\Program Files (x86)\ManageEngine\UEMS_Agent\bin\dcondemand
26-03-22		06:32:58		Restart		The process C:\Windows\servicing\TrustedInstaller
```

```javascript
<AffectedPatchStatus RESOURCE_ID="28658" PATCH_ID="43694" STATUS="Available" STATUS_ID="201" UPDATED_TIME="0" REMARKS="" />
```

```javascript
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] PatchScan:scanning : 43694
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] End of the function checkforpatchapplicableex
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] ChkForPatchAppliEx ret val: 127
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] End of the function checkforpatchapplicableex
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] isMsucheck:0
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] @@@@@ 	 Inside CheckForAvailableEx() [d:\Webhost\24-02-2026\WindowsBuilds\VMDR_AGENT\12685885\vmdr_agent\Native_Src\native\patch\src\patchreshdlr.cpp](4620) 	 @@@@@
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] ChkForAvail: Path: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\KB5077471 checkId : 2107963 checkType : 10
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] chkid:2107963,Type:10,Local Val:true
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] ChkForPatchAvailEx: ChkId 2107963,PatchId 43694,CrtGrpId 1 Status 121
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] CheckForPatchAvailableEx ret val: 121
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] CheckForPatchApplicableEx ret val: 121
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] ProcessPatchScanEx: Return Val for patchid 43694:121,remarks: 
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] AddAffPatchStatusRow: added row patch 43694 to AffPatchStatus
[ 2026-03-26 08:21:39:990 ] [ 1904 ] [INFO] AddAffectedProductsRow : Successfully added the params row(patchid: 43694 , productid Id: 1615) to AffectedProduct Table
```

```javascript
[ 2026-03-26 08:21:50:139 ] [ 1904 ] [INFO] AffectedPatchStatus : patchid:status 
[ 2026-03-26 08:21:50:139 ] [ 1904 ] [INFO] 106382:201 , 107664:201 , 107921:201 , 112861:201 , 112862:201 , 112917:201 , 12621:201 , 12622:201 , 16316:201 , 355222:201 , 400002:202 , 400009:202 , 400054:201 , 41815:201 , 42378:201 , 42629:201 , 42660:201 , 42878:201 , 43077:201 , 43209:201 , 43214:201 , 43391:201 , 43408:201 , 43411:201 , 43574:201 , 43694:201 , 500106:201 , 500108:201 ,
```

