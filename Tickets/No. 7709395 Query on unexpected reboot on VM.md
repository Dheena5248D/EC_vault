---
notion_id: "33343c23-a5e2-8077-a993-c604ec1e2df9"
notion_last_edited: "2026-03-31T11:39:00.000Z"
tags:
  - "reboot"
resolved: "False"
problem tags:
  - "unexpected reboot"
Date: "2026-03-30"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003524189518"
---

# Issue:

Machines are rebooted thrice on 27th March. There is no patches got installed too

# Analysis:

The restart is triggered by the Self service portal and not by the patch deployment,

# Log traces:

```javascript
[ 2026-03-27 09:24:25:025 ] [ 22104 ] [INFO] GetProcessID : Retrieved Session ID : 2 for the process explorer.exe 
[ 2026-03-27 09:24:25:025 ] [ 22104 ] [INFO] GetProcessID : Compare Session ID : 3 
[ 2026-03-27 09:24:25:026 ] [ 22104 ] [INFO] GetProcessID : Retrieved Session ID : 3 for the process explorer.exe 
[ 2026-03-27 09:24:25:026 ] [ 22104 ] [INFO] GetProcessID : Compare Session ID : 3 
[ 2026-03-27 09:24:25:026 ] [ 22104 ] [INFO] GetProcessID : Process ID for explorer.exe is 16452
[ 2026-03-27 09:24:25:027 ] [ 22104 ] [INFO] ExecuteConfiguration : OpenProcessToken -> Process opened successfully. 
[ 2026-03-27 09:24:25:034 ] [ 22104 ] [INFO] @@@ Inside RefreshScheduledAtTime() @@@
[ 2026-03-27 09:24:25:062 ] [ 22104 ] [ERROR] IsFileExist : Invalid Handle returned for C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patchCatalog\patchCatalog.json - 3
[ 2026-03-27 09:24:25:062 ] [ 22104 ] [INFO] String from Registry : 0409 and Integer after Conversion : 1033
[ 2026-03-27 09:24:25:062 ] [ 22104 ] [INFO] returning locale en_US
[ 2026-03-27 09:24:25:063 ] [ 22104 ] [INFO] User IE veriosn: 11.1882.26100.0
[ 2026-03-27 09:24:25:064 ] [ 22104 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-27 09:24:25:065 ] [ 22104 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-27 09:24:25:065 ] [ 22104 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-27 09:24:25:065 ] [ 22104 ] [INFO] SetUserIERegistryValues: User IE Registry Values backed up successfully
[ 2026-03-27 09:24:25:065 ] [ 22104 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-27 09:24:25:065 ] [ 22104 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-27 09:24:25:066 ] [ 22104 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-27 09:24:25:066 ] [ 22104 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-27 09:24:25:066 ] [ 22104 ] [INFO] executeinfo : Current Working Directory : C:\Program Files (x86)\ManageEngine\UEMS_Agent\bin 
[ 2026-03-27 09:24:25:066 ] [ 22104 ] [INFO] executeinfo : Executing Application Source : NativeUIHandler.exe 
[ 2026-03-27 09:24:25:066 ] [ 22104 ] [INFO] executeinfo : Set Working Directory : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\bin 
[ 2026-03-27 09:24:25:073 ] [ 22104 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-27 09:24:25:073 ] [ 22104 ] [INFO] executeinfo : Remarks from the CreateProcess is The operation completed successfully.  for the executable NativeUIHandler.exe 
[ 2026-03-27 09:24:25:073 ] [ 11572 ] [INFO] GetActiveSessionId : WTSGetActiveConsoleSessionId = 1
[ 2026-03-27 09:24:25:082 ] [ 11572 ] [INFO] GetProcessID : Retrieved Session ID : 3 for the process NativeUIHandler.exe 
[ 2026-03-27 09:24:25:082 ] [ 11572 ] [INFO] GetProcessID : Compare Session ID : 3 
[ 2026-03-27 09:24:25:082 ] [ 11572 ] [INFO] GetProcessID : Process ID for NativeUIHandler.exe is 1224
[ 2026-03-27 09:24:25:083 ] [ 11572 ] [INFO] ProcessID : 1224 opened successfully.
[ 2026-03-27 09:24:29:767 ] [ 22104 ] [INFO] Inside ProcessAndDispatchPipeMes Method 
[ 2026-03-27 09:24:29:767 ] [ 22104 ] [INFO] @@@ Inside CDCJson::StringToJson
[ 2026-03-27 09:24:29:767 ] [ 22104 ] [INFO] @@@ End of CDCJson::StringToJson
[ 2026-03-27 09:24:29:767 ] [ 22104 ] [INFO] ProcessAndDispatchPipeMes: ReqType -ProcessPatchCatalog has been received from pipe.
[ 2026-03-27 09:24:29:767 ] [ 22104 ] [INFO] Key dc.agent.msghand.ssp_patch_reboot_text not found
[ 2026-03-27 09:24:29:767 ] [ 22104 ] [INFO] 	 @@@@@@@@ Inside RebootSystem Method @@@@@@@@ 
[ 2026-03-27 09:24:29:767 ] [ 22104 ] [INFO] 	 Trying to take backup of Reboot history file for this cycle.
[ 2026-03-27 09:24:29:767 ] [ 22104 ] [INFO] 	 Reboot history backup creation failed
[ 2026-03-27 09:24:29:770 ] [ 22104 ] [INFO] RebootSystem : Initiated the InitiateSystemShutdown Method 
[ 2026-03-27 09:24:29:781 ] [ 22104 ] [INFO] RebootSystem : Successfully initiated the shutdown / restart .. 
[ 2026-03-27 09:24:29:781 ] [ 22104 ] [INFO] Product code is 2
[ 2026-03-27 09:24:29:781 ] [ 22104 ] [INFO] Key dc.db.agent.event.ssp_patch_reboot_msg&&&Patch Manager Plus not found
```



```javascript
2026-03-27       08:37:39           RESTART     PATCH                       08:37:44                PROCESSED       08:37:44
2026-03-27       08:55:24           RESTART     PATCH                       09:18:29                PROCESSED       09:18:29
2026-03-27       09:24:25           RESTART     PATCH                       09:24:29                PROCESSED       09:24:29
```



