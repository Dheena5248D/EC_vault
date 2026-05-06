---
notion_id: "34343c23-a5e2-80a9-a28f-d3bebdbc9a3c"
notion_last_edited: "2026-04-15T09:49:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-15"
---

# Issue:

A manually triggered job started as “Deploy immediately” is still in the “Yet to apply” state on all three servers even after 24 hours. I tried restarting the client servers, but the status remains unchanged.

# Analysis:

On analysing the log the collection was not applicable for the systems because the remote office of the systems are modified by the user from SYST-INST to syst.ceps.one but the target in the collection is remote office is SYST-INST so the target is not processed by the system and that is the reason for patches not deployed.

kindly ask the customer to modify the collection's target with correct remote office to deploy the patches

# Log traces:

```prolog
DesktopCentral Server Name                -> bhdpmpmgmt.e-ceps.cz 
DesktopCentral Agent Version              -> 11.5.2605.13.W 
DesktopCentral Product Code               -> PMP 
Local Computer Name                       -> tsfo-eisstyn
Local Computer IP Address                 -> 10.163.225.100 
The remote office name is                 -> syst.ceps.one 
```

```prolog
[ 2026-04-09 09:27:08:675 ] [ 2896 ] [INFO] The remote office name is                 -> syst.ceps.one 
```

```prolog
[08:36:44:200]|[04-09-2026]|[EventLogLogger]|[INFO]|[992]|[8a06e188-1441-4862-bac8-976c84dc5151]: DCEventLogUtil::addEvent --> Method starts here, eventID : 213 userName : x1kukucz resHashMap : {resourceID=76802, computerName=tsfo-eisstab, domainName=SYST, serviceTag=VMWARE-42 02 0C D7 A7 54 99 57-B4 32 A0 F1 90 43 29 0C} remarks : desktopcentral.webclient.admin.som.Computer_Move_RO_initiated updateTime : false customerID : 1|

```

```prolog
[ 2026-04-09 08:40:07:324 ] [ 1076 ] [INFO] @@@@@@@@ Inside ProcessFilter Method @@@@@@@@ 
[ 2026-04-09 08:40:07:324 ] [ 1076 ] [INFO] @@@@@@@@@@@@@@@@@@@@@@@@ Inside  ProcessNewFilter method @@@@@@@@@@@@@@@@@
[ 2026-04-09 08:40:07:324 ] [ 1076 ] [INFO] ProcessFilterComponentValue : filter_class_id = Remote Office ID , comparator_id = Equals , logical_operator = OR 
[ 2026-04-09 08:40:07:324 ] [ 1076 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-09 08:40:07:324 ] [ 1076 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-09 08:40:07:324 ] [ 1076 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-09 08:40:07:324 ] [ 1076 ] [INFO] GetValueAndCompare : Compare Value From Filter XML	   -> 3601 
[ 2026-04-09 08:40:07:324 ] [ 1076 ] [INFO] GetValueAndCompare : Retrieved Value From Local Machine  -> 3301
[ 2026-04-09 08:40:07:324 ] [ 1076 ] [INFO] ProcessNewFilter: processComputerSubFilter skipped for computer config 
[ 2026-04-09 08:40:07:324 ] [ 1076 ] [INFO] @@@@@@@@@@@@@@@@@@@@@@@@ End of  ProcessNewFilter method @@@@@@@@@@@@@@@@@
[ 2026-04-09 08:40:07:324 ] [ 1076 ] [INFO] @@@@@@@@ End Of ProcessFilter Method @@@@@@@@ 
[ 2026-04-09 08:40:07:324 ] [ 1076 ] [INFO] Collection tsfo is not applicable for this target computer or target user. 
```



