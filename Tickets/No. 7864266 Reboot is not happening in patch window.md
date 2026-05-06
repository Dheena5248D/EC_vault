---
notion_id: "35043c23-a5e2-8074-b504-fb435ef1a401"
notion_last_edited: "2026-04-28T05:48:00.000Z"
tags:
resolved: "False"
problem tags:
Date: "2026-04-28"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003607026355"
---

# Issue:

patch being displayed as **"Pending Reboot"** despite having a reboot policy configured within the Automated Patch Deployment (APD) task window.

# Analysis:



# Log traces:

```sql
[ 2026-04-21 19:38:18:301 ] [ 28164 ] [INFO] operation : ConstructRebootRequiredProps; collection_id : 111609000000860221; config_id : 163; restart_option : 1; is_exclude_server : FALSE;
[ 2026-04-21 19:38:18:318 ] [ 28164 ] [INFO] operation : ProcessRebootPolicy; reboot_required_reason_id : 0; remarks : "Temporarily assigning as not-applicable";
[ 2026-04-21 19:38:18:331 ] [ 28164 ] [INFO] GetPerformNoDeploymentSuccessForActionID: action_id : 111609000000858190; proceed_on_failure : TRUE
[ 2026-04-21 19:38:18:331 ] [ 28164 ] [INFO] GetTimeInSeconds : Time in Second : 1776829098
[ 2026-04-21 19:38:18:331 ] [ 28164 ] [INFO] GetCurrentTimeInSecondsWithDayLightBias : Time in Second : 1776825498
[ 2026-04-21 19:38:18:332 ] [ 28164 ] [INFO] [UpdateDepSetting] => Enter fn. Going to update dep settins for templId 111609000000799090
[ 2026-04-21 19:38:18:355 ] [ 28164 ] [INFO] [SaveRbtJson] => Starting to save
[ 2026-04-21 19:38:18:356 ] [ 28164 ] [INFO] [SaveRbtJson] => Saved Json
[ 2026-04-21 19:38:18:358 ] [ 28164 ] [INFO] [UpdateDepSetting] => Successfully updated depSettings for tempate id
[ 2026-04-21 19:38:18:358 ] [ 28164 ] [INFO] [ProcessRebootPolicy] => Updated depSettings
[ 2026-04-21 19:38:18:359 ] [ 28164 ] [INFO] ProcessDeploymentPolicies : Successfully downloaded deployment-policies.xml 
[ 2026-04-21 19:38:18:377 ] [ 28164 ] [INFO] ProcessDeploymentPolicies : Sucessfully loaded the deployment policies group .. 
[ 2026-04-21 19:38:18:377 ] [ 28164 ] [INFO] ProcessSechudularOption : Configured the option such as to install the patches/softwares at any policy. 
[ 2026-04-21 19:38:18:377 ] [ 28164 ] [INFO] template_id : 111609000000799090; template_name : "Auto Patch Ring 3 - All non-IT"; time_zone : "--"; week_type_patch_tuesday : FALSE; install_option : 3; enable_staging : FALSE;
[ 2026-04-21 19:38:18:377 ] [ 28164 ] [INFO] operation : process_deployment_template; config_policy : AppCtrlPolicyDeployment; install_on_startup : TRUE; install_on_refresh : TRUE; remarks : "configured the option such as to install the patches/softwares at any policy";
[ 2026-04-21 19:38:18:377 ] [ 28164 ] [INFO] GetTimeInSeconds : Time in Second : 1776825498
[ 2026-04-21 19:38:18:378 ] [ 28164 ] [INFO] template_id : 111609000000799090; temp_window_id : 111609000000858193; weeks_to_process : 3; week_days_to_process : 3,4; window_date : 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31; window_months : 0,1,2,3,4,5,6,7,8,9,10,11; window_start_time : 17:00; window_end_time : 23:59
[ 2026-04-21 19:38:18:378 ] [ 28164 ] [INFO] GetTimeInSeconds : Time in Second : 1776819600
[ 2026-04-21 19:38:18:378 ] [ 28164 ] [INFO] GetTimeInSecondsWithDayLightBias : Time in Second : 1776816000
[ 2026-04-21 19:38:18:378 ] [ 28164 ] [INFO] GetTimeInSeconds : Time in Second : 1776844740
[ 2026-04-21 19:38:18:378 ] [ 28164 ] [INFO] GetTimeInSecondsWithDayLightBias : Time in Second : 1776841140
[ 2026-04-21 19:38:18:378 ] [ 28164 ] [INFO] GetTimeInSeconds : Time in Second : 1776829098
[ 2026-04-21 19:38:18:378 ] [ 28164 ] [INFO] GetTimeInSecondsWithDayLightBias : Time in Second : 1776825498
[ 2026-04-21 19:38:18:378 ] [ 28164 ] [INFO] param : time_to_check; time_zone : "--"; week_day : Tuesday; date : 21/4/2026; time : 19:38:18; timestamp : 1776825498;
[ 2026-04-21 19:38:18:378 ] [ 28164 ] [INFO] param : window_start_time; time_zone : "--"; week_day : Tuesday; date : 21/4/2026; time : 17:0:0; timestamp : 1776816000;
[ 2026-04-21 19:38:18:378 ] [ 28164 ] [INFO] param : window_end_time; time_zone : "--"; week_day : Tuesday; date : 21/4/2026; time : 23:59:0; timestamp : 1776841140;
[ 2026-04-21 19:38:18:379 ] [ 28164 ] [INFO] params : is_day_allowed_for_deployment; week_type : 1; week_day_to_check : 3; date_to_check : 21; month_to_check : 4; year_to_check : 2026;
[ 2026-04-21 19:38:18:379 ] [ 28164 ] [INFO] operation : get_week_number; month : 4; date : 21; year : 2026; day_of_week : 3; week_number : 3, is_last_week : 0;
[ 2026-04-21 19:38:18:379 ] [ 28164 ] [INFO] template_id : 111609000000799090; temp_window_id : 111609000000858193; valid_window : TRUE; window_start_time : 1776816000; window_end_time : 1776841140;
[ 2026-04-21 19:38:18:379 ] [ 28164 ] [INFO] template_id : 111609000000799090; temp_window_id : 111609000000858193; default_window : FALSE;
[ 2026-04-21 19:38:18:379 ] [ 28164 ] [INFO] operation : process_maintenance_window; remarks : "current time lies within atleast one maintanence window"; end_time : 1776840540;
[ 2026-04-21 19:38:18:379 ] [ 28164 ] [INFO] Returning from ProcessDeploymentSetting method with status 10010 
[ 2026-04-21 19:38:18:379 ] [ 28164 ] [INFO] [ProcessRebootPolicy][FORCE_IMM_SAFETY_CHECK] => Actual window end time retreived 1776841140 , ProcessDepSet Retval : 10010
[ 2026-04-21 19:38:18:379 ] [ 28164 ] [INFO] [ProcessRebootPolicy][FORCE_IMM_SAFETY_CHECK] => Since policy was force_immediately after deployment and current time is within deployment window, will add to Job FW and do normal processing
[ 2026-04-21 19:38:18:379 ] [ 28164 ] [INFO] [AddRbtJob] => Starting to add/modify a reboot job for CollnId : 111609000000860221
[ 2026-04-21 19:38:18:379 ] [ 28164 ] [INFO] [AddRbtJob] => Subree to add to : ForceJobs
```



```sql
26-04-21	AppCtrlPolicyDeployment	  Computer	    SYSTEM	          APD Deploy	Auto Patch Ring 3 Windows - All non-IT	111609000000860221	      SCHEDULED_SKIP	  18:00:42	    2	
```

