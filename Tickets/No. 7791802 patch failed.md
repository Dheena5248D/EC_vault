---
notion_id: "34a43c23-a5e2-8061-be40-c65ecb8dd00e"
notion_last_edited: "2026-04-22T12:56:00.000Z"
tags:
  - "patch-deployment"
  - "roll-back"
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-22"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003568939551"
---

# Issue:

Customer has reported the patch deployment failure for the machine WUHCOMVLT01A.

# Analysis:

The patch 43393 is deployed on April 9, 10:27, and it is in the state of reboot pending. At 10:27 of the same day, the system rebooted. After the reboot, the patch is found missing and rolled back, so the patch is marked as failed in view.

[Haritha](https://medcsupport.zohodesk.com/agent/medcsupport/all/setup#setup/users-control/agents/220709001162370698) Kindly take care of the rollback

# Log traces:

```prolog
DesktopCentral Server Name                -> chipdvxr38.vistcorp.ad.visteon.com
DesktopCentral Server Flat Name           -> chipdvxr38 
DesktopCentral Product Code               -> DCEE 
 Local Computer Name                       -> wuhcomvlt01a
Local Computer IP Address                 -> 10.138.239.50,10.138.254.36 
DC Distribution Server Enabled            -> yes 
The remote office name is                 -> HIROSHIMA PLANT-7823  
The Agent Machine Resource Id is given by -> 20909 

[ 2026-04-09 10:27:14:631 ] [ 8388 ] [INFO] executeFileEx : Remarks from the CreateProcess is The requested operation is successful. Changes will not be effective until the system is rebooted.  for the executable C:\Windows\system32\wusa.exe "C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\43393-windows10.0-kb5075904-x64-2019.msu" /quiet /norestart

[ 2026-04-09 10:27:14:637 ] [ 8388 ] [INFO] 	 Successfully installed the Patch : 43393-windows10.0-kb5075904-x64-2019.msu : with remarks : [i18n]Reboot Pending[/i18n] 

26-04-09		10:39:42		Restart		The process C:\Windows\system32\SystemSettingsAdminFlows


[ 2026-04-09 10:44:49:300 ] [ 13096 ] [INFO] GetPatchScanResult : Queried scan result for Patch id: 43393 , Status : Missing, status Id : 122
[ 2026-04-09 10:44:49:318 ] [ 13096 ] [INFO] CPatchConfiguration::CheckIfPatchRolledBack : Machine has been rebooted after patch installation, yet listed as missing. Hence patch rolled

[ 2026-04-09 10:44:50:434 ] [ 13096 ] [INFO] Patch 43393 rolledback with error : Patch installed successfully, but rolled back on reboot.
```

