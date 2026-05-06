---
notion_id: "32043c23-a5e2-80ae-bbbe-ffdbdbf4c983"
notion_last_edited: "2026-03-13T10:29:00.000Z"
tags:
  - "refresh cycle"
  - "reboot prompt"
  - "patch-deployment"
  - "APD"
resolved: "False"
problem tags:
Date: "2026-03-12"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003449368445"
---

# Problem

CX deployed the configuration task with delay reboot but even after the reboot schedule still reboot prompt didnt appeared in client machine.



# Analysis:

The dev confirms that this is a known issue 

this is a known case in the agent side for which the fix is in release process



According to pdf the reboot window will only show after 14:00

```javascript
26-03-11	3068000004195745	2026-02 Monthly Update Windows - ITCSS	43586		3068000004195753		Install Patch	11:40:31	11:59:08	REBOOT_REQUIRED	[i18n]Reboot Pending[/i18n]
```

A patch is installed at 11:59:08

```javascript
[ 2026-03-11 12:18:12:216 ] [ 15104 ] [INFO] operation : ConstructRebootRequiredProps; collection_id : 3068000004195745; config_id : 151; restart_option : 3; is_exclude_server : FALSE;
[ 2026-03-11 12:18:12:257 ] [ 15104 ] [INFO] operation : ProcessRebootPolicy; reboot_required_reason_id : 0; remarks : "Temporarily assigning as not-applicable";
[ 2026-03-11 12:18:12:208 ] [ 15104 ] [INFO] Inside processreboot policy
[ 2026-03-11 12:18:12:210 ] [ 15104 ] [INFO] ShutdownBlocked : 0
[ 2026-03-11 12:18:12:211 ] [ 15104 ] [INFO] ProcessDeploymentSetting : Configuration deployed using deployment policy with id : 3068000003556232 
[ 2026-03-11 12:18:12:212 ] [ 15104 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-11 12:18:12:212 ] [ 15104 ] [INFO] Reboot_Option : 3
[ 2026-03-11 12:18:12:212 ] [ 15104 ] [INFO] Reboot_Timeout : -1
[ 2026-03-11 12:18:12:212 ] [ 15104 ] [INFO] Exclude_Server : 1
[ 2026-03-11 12:18:12:212 ] [ 15104 ] [INFO] Skip_Reboot :^1
[ 2026-03-11 12:18:12:212 ] [ 15104 ] [INFO] Restart_And_Shutdown : 0
[ 2026-03-11 12:18:12:212 ] [ 15104 ] [INFO] Reboot_Message : Restart required. Choose Restart Now or Postpone. A forced restart will occur within the next 24 hours.
[ 2026-03-11 12:18:12:212 ] [ 15104 ] [INFO] Reboot_Tile : Restart Required
[ 2026-03-11 12:18:12:212 ] [ 15104 ] [INFO] Enable_Notify : FALSE
[ 2026-03-11 12:18:12:212 ] [ 15104 ] [INFO] Pre-deployment action : FALSE
[ 2026-03-11 12:18:12:212 ] [ 15104 ] [INFO] ProcessRebootPolicy: Configured to the exclude the server while processing Reboot Policy
[ 2026-03-11 12:18:12:213 ] [ 15104 ] [INFO] GetOSName: OS Name returned from global variable Windows 11 Enterprise Edition (x64) 
[ 2026-03-11 12:18:12:214 ] [ 15104 ] [INFO] Restart  : DC_ALLOWSKIP_REBOOT ,timeoutToReboot  : -1 ,isthisMachineExcluded  : 0, rebootOnlyIfReq : 1
[ 2026-03-11 12:18:12:214 ] [ 15104 ] [INFO] installStatus  : 1 ,isRebootRequired  : 1 ,isMarkedforScheduled(is10008)  : 0
[ 2026-03-11 12:18:12:214 ] [ 15104 ] [INFO] blockShutdownStatus  : 0 
[ 2026-03-11 12:18:12:214 ] [ 15104 ] [INFO] reboot_required_collection : 1 
[ 2026-03-11 12:18:12:214 ] [ 15104 ] [INFO] doReboot  : 1 
[ 2026-03-11 12:18:12:214 ] [ 15104 ] [INFO] pConfResp -> doNotRebootnow  : 0 
[ 2026-03-11 12:18:12:214 ] [ 15104 ] [INFO] rebootskipcount  : 0 
```

```javascript
[ 2026-03-11 11:59:09:509 ] [ 15104 ] [INFO] @@@ Inside PerformRebootAction for actionID : 3068000003746131 @@@[ 2026-03-11 11:59:09:511 ] [ 15104 ] [INFO] GetOSName: OS Name returned from global variable Windows 11 Enterprise Edition (x64) 
[ 2026-03-11 11:59:09:511 ] [ 15104 ] [INFO] @@@ Inside SleepBetweenReboots() @@@
[ 2026-03-11 11:59:09:511 ] [ 15104 ] [INFO] GetTimeInSeconds : Time in Second : 1773244749
[ 2026-03-11 11:59:09:511 ] [ 15104 ] [INFO] @@@ End of SleepBetweenReboots() @@@
[ 2026-03-11 11:59:09:512 ] [ 15104 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-11 11:59:09:541 ] [ 15104 ] [INFO] Reboot operation will be processed in ProcessRebootPolicy()
[ 2026-03-11 11:59:09:541 ] [ 15104 ] [INFO] @@@ End of PerformRebootAction @@@
[ 2026-03-11 11:59:09:673 ] [ 15104 ] [INFO] All post-deployment actions have been executed successfully.
[ 2026-03-11 11:59:09:673 ] [ 15104 ] [INFO] @@@ ClearPrePostRegValue @@@
[ 2026-03-11 11:59:09:703 ] [ 15104 ] [INFO] PrePostData : {
   "S-1-5-18" : {
      "3068000004195745" : {
         "3068000003746131" : "Reboot action processed\t 11-03-2026 11:59:09",
         "CollectionStartedStatusSent" : 1,
         "DeploymentCompleted" : 1,
         "LastBootupTime" : 1772226577,
         "PatchOrSoftwareInstalled" : 1,
         "PreDepActionsCompleted" : 1,
         "ProcessedActionIDs" : "3068000003746131",
         "RebootRequired" : 1
      }
   }
}
```

The reboot policy are loaded but the log ended before writing rbtjobs

```javascript
[ 2026-03-11 12:18:12:216 ] [ 15104 ] [INFO] operation : ConstructRebootRequiredProps; collection_id : 3068000004195745; config_id : 151; restart_option : 3; is_exclude_server : FALSE;
[ 2026-03-11 12:18:12:257 ] [ 15104 ] [INFO] operation : ProcessRebootPolicy; reboot_required_reason_id : 0; remarks : "Temporarily assigning as not-applicable";
```

```javascript
26-03-11	       Ondemand	  11:39:02	
26-03-11	        Refresh	  13:07:17	       13:07:51
```

```javascript
26-03-11	Timer_Refresh_Notification	10:07:10	
26-03-11	Timer_Refresh_Notification	11:37:12	
26-03-11	Timer_Refresh_Notification	13:07:14
```



