---
Status: "Done"
tags:
problem tags:
Solved by: "ME"
Date: "2026-04-17"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003590639896"
---

# Issue:

patches are deployed to the excluded custom group

# Analysis:

On analysing the APD is last is last modifed May 29, 2025 and till april 15 08:57 the filter is being success and patches are deployed in the system  PCULaptop-90 (which is not expected behaviour)  and from april 15 18:16 the filter is failing and target is marked as not apllicable(expected behaviour).

the patches are being installed from the may 29 to april 15 from the APD

on april 15 the apd target was modifed so the files are regenerated and from then the filter is failing and working as expected.

since the collections last modified time is may 2025 the logs are already roated and we cannot find the Root cause of why the system is not excluded before.

The apd is excluding the system PCULaptop-90 as expected now, kindly ask the customer to report the issue as soon as possible in the future so that we can find the Root cause.

# Log traces:

```prolog
26-02-02	46771000000317293	Patch Deployment  - Laptops	355397		355397		APD Deploy	15:25:29	15:25:48	SUCCESS	The operation completed successfully.
26-02-05	46771000000317293	Patch Deployment  - Laptops	354198		354198		APD Deploy	12:27:24	12:27:42	SUCCESS	The operation completed successfully.
26-02-10	46771000000317293	Patch Deployment  - Laptops	113003		113003		APD Deploy	23:01:53	23:19:41	REBOOT_REQUIRED	[i18n]Reboot Pending[/i18n]
26-02-10	46771000000317293	Patch Deployment  - Laptops	113008		113008		APD Deploy	23:19:42	23:21:08	REBOOT_REQUIRED	[i18n]Reboot Pending[/i18n]
26-02-18	46771000000317293	Patch Deployment  - Laptops	355941		355941		APD Deploy	23:00:23	23:00:50	SUCCESS	The operation completed successfully.
26-02-23	46771000000317293	Patch Deployment  - Laptops	356100		356100		APD Deploy	23:00:03	23:00:12	SUCCESS	The operation completed successfully.
26-03-05	46771000000317293	Patch Deployment  - Laptops	356571		356571		APD Deploy	09:29:32	09:29:42	SUCCESS	The operation completed successfully.
26-03-09	46771000000317293	Patch Deployment  - Laptops	113060		113060		APD Deploy	00:00:15	00:20:50	REBOOT_REQUIRED	[i18n]Reboot Pending[/i18n]
26-03-11	46771000000317293	Patch Deployment  - Laptops	356638		356638		APD Deploy	05:55:02	05:57:10	SUCCESS	The operation completed successfully.
26-03-13	46771000000317293	Patch Deployment  - Laptops	356758		356758		APD Deploy	02:59:25	03:01:19	SUCCESS	The operation completed successfully.
26-03-19	46771000000317293	Patch Deployment  - Laptops	356918		356918		APD Deploy	00:00:01	00:00:30	SUCCESS	The operation completed successfully.
26-04-01	46771000000317293	Patch Deployment  - Laptops	357378		357378		APD Deploy	02:59:31	02:59:51	SUCCESS	The operation completed successfully.
26-04-02	46771000000317293	Patch Deployment  - Laptops	357397		357397		APD Deploy	01:29:37	01:29:45	SUCCESS	The operation completed successfully.
26-04-03	46771000000317293	Patch Deployment  - Laptops	357485		357485		APD Deploy	00:00:03	00:03:33	SUCCESS	The operation completed successfully.
26-04-12	46771000000317293	Patch Deployment  - Laptops	113143		113143		APD Deploy	23:34:28	23:51:11	REBOOT_REQUIRED	[i18n]Reboot Pending[/i18n]
26-04-13	46771000000317293	Patch Deployment  - Laptops	357799		357799		APD Deploy	00:14:48	00:15:26	SUCCESS	The operation completed successfully.
26-04-15	46771000000317293	Patch Deployment  - Laptops	357880		357880		APD Deploy	02:59:44	03:00:02	SUCCESS	The operation completed successfully.
```

```prolog
 26-04-15	   StartUp	    SYSTEM	Patch Deployment  - Laptops	46771000000317293	  08:56:59	      Filter_Success	  08:57:39
 26-04-15	   StartUp	    SYSTEM	Patch Deployment  - Laptops	46771000000317293	  18:16:12	Target_Not_Applicable	  18:16:12
 26-04-15	   StartUp	    SYSTEM	Patch Deployment  - Laptops	46771000000317293	  18:22:18	Target_Not_Applicable	  18:22:18
 26-04-16	   Refresh	    SYSTEM	Patch Deployment  - Laptops	46771000000317293	  12:02:23	Target_Not_Applicable	  12:02:23
```

```prolog
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] @@@@@@@@@@@@@@@@@@@@@@@@ Inside  ProcessNewFilter method @@@@@@@@@@@@@@@@@
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] ProcessFilterComponentValue : filter_class_id = Remote Office ID , comparator_id = Equals , logical_operator = OR 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] GetValueAndCompare : Compare Value From Filter XML	   -> 46771000000103019 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] GetValueAndCompare : Retrieved Value From Local Machine  -> 46771000000103019
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] ProcessNewFilter : Main filter process succeeded 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] ProcessNewFilter: processComputerSubFilter skipped for computer config 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] ProcessFilterComponentValue : filter_class_id = Custom Group , comparator_id = Not Equals , logical_operator = AND 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] @@@@@@@@ Inside FilterByCustomGroupMembers Method @@@@@@@@ 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] gv_isCustomGroupJSON 1
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] FilterByCustomGroupMembers : As the custom Group JSON files are added, the CG validation is proceeded with the new file
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] @@@@@@@@ Inside FilterByCustomGroupsAsJSON Method @@@@@@@@ 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] FilterByCustomGroupsAsJSON : To check whether the given cg-id is present in the custom group metadata
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] FilterByCustomGroupsAsJSON : Param Value -> 46771000064881591 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [ERROR] FilterByCustomGroupsAsJSON :  Local path for CG meta data  : C:\Program Files (x86)\ManageEngine\UEMS_Agent\data\cg-meta-data.xml
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] Attempting to read MultiDomainCGMetaData
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] FilterByCustomGroupsAsJSON : Setting version as it is not null..!!!
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] FilterByCustomGroupsAsJSON : No diff found so loaded from local CG id File Path : C:\Program Files (x86)\ManageEngine\UEMS_Agent\data\custom-groups\46771000064881591.json
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] getApplicableStaticGroups : Inside getApplicableStaticGroups
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] getApplicableStaticGroups : The static group ids are:46771000067353289,46771000064881591,46771000072926451,
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] getApplicableStaticGroups : Completed getApplicableStaticGroups
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] getApplicableStaticGroups : Completed getApplicableStaticGroups
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] FilterByCustomGroupsAsJSON : checking if any declined static group id is in applicable static group id
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] FilterByCustomGroupsAsJSON : checking if any declined static group id is in applicable static group id
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] FilterByCustomGroupsAsJSON : The given group id is present already in the list of static groups in registry..!
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] FilterByCustomGroupsAsJSON : process completed 0
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] FilterByCutomGroupMembers : Excluded Type -> Loggedon user name (null) or loggedon computer name PCULaptop-90 is available in the custom group 46771000064881591 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] @@@@@@@@ End Of FilterByCutomGroupMembers Method @@@@@@@@ 
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] @@@@@@@@@@@@@@@@@@@@@@@@ End of  ProcessNewFilter method @@@@@@@@@@@@@@@@@
[ 2026-04-15 18:16:12:433 ] [ 8652 ] [INFO] @@@@@@@@ End Of ProcessFilter Method @@@@@@@@ 
[ 2026-04-15 18:16:12:435 ] [ 8652 ] [INFO] This collection is APD/TG. Hence deleting task_status from the registry
[ 2026-04-15 18:16:12:435 ] [ 8652 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-04-15 18:16:12:435 ] [ 8652 ] [INFO] deleteValue:  Delete value task_status success! 
[ 2026-04-15 18:16:12:435 ] [ 8652 ] [INFO] Collection Patch Deployment  - Laptops is not applicable for this target computer or target user. 
```

```prolog
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [INFO] @@@@@@@@ Inside ProcessFilter Method @@@@@@@@ 
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [INFO] @@@@@@@@@@@@@@@@@@@@@@@@ Inside  ProcessNewFilter method @@@@@@@@@@@@@@@@@
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [INFO] ProcessFilterComponentValue : filter_class_id = Remote Office ID , comparator_id = Equals , logical_operator = OR 
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [INFO] ProcessFilterComponentValue : isExcludeSubOU value = 0 
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [INFO] ProcessFilterComponentValue : DomainType value = 1 
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [INFO] GetValueAndCompare : Compare Value From Filter XML	   -> 46771000000103019 
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [INFO] GetValueAndCompare : Retrieved Value From Local Machine  -> 46771000000103019
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [INFO] ProcessNewFilter : Main filter process succeeded 
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [INFO] ProcessNewFilter: processComputerSubFilter skipped for computer config 
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [INFO] @@@@@@@@@@@@@@@@@@@@@@@@ End of  ProcessNewFilter method @@@@@@@@@@@@@@@@@
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [INFO] @@@@@@@@ End Of ProcessFilter Method @@@@@@@@ 
[ 2026-04-15 08:56:59:557 ] [ 8604 ] [INFO] Collection Patch Deployment  - Laptops -> Filter Successed. Proceeding to apply the configuration. 
```





