---
notion_id: "33343c23-a5e2-80f4-8b31-d49b01445cf6"
notion_last_edited: "2026-04-02T10:21:00.000Z"
tags:
  - "patch-deployment"
  - "APD"
resolved: "False"
problem tags:
  - "patch not deployed in apd"
Solved by: "Others"
Date: "2026-03-30"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003519755794"
---

# Issue:

Patch deployment stuck at yet to apply

# Analysis:

The collection "U_Office_Logon" is configured to deploy patches only at system startup. During startup, the collection "G_GPO_Windows Updates_Win11" a custom registry configuration is processed. However, this process crashes, and as a result, the other collections are not processed during startup.

During the subsequent refresh cycle, the "U_Office_Logon" collection is processed. At that time, the current time falls outside the deployment window. Since the policy is configured to install only during startup, the patch process does not begin. Therefore, the patch deployment status remains in the state of "Yet to apply."



Based on the log analysis, it is observed that the customer has deployed a registry configuration which crashed on the agent side and which is the reason for no other deployment happening in the agent side.
This issue may occur if there are leading or trailing spaces in the Subkey field while configuring the registry.

# Log traces:

```sql
26-03-25	StartUp	  Computer	    SYSTEM	     Custom Registry	   G_GPO_Windows Updates_Win11	49253	      New Collection	  23:06:53	    2	
26-03-25	Refresh	  Computer	    SYSTEM	          APD Deploy	WKS-Aktualisierung ohne IT - 1 	8708	    Retry Collection	  23:56:09	    2	  00:00:45DC_FORCE_REBOOT_IMMEDIATE(skppd)     CONFIGURATION_STAGED	   --
26-03-26	Refresh	  Computer	    SYSTEM	       Install Patch	                U_Office_Logon	53402	      SCHEDULED_SKIP	  00:00:45	    2	  00:00:45              DC_NO_REBOOT                  SKIPPED	   --
```

```sql
[ 2026-03-25 23:06:53:798 ] [ 6032 ] [INFO] ProcessCollections : ********* Collection Started for collectionID : 49253 and Name : G_GPO_Windows Updates_Win11 ********* 
[ 2026-03-25 23:06:53:808 ] [ 6032 ] [INFO] ****************************************************************************** 
[ 2026-03-25 23:06:53:808 ] [ 6032 ] [INFO] Started to process Custom Registry configuration 
[ 2026-03-25 23:06:53:808 ] [ 6032 ] [INFO] customregistry.xml
[ 2026-03-25 23:06:53:808 ] [ 6032 ] [INFO] @@@@@@@@ Inside LoadAllNecessaryXMLFiles Method @@@@@@@@ 
[ 2026-03-25 23:06:53:808 ] [ 6032 ] [INFO] Creating DataObject for Dynamic variables from C:\Program Files (x86)\ManageEngine\UEMS_Agent\\data\dynamic-variables.xml 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] @@@@@@@@ End Of LoadAllNecessaryXMLFiles Method @@@@@@@@ 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] Message : Der Vorgang wurde erfolgreich beendet.  
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] UpdateConfigDataStatus : The Required SubKey is given by Software\AdventNet\DesktopCentral\DCAgent\CollectionHistory\49253 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] TrayIconStatusUpdate ::: value to write :: 1
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] GetTimeInSeconds : Time in Second : 1774476413
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] GetCurrentTimeInSecondsWithDayLightBias : Time in Second : 1774476413
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] Message : Der Vorgang wurde erfolgreich beendet.  
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] Message : Der Vorgang wurde erfolgreich beendet.  
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] @@@@@@@@ Inside ProcessCustomRegistry Method @@@@@@@@ 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [ERROR] ProcessCustomRegistry : Empty data in RegCustomKeyConfig ! 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] Credential UUID set as:
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : Header key (main): HKLM 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : Sub key (else): SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : valueName (else): TargetReleaseVersionInfo 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : valueData (else): 24H2 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] Message : Der Vorgang wurde erfolgreich beendet.  
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : CustomRegistry - Write registry value successful! 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : Header key (main): HKLM 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : Sub key (else): SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : valueName (else): ProductVersion 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : valueData (else): Windows 11 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] Message : Der Vorgang wurde erfolgreich beendet.  
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : CustomRegistry - Write registry value successful! 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : Header key (main): HKLM 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : Sub key (else): 	SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : valueName (else): TargetReleaseVersion 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : valueData (else): 1 
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] Message : Der Vorgang wurde erfolgreich beendet.  
[ 2026-03-25 23:06:53:825 ] [ 6032 ] [INFO] ProcessCustomRegistry : CustomRegistry - Write registry value successful! 
[ 2026-03-25 23:55:53:771 ] [ 4604 ] [INFO] Log open time: 2026-03-25 23:55:53:771
[ 2026-03-25 23:55:53:771 ] [ 4604 ] [INFO] =====> Time: 23:55:53 25/3/2026 
[ 2026-03-25 23:55:53:771 ] [ 4604 ] [INFO] Commmand Line Arg : refreshType  :Refresh 
[ 2026-03-25 23:55:53:771 ] [ 4604 ] [INFO] Commmand Line Arg : ismanualRefresh  :0 
[ 2026-03-25 23:55:53:771 ] [ 4604 ] [INFO] Commmand Line Arg : getSessionID :0 



[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] ProcessSechudularOption : Configured the option such as to install the patches/softwares at any policy. 
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] template_id : 7; template_name : "Deploy during System start up/login"; time_zone : "--"; week_type_patch_tuesday : FALSE; install_option : 1; enable_staging : FALSE;
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] operation : process_deployment_template; config_policy : Refresh; install_on_startup : TRUE; install_on_refresh : FALSE; status : apply_later; remarks : "configured the option such as not to install the patches/softwares at background. software will get installed at system bootup/user logon";
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] Returning from ProcessDeploymentSetting method with status 12 
[ 2026-03-26 02:56:08:774 ] [ 872 ] [ERROR] IsFileExist : The File Name C:\Program Files (x86)\ManageEngine\UEMS_Agent\\data\prepostdata.json is not found 2
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] Processed ActionID : 
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] Message : Der Vorgang wurde erfolgreich beendet.  
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] Deployment policy return code : 12
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] IsStagingEnabled : FALSE
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] Current time lies out of deployment window. Hence skipping patch deployment.
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] deleteValue:  Delete value CollectionStatus success! 
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] deleteCollectionStatusToBeGeneratedStatusFromRegistry : Deleted for Collection 53402
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] isAgentNotLiveDisabled : 0
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] ProcessDeploymentSetting : Configuration deployed using deployment policy with id : 7 
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] Install Option : 1
[ 2026-03-26 02:56:08:774 ] [ 872 ] [INFO] Configured the option such as patches will get installed at system bootup/user logon.
```



