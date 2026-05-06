---
notion_id: "32743c23-a5e2-806b-b08d-de9fc3d08aa7"
notion_last_edited: "2026-03-18T09:15:00.000Z"
tags:
  - "APD"
  - "pre deployment"
  - "user_notification"
resolved: "False"
problem tags:
  - "pre deployment user notification is not showing in retry collection"
Date: "2026-03-18"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003465756052"
---

# Problem:

According to the customer, the patch installation works as expected during the initial deployment. The user notification is displayed to the user, after which the pre-deployment script executes, closes all the applications as defined in the script, and proceeds with the patch installation. The machine is then rebooted based on the configured post-deployment activity.

However, if any patches fail to install during this process, the APD task retries the installation. During the retry, the applications are forcefully closed without displaying the user notification prompt.



# Analysis:

According to patchmgmt log the user notification is processed every time but i can’t find entry on dcmsghandler log



> [!info] 



# Log traces:

```javascript
26-03-11	Refresh	  Computer	    SYSTEM	    Patch test group	          Intune IT Test Group	29863000011693001	      SCHEDULED_SKIP	  09:00:30	    2	  09:41:07DC_ALLOWSKIP_REBOOT(prbtsh)      RETRY_UNTIL_SUCCESS	    0
26-03-11	Refresh	  Computer	    SYSTEM	    Patch test group	          Intune IT Test Group	29863000011693001	    Retry Collection	  10:22:37	    2	  10:48:19DC_ALLOWSKIP_REBOOT(prbtsch)      RETRY_UNTIL_SUCCESS	   --
26-03-11	Refresh	  Computer	    SYSTEM	    Patch test group	          Intune IT Test Group	29863000011693001	    Retry Collection	  11:44:31	    2	  11:45:28DC_ALLOWSKIP_REBOOT(skppd)      RETRY_UNTIL_SUCCESS	   --
26-03-11	StartUp	  Computer	    SYSTEM	    Patch test group	          Intune IT Test Group	29863000011693001	    Retry Collection	  12:30:56	    2	  12:35:46DC_ALLOWSKIP_REBOOT(skppd)      RETRY_UNTIL_SUCCESS	   --
26-03-11	Refresh	  Computer	    SYSTEM	    Patch test group	          Intune IT Test Group	29863000011693001	    Retry Collection	  13:52:35	    2	  13:53:32              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
26-03-11	Refresh	  Computer	    SYSTEM	    Patch test group	          Intune IT Test Group	29863000011693001	    Retry Collection	  15:15:35	    2	  15:16:33              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
```

```javascript
  [ 2026-03-11 13:53:29:887 ] [ 20532 ] [INFO] PrePostData : {
   "S-1-5-18" : {
      "29863000011693001" : {
         "29863000011889095" : "User notification processed.\t 11-03-2026 13:53:11",
         "29863000011889097" : "Test_CloseAllApps.ps1 script execution succeeded with error code : 0\t 11-03-2026 13:53:13",
         "29863000011889099" : "Skipped as no patch/software has been installed.\t 11-03-2026 13:53:24",
         "CollectionStartedStatusSent" : 1,
         "DeploymentCompleted" : 1,
         "PatchOrSoftwareInstalled" : 1,
         "PreDepActionsCompleted" : 1,
         "ProcessedActionIDs" : "29863000011889095,29863000011889097,29863000011889099",
         "RebootRequired" : 0,
         "UserNotificationPerformed" : 1
      }
   }
  "S-1-5-18" : {
      "29863000011693001" : {
         "29863000011889095" : "User notification processed.\t 11-03-2026 15:16:14",
         "29863000011889097" : "Test_CloseAllApps.ps1 script execution succeeded with error code : 0\t 11-03-2026 15:16:16",
         "29863000011889099" : "Skipped as no patch/software has been installed.\t 11-03-2026 15:16:25",
         "CollectionStartedStatusSent" : 1,
         "DeploymentCompleted" : 1,
         "PatchOrSoftwareInstalled" : 1,
         "PreDepActionsCompleted" : 1,
         "ProcessedActionIDs" : "29863000011889095,29863000011889097,29863000011889099",
         "RebootRequired" : 0,
         "UserNotificationPerformed" : 1
      }
   }
}
```



