---
notion_id: "34143c23-a5e2-807a-abee-c50acfae66e4"
notion_last_edited: "2026-04-13T09:07:00.000Z"
tags:
  - "patch-deployment"
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-13"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003565952519"
---

# Issue:

Microsoft Edge patches are failing to install on multiple endpoints

# Analysis:

The patch 113157 have download successfully but during execution it returned Error Code : 1603 , Error Message : Fatal error during installation.on analysing the collection pdf the error seems consitant over all the target endpoints



[Jeyakrithiga K](https://medcsupport.zohodesk.com/agent/medcsupport/all/setup#setup/users-control/agents/220709000392496752) kindly take care.

# Log traces:

```prolog
DesktopCentral Server Name                -> endpointcentral-agent6.manageengine.com
DesktopCentral Agent Version              -> 11.5.2605.12.W 
DesktopCentral Product Code               -> DCODEE
Local Computer Name                       -> 10-TL-W01
Local Computer IP Address                 -> 10.120.10.15 
DC Distribution Server  Name      			-> PCBFS10 
```



```prolog
26-04-07	60615000100767098	MS Edge Zero-Day Attemp#2	113157		60615000100767099		Install Patch	15:32:55	15:33:18	FAILURE	[i18n]Fatal error during installation[/i18n]
```

```prolog
[ 2026-04-07 15:33:01:181 ] [ 25120 ] [INFO] Executable FileName : 113157-microsoftedgeenterprise_146.0.3856.109_x64.msi
[ 2026-04-07 15:33:01:181 ] [ 25120 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-07 15:33:01:181 ] [ 25120 ] [INFO] 	 ******** Inside InstallPatch Method ******** 
[ 2026-04-07 15:33:01:181 ] [ 25120 ] [ERROR] IsFileExist : The File Name C:\Program Files (x86)\ManageEngine\UEMS_Agent\\data\custom-patch-remarks.json is not found 2
[ 2026-04-07 15:33:01:181 ] [ 25120 ] [INFO] IsRowsPresentInResultData : RowCount ->1 1
[ 2026-04-07 15:33:01:181 ] [ 25120 ] [INFO] getISwitch : criteria patchid = 113157 and languageid=0!!!
[ 2026-04-07 15:33:01:181 ] [ 25120 ] [INFO] IsRowsPresentInResultData : RowCount ->1 1
[ 2026-04-07 15:33:01:181 ] [ 25120 ] [INFO] getISwitch : iswitch for patchid : 113157 is /qn /norestart !!!
[ 2026-04-07 15:33:01:181 ] [ 25120 ] [INFO] installPatch : .msi file found 
[ 2026-04-07 15:33:01:181 ] [ 25120 ] [INFO] installPatch : installation directory : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches  
[ 2026-04-07 15:33:01:181 ] [ 25120 ] [INFO] installPatch : installationFileName : 113157-microsoftedgeenterprise_146.0.3856.109_x64.msi  
[ 2026-04-07 15:33:01:181 ] [ 25120 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-07 15:33:01:196 ] [ 25120 ] [INFO] GetTimeInSeconds : Time in Second : 1775590381
[ 2026-04-07 15:33:01:196 ] [ 25120 ] [INFO] executeFileEx : Current Working Directory : C:\Program Files (x86)\ManageEngine\UEMS_Agent 
[ 2026-04-07 15:33:01:196 ] [ 25120 ] [INFO] executeFileEx : Executing Application Source : C:\Windows\system32\msiexec.exe /i "C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\113157-microsoftedgeenterprise_146.0.3856.109_x64.msi" /qn /norestart 
[ 2026-04-07 15:33:01:196 ] [ 25120 ] [INFO] executeFileEx : Set Working Directory : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches 
[ 2026-04-07 15:33:01:552 ] [ 25120 ] [INFO] execute : Process successfully created for application C:\Windows\system32\msiexec.exe /i "C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\113157-microsoftedgeenterprise_146.0.3856.109_x64.msi" /qn /norestart 
[ 2026-04-07 15:33:18:185 ] [ 25120 ] [ERROR] Error Code : 1603 , Error Message : Fatal error during installation.  
[ 2026-04-07 15:33:18:185 ] [ 25120 ] [INFO] executeFileEx : Exit code for the application : 1603 
[ 2026-04-07 15:33:18:185 ] [ 25120 ] [INFO] executeFileEx : Remarks from the CreateProcess is Fatal error during installation.  for the executable C:\Windows\system32\msiexec.exe /i "C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\113157-microsoftedgeenterprise_146.0.3856.109_x64.msi" /qn /norestart 
```

