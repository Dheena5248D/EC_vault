---
notion_id: "34843c23-a5e2-80de-b732-fe2fc510ec11"
notion_last_edited: "2026-04-20T06:04:00.000Z"
tags:
resolved: "False"
problem tags:
Date: "2026-04-20"
ticket_url: "#7839627"
---

# Issue:



# Analysis:



# Log traces:

```prolog
26-04-16	4633000000251089	BQP_Monthly_Patch	44036		44036		APD Deploy	22:01:45	22:04:01	SUCCESS	The operation completed successfully.
26-04-16	4633000000251089	BQP_Monthly_Patch	106427		106427		APD Deploy	22:04:02	22:06:36	REBOOT_REQUIRED	[i18n]Reboot Pending[/i18n]
26-04-16	4633000000251089	BQP_Monthly_Patch	357395		357395		APD Deploy	22:06:37	22:06:48	SUCCESS	The operation completed successfully.
```

```prolog
26-04-16	Ondemand	  Computer	    SYSTEM	          APD Deploy	             BQP_Monthly_Patch	4633000000251089	      SCHEDULED_SKIP	  22:00:19	    2	  22:12:05DC_FORCE_REBOOT_IMMEDIATE(rbtcat0)                  SUCCESS	   --
26-04-16	Refresh	  Computer	    SYSTEM	          APD Deploy	             BQP_Monthly_Patch	4633000000251089	      New Collection	  23:35:51	    2	  23:37:05              DC_NO_REBOOT                  SUCCESS	   --
```

```prolog
[ 2026-04-16 22:12:01:777 ] [ 15272 ] [INFO] @@@ Inside PerformRebootAction for actionID : 4633000000659469 @@@[ 2026-04-16 22:12:01:777 ] [ 15272 ] [INFO] Configured to perform reboot action even if no deployment was success.[ 2026-04-16 22:12:01:777 ] [ 15272 ] [INFO] @@@ Inside SleepBetweenReboots() @@@
[ 2026-04-16 22:12:01:777 ] [ 15272 ] [INFO] GetTimeInSeconds : Time in Second : 1776341521
[ 2026-04-16 22:12:01:777 ] [ 15272 ] [INFO] @@@ End of SleepBetweenReboots() @@@
[ 2026-04-16 22:12:01:777 ] [ 15272 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-16 22:12:01:777 ] [ 15272 ] [INFO] Reboot operation will be processed in ProcessRebootPolicy()
[ 2026-04-16 22:12:01:777 ] [ 15272 ] [INFO] @@@ End of PerformRebootAction @@@
[ 2026-04-16 22:12:01:777 ] [ 15272 ] [INFO] All post-deployment actions have been executed successfully.
[ 2026-04-16 22:12:01:777 ] [ 15272 ] [INFO] @@@ ClearPrePostRegValue @@@
[ 2026-04-16 22:12:01:777 ] [ 15272 ] [INFO] PrePostData : {
   "S-1-5-18" : {
      "4633000000251089" : {
         "4633000000659468" : "Skipped as machine does not require reboot.\t 16-04-2026 22:01:45",
         "4633000000659469" : "Reboot action processed\t 16-04-2026 22:12:01",
         "CollectionStartedStatusSent" : 1,
         "DeploymentCompleted" : 1,
         "LastBootupTime" : 1763644923,
         "PatchOrSoftwareInstalled" : 1,
         "PreDepActionsCompleted" : 1,
         "ProcessedActionIDs" : "4633000000659468,4633000000659469",
         "RebootRequired" : 1
      }
   }
}
```

```prolog
[ 2026-04-16 22:12:07:569 ] [ 12592 ] [INFO] [WndProc] => Invalid postponedFor or is not reboot window. did not write postpone access log
[ 2026-04-16 22:12:07:569 ] [ 12592 ] [ERROR] MSGHANLDER_LOGGER::PrintLog Empty Access data so not printing it in the log
[ 2026-04-16 22:12:07:569 ] [ 12592 ] [INFO] [WndProc] => END MessageHandler
```

```prolog
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] operation : process_deployment_template; config_policy : Ondemand; install_on_startup : TRUE; install_on_refresh : TRUE; remarks : "configured the option such as to install the patches/softwares at any policy";
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] GetTimeInSeconds : Time in Second : 1776340820
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] template_id : 4633000000235007; temp_window_id : 4633000000659472; weeks_to_process : 3; week_days_to_process : 5; window_date : 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31; window_months : 0,1,2,3,4,5,6,7,8,9,10,11; window_start_time : 22:00; window_end_time : 02:00
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] GetTimeInSeconds : Time in Second : 1776340800
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] GetTimeInSecondsWithDayLightBias : Time in Second : 1776340800
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] GetTimeInSeconds : Time in Second : 1776268800
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] GetTimeInSecondsWithDayLightBias : Time in Second : 1776268800
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] GetTimeInSeconds : Time in Second : 1776340820
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] GetTimeInSecondsWithDayLightBias : Time in Second : 1776340820
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] param : time_to_check; time_zone : "--"; week_day : Thursday; date : 16/4/2026; time : 22:0:20; timestamp : 1776340820;
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] param : window_start_time; time_zone : "--"; week_day : Thursday; date : 16/4/2026; time : 22:0:0; timestamp : 1776340800;
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] param : window_end_time; time_zone : "--"; week_day : Thursday; date : 16/4/2026; time : 2:0:0; timestamp : 1776268800;
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] params : is_day_allowed_for_deployment; week_type : 1; week_day_to_check : 5; date_to_check : 16; month_to_check : 4; year_to_check : 2026;
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] operation : get_week_number; month : 4; date : 16; year : 2026; day_of_week : 5; week_number : 3, is_last_week : 0;
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] template_id : 4633000000235007; temp_window_id : 4633000000659472; valid_window : TRUE; window_start_time : 1776340800; window_end_time : 1776355200;
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] template_id : 4633000000235007; temp_window_id : 4633000000659472; default_window : FALSE;
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] operation : process_maintenance_window; remarks : "current time lies within atleast one maintanence window"; end_time : 1776354600;
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] Returning from ProcessDeploymentSetting method with status 10010 
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [ERROR] IsFileExist : The File Name C:\Program Files (x86)\ManageEngine\UEMS_Agent\\data\prepostdata.json is not found 2
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] Processed ActionID : 
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] Deployment policy return code : 10010
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] IsStagingEnabled : TRUE
[ 2026-04-16 22:00:20:888 ] [ 15272 ] [INFO] IsScanNeeded : FALSE
```

