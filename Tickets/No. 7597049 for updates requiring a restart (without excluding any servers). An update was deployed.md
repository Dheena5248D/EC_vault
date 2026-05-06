---
notion_id: "32043c23-a5e2-808d-9e94-f3bcdf0d7d83"
notion_last_edited: "2026-03-12T11:18:00.000Z"
tags:
  - "test and approve"
  - "post reboot"
resolved: "False"
problem tags:
Date: "2026-03-12"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003447583885"
---

# Problem:

Cx has post deployment of restart (if requires reboot) and (include server) but the restart didn’t happen.

# Analysis

```javascript
26-03-10	3319	RECETTE - SERVEUR - Mise a jour Non critique	113071		113071		Patch test group	00:50:08	00:50:19	REBOOT_REQUIRED	[i18n]dc.db.agent.patchinstall.already_inst[/i18n]
26-03-10	3319	RECETTE - SERVEUR - Mise a jour Non critique	113078		113078		Patch test group	00:50:20	00:51:22	SUCCESS	Unknown Error. Code : 0
26-03-10	3319	RECETTE - SERVEUR - Mise a jour Non critique	355348		355348		Patch test group	00:51:23	00:51:24	FAILURE	[i18n]Patch update delayed since application is used by another process.[/i18n]
```



```javascript
template_id : 1502; template_name : "SERVEUR - P2 -  Mise a jour Non critique";
```

```javascript
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] Inside processreboot policy
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] ShutdownBlocked : 0
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] ProcessDeploymentSetting : Configuration deployed using deployment policy with id : 1502 
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] Message : L’opération a réussi.  
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] Restart  : DC_NO_REBOOT ,timeoutToReboot  : -1 ,isthisMachineExcluded  : 0, rebootOnlyIfReq : 1
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] installStatus  : 1 ,isRebootRequired  : 0 ,isMarkedforScheduled(is10008)  : 0
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] blockShutdownStatus  : 0 
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] doReboot  : 0 
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] pConfResp -> doNotRebootnow  : 0 
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] rebootskipcount  : 0 
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] patchesPartiallyInstalled status : 0
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] ProcessRebootPolicy : Reboot policy is not enabled. Restart : 0
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] Current Message ID : 4. New Message ID : 18
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] Message ID : 18. No need to reinitiate msg handler.
[ 2026-03-10 01:10:08:583 ] [ 15428 ] [INFO] Last message id set to 18.
[ 2026-03-10 01:10:08:599 ] [ 15428 ] [INFO] Bytes Sent = 6160
[ 2026-03-10 01:10:08:599 ] [ 15428 ] [INFO] ProcessRebootPolicy : Sending exit message to dcmsghandler
[ 2026-03-10 01:10:08:615 ] [ 15428 ] [INFO] End of ProcessRebootPolicy ret : 0
[ 2026-03-10 01:10:08:615 ] [ 15428 ] [INFO] @@@@@@@@ End Of ProcessConfiguration Method @@@@@@@@ 
```

As per the logs deployment policy in the APD is not enabled with reboot

But the APD pdf shows otherwise 



So asked agent data folder to check the deployment policy.xml and server logs 

