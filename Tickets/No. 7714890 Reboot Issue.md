---
notion_id: "33343c23-a5e2-80ab-ac30-e0efec7d3cc6"
notion_last_edited: "2026-03-31T11:33:00.000Z"
tags:
  - "post reboot"
resolved: "True"
problem tags:
  - "post server-upgrade"
  - "unexpected reboot"
  - "system reboot while other config is in process"
Date: "2026-03-30"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003529198219"
---

# Issue:

CX reported that some of the servers are not been triggered by reboot even though the patch installation status shows "Pending for reboot" he gas not enabled the "Excluded server from reboot”

# Analysis:

The patch deployment window is 23:45 to 03:00 within the deployment window as expected the patch deployment started at 00:49:15 and it ended at 03:36:31 which is outside the deployment window so the reboot is not happened



# Log trace:

```javascript
26-03-28	10802	JCB-NonCritical-Servers	43573		43573		APD Deploy	00:45:48	03:37:01	REBOOT_REQUIRED	[i18n]Reboot Pending[/i18n]
```



```javascript
[ 2026-03-29 11:14:40:023 ] [ 10764 ] [INFO] ProcessMaintenanceWindow : Template Window ID : 6909
[ 2026-03-29 11:14:40:023 ] [ 10764 ] [INFO] ProcessMaintenanceWindow : Configured to process on weeks : 4
[ 2026-03-29 11:14:40:023 ] [ 10764 ] [INFO] ProcessMaintenanceWindow : Configured to install on Days : 6
[ 2026-03-29 11:14:40:023 ] [ 10764 ] [INFO] ProcessMaintenanceWindow : Window Start Time : 23:45
[ 2026-03-29 11:14:40:023 ] [ 10764 ] [INFO] ProcessMaintenanceWindow : Window End Time : 03:00
```



```javascript
[ 2026-03-28 00:49:14:923 ] [ 7532 ] [INFO] executeFileEx : Current Working Directory : C:\Program Files (x86)\ManageEngine\UEMS_Agent\bin 
[ 2026-03-28 00:49:14:923 ] [ 7532 ] [INFO] executeFileEx : Executing Application Source : PackageInstaller.exe -i "43573-windows11.0-kb5078740-x64-2025.msu" -d "40378-windows11.0-kb5043080-x64_953449672073f8fb99badb4cc6d5d7849b9c83e8.msu"  -s "/quiet /norestart" 
[ 2026-03-28 00:49:14:923 ] [ 7532 ] [INFO] executeFileEx : Set Working Directory : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches 
[ 2026-03-28 00:49:15:430 ] [ 7532 ] [INFO] execute : Process successfully created for application PackageInstaller.exe -i "43573-windows11.0-kb5078740-x64-2025.msu" -d "40378-windows11.0-kb5043080-x64_953449672073f8fb99badb4cc6d5d7849b9c83e8.msu"  -s "/quiet /norestart" 
[ 2026-03-28 03:36:31:284 ] [ 7532 ] [INFO] executeFileEx : Remarks from the CreateProcess is The requested operation is successful. Changes will not be effective until the system is rebooted.  for the executable PackageInstaller.exe -i "43573-windows11.0-kb5078740-x64-2025.msu" -d "40378-windows11.0-kb5043080-x64_953449672073f8fb99badb4cc6d5d7849b9c83e8.msu"  -s "/quiet /norestart"
[ 2026-03-28 03:36:31:371 ] [ 7532 ] [INFO] Does not contain post-dep actions after post-reboot action. Can record patch history for rollback check.
```

