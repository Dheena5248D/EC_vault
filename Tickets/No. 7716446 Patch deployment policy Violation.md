---
notion_id: "33543c23-a5e2-80eb-ad8d-f0276d9e2fa7"
notion_last_edited: "2026-04-05T07:05:00.000Z"
tags:
  - "APD"
  - "patch-deployment"
resolved: "False"
Difficulty: "3"
problem tags:
  - "collection struck at ready to execute"
  - "post reboot not working"
  - "patch not deleted from the agent after deployment"
Solved by: "ME"
Date: "2026-04-02"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003530858123"
---

# Issue:

The Cx chosen, Friday & Sunday as Deployment time. But the driver patch has been redeployed on Monday

# Analysis:

On analyzing the log The Patch outside deployment window option is enabled under deployment settings of APD and set to force deploy to unpatched systems after they have missed 1 day. 

The patch can’t be deployed on  29/03/2026(Sunday) because the system was not alive the system went down on 27/03/2026 at 20:12 (Friday) and came online on 30/03/2026 08:53:38(Monday).

Because of the patch can’t be deployed on Sunday(deployment window) the deadline was crossed and the agent started deployment on Monday.

# Log traces:

```sql
Local Computer Name                       -> AE-5CG51130F2 
Local Computer IP Address                 -> 192.168.1.128 
DesktopCentral Agent Version              -> 11.4.2528.28.W 
System Time ZONE offset is given by : GMT+4:0 
```

```sql
[ 2026-03-30 08:54:49:466 ] [ 9352 ] [INFO] Task ID : 980112
[ 2026-03-30 08:54:49:466 ] [ 9352 ] [ERROR] Updates other than 4 is found
[ 2026-03-30 08:54:49:466 ] [ 9352 ] [INFO] Definition Update not found for the Task ID : 980112
[ 2026-03-30 08:54:49:466 ] [ 9352 ] [INFO] PatchResource modified. Need to send collection status.
[ 2026-03-30 08:54:49:466 ] [ 9352 ] [INFO] IsPatchScanDone : No Patch scan has been done in this refresh cycle.
[ 2026-03-30 08:54:49:466 ] [ 9352 ] [INFO] Patch resource modified and patch scan has not been modified in this refresh cycle. Hence patch scan needed
[ 2026-03-30 08:54:49:466 ] [ 9352 ] [ERROR] IsFileExist : The File Name C:\Program Files (x86)\ManageEngine\UEMS_Agent\data\patch-install-history.json is not found 2
[ 2026-03-30 08:54:49:466 ] [ 9352 ] [INFO] operation : GetDeadlineForDeploymentProps; collection_id : 2401; deadline_time : "GMT"; deadline_preferred_days : 1; force_reboot_option : 2;
[ 2026-03-30 08:54:49:466 ] [ 9352 ] [INFO] ProcessPatchDirectDownload already processed. Loading LastDirectDownloadState : 1
[ 2026-03-30 08:54:49:466 ] [ 9352 ] [INFO] DirectDownloadEnabled : TRUE
[ 2026-03-30 08:54:49:474 ] [ 9352 ] [INFO] ProcessDeploymentPolicies : Successfully downloaded deployment-policies.xml 
[ 2026-03-30 08:54:49:483 ] [ 9352 ] [INFO] ProcessDeploymentPolicies : Sucessfully loaded the deployment policies group .. 
[ 2026-03-30 08:54:49:483 ] [ 9352 ] [INFO] ProcessDeploymentSetting : Configuration deployed using deployment policy with id : 1801 
[ 2026-03-30 08:54:49:483 ] [ 9352 ] [INFO] ProcessSechudularOption : Configured the option such as to install the patches/softwares at any policy. 
[ 2026-03-30 08:54:49:483 ] [ 9352 ] [INFO] template_id : 1801; template_name : "IMEA-Win-Clients-APD"; time_zone : "--"; week_type_patch_tuesday : FALSE; install_option : 3; enable_staging : FALSE;
[ 2026-03-30 08:54:49:483 ] [ 9352 ] [INFO] operation : process_deployment_template; config_policy : StartUp; install_on_startup : TRUE; install_on_refresh : TRUE; remarks : "configured the option such as to install the patches/softwares at any policy";
[ 2026-03-30 08:54:49:483 ] [ 9352 ] [INFO] GetTimeInSeconds : Time in Second : 1774846489
[ 2026-03-30 08:54:49:483 ] [ 9352 ] [INFO] template_id : 1801; temp_window_id : 16812; weeks_to_process : 1,2,3,4,5; week_days_to_process : 1,6; window_date : 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31; window_months : 0,1,2,3,4,5,6,7,8,9,10,11; window_start_time : 06:30; window_end_time : 10:30
[ 2026-03-30 08:54:49:483 ] [ 9352 ] [INFO] template_id : 1801; temp_window_id : 16813; weeks_to_process : 1,2,3,4,5; week_days_to_process : 1,6; window_date : 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31; window_months : 0,1,2,3,4,5,6,7,8,9,10,11; window_start_time : 16:30; window_end_time : 21:00
```

```sql
26-03-27	         Logoff	  20:12:55	       20:12:56
26-03-30	        StartUp	  08:53:38	
```

```sql
[ 2026-03-30 08:54:49:487 ] [ 9352 ] [INFO] operation : FindPrevDeploymentWindows; valid_deployment_date : 2026-3-29; current_time : 1774846489; window_start_time : 1774751400; window_end_time : 1774765800; check_from_in_reverse : 1774846418; check_till_in_reverse : 1774626811;
[ 2026-03-30 08:54:49:487 ] [ 9352 ] [INFO] operation : FindPrevDeploymentWindows; max_window_count : 1; return_value : TRUE; remarks : "max window count reached";
[ 2026-03-30 08:54:49:487 ] [ 9352 ] [INFO] operation : process_agent_not_live_during_deployment_window; remarks : "agent was not live during deployment window";
[ 2026-03-30 08:54:49:487 ] [ 9352 ] [INFO] GetTimeInSeconds : Time in Second : 1774846489
```

```sql
[ 2026-03-30 09:06:29:686 ] [ 9352 ] [INFO] SendConfigStatusUpdateEx : Data to Send to Server -> 
 <?xml version="1.0" encoding="UTF-8"?>
<agent-params>
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="COLL_STATUS" PARAM_VALUE="3" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="COLL_REMARKS" PARAM_VALUE="[i18n]dc.db.agent.config.common.colln_started[/i18n]" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="COLL_REMARKS_EN" PARAM_VALUE="Deployment is in progress." />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="NAME" PARAM_VALUE="AE-5CG51130F2" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="DOMAIN_NETBIOS_NAME" PARAM_VALUE="HWL-FAMILY" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="RESOURCE_ID" PARAM_VALUE="554103" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="DOMAIN_TYPE" PARAM_VALUE="2" />
```





