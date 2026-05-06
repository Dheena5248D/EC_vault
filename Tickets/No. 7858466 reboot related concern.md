---
notion_id: "34a43c23-a5e2-80e4-acd4-f0e4e293086b"
notion_last_edited: "2026-04-22T12:52:00.000Z"
tags:
  - "reboot"
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-22"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003604005783"
---

# Issue:

400009 which required reboot after the patch installation on the client machines. Hope reboot haven't triggered on the client machines.

# Analysis:

The patch 400009 is a reboot may require patch, which means that. We can't know the reboot status of the patch until the patch is deployed.

After deployment, the patch can return either "successfully installed" or "reboot required." This is entirely based on the system's environment

On the " Skip reboot for machines that do not require a reboot" option is enabled

If, after deployment, the patch returned "reboot required," then the agent initiates the reboot, and if the patch returned "Install success," then the reboot will not be triggered.

On analysing the log the patch was installed successfully without requiring a reboot, so a reboot was not performed.

Kindly convey that the reboot may require flow to the customer.

# Log traces:

```prolog
DesktopCentral Server Name                -> GRM-VULNSCAN.gruma1.de
DesktopCentral Agent Version              -> 11.5.2613.04.W 
DesktopCentral Product Code               -> VMP 
Local Computer Name                       -> GRM-FLOW 
DC Distribution Server Enabled            -> no 
Local Computer Domain controller          -> GRM-DC01 
DC Distribution Server Enabled            -> no 
The remote office name is                 -> Local Office 
The Agent Machine Resource Id is given by -> 2692 

```





```prolog
6-04-20	4201	APD-WINDOWS-DEFENDER	400009		400009		APD Deploy	03:50:17	03:50:58	SUCCESS	Unknown Error. Code : 0
26-04-20	4201	APD-WINDOWS-DEFENDER	400009		400009		APD Deploy	05:19:50	05:20:31	SUCCESS	Unknown Error. Code : 0
```



```plain text
[ 2026-04-20 05:30:09:443 ] [ 5608 ] [INFO] patchesPartiallyInstalled status : 0
[ 2026-04-20 05:30:09:443 ] [ 5608 ] [INFO] operation : ConstructRebootRequiredProps; remarks : "Not a reboot required collection. Hence skipped processing reboot required props.";
[ 2026-04-20 05:30:09:443 ] [ 5608 ] [INFO] ProcessRebootPolicy : Reboot policy is not enabled. Restart : 0
```

