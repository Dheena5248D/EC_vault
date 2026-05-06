---
notion_id: "32543c23-a5e2-8026-a9ed-ded8d1ad628d"
notion_last_edited: "2026-03-16T12:38:00.000Z"
tags:
  - "manual-deployment"
  - "deployment policy"
  - "reboot prompt"
  - "post reboot"
resolved: "False"
problem tags:
  - "Cx wants to know which coll trigred a reboot"
Date: "2026-03-16"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003455692744"
---



# Problem:

The Cx gets a reboot notification on 11/3/26 10:20  and wants to find which deployment trigged it



# Analysis:

Base on the logs  reboot is triggered by remote tolls and by collections so view

# Log trace

```javascript
Local Computer Name                       -> LU-GD100B4 
Local Computer IP Address                 -> 172.17.1.51
DC Distribution Server  Name      			-> manengine01-sj1 
```

```javascript
SetSize width = 500	height = 329[ 2026-03-11 10:20:02:551 ] [ 28808 ] [INFO] Registry Key Value "dcToolsPshutdownMessage"  is Your computer will be Shutdown/Restart by the Administrator. Postpone/Skip the operation if necessary. 
[ 2026-03-11 10:20:02:554 ] [ 28808 ] [INFO] [PostponeWindowCallback] => Timer to set : 0 Mins , 30 Secs
[ 2026-03-11 10:20:02:555 ] [ 28808 ] [INFO] [PostponeWindowCallback] => Postpone Skip Enabled
[ 2026-03-11 10:20:02:555 ] [ 28808 ] [INFO] [PostponeWindowCallback] => Postpone Skip Remaining: 1
[ 2026-03-11 10:20:02:557 ] [ 28808 ] [INFO] RAW instruction : DELETE_FOOTPRINT RCVD
[ 2026-03-11 10:20:02:557 ] [ 28808 ] [INFO] Product code is 2
[ 2026-03-11 10:20:02:581 ] [ 28808 ] [INFO] Product code is 2
[ 2026-03-11 10:20:02:581 ] [ 28808 ] [INFO] [Rebranding] => Permanently hide powered by : 0
[ 2026-03-11 10:20:02:581 ] [ 28808 ] [INFO] [Rebrand] => Showing powered by
[ 2026-03-11 10:20:02:583 ] [ 28808 ] [INFO] RAW instruction : SET_HEIGHT_309 RCVD
[ 2026-03-11 10:20:02:583 ] [ 28808 ] [INFO] Need to set height to 309
[ 2026-03-11 10:20:02:583 ] [ 28808 ] [INFO] 
```

```javascript
26-03-11	Refresh	  Computer	    SYSTEM	    Patch test group	[Stage 0 Deployment] Test Computers	38773000015546501	    Retry Collection	  09:48:08	    2	  10:15:13DC_ALLOWSKIP_REBOOT(skppd)      RETRY_UNTIL_SUCCESS	   --
26-03-11	Refresh	  Computer	    SYSTEM	          APD Deploy	[Stage 3 - All User PCs] OS & Applications Updates	38773000015559003	      SCHEDULED_SKIP	  10:15:35	    2	  10:16:49              DC_NO_REBOOT     CONFIGURATION_STAGED	   --
26-03-11	Refresh	  Computer	    SYSTEM	          APD Deploy	[Stage 1 - EIT] Antivirus Updates	38773000015425883	      New Collection	  10:16:53	    2	  10:17:46              DC_NO_REBOOT                  SUCCESS	   --
26-03-11	Refresh	  Computer	    SYSTEM	          APD Deploy	    [Stage 1 - EIT] OS Upgrade	38773000015485953	      New Collection	  10:17:47	    2	  10:18:38              DC_NO_REBOOT                  SUCCESS	   --
26-03-11	Refresh	  Computer	    SYSTEM	          APD Deploy	[Stage 3 - All User PCs] Antivirus Updates	38773000015557245	      New Collection	  10:18:39	    2	  10:19:31              DC_NO_REBOOT                  SUCCESS	   --
```



```javascript
26-03-11,----,----,----,----,----,----,POSTPONE_REBOOT,YES,1773249616,1773264016,14400,TOOLS_REBOOT
```

