---
notion_id: "34a43c23-a5e2-803e-997a-c5d4deaf0d14"
notion_last_edited: "2026-04-22T12:59:00.000Z"
tags:
  - "manual-deployment"
  - "status_update"
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-22"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003606032226"
---

# Issue:

Cx reported that the patch deployment status was not updated in the manual deployment tasks were several machines despite the patch was installed to the machine via an external update and it remains in yet to apply for a extended period of time 

# Analysis:

The configuration was processed on March 12, where the configuration exited due to the collection schedule time not reached,

kindly collect configuration pdf to analyse further.

# Log traces:

```prolog
DesktopCentral Server Name                -> UKWBPMEECINF01.CIMBUK.CIMBDomain.com
DesktopCentral Server IPAddress           -> 172.31.3.39
DesktopCentral Agent Version              -> 11.5.2605.13.W 
Local Computer Name                       -> CIMBUK-NB-02 
Local Computer IP Address                 -> 172.31.1.32 
DC Distribution Server Enabled            -> no
The remote office name is                 -> Local Office 
The Agent Machine Resource Id is given by -> 1202 
```



```prolog
[ 2026-03-12 22:50:35:249 ] [ 24952 ] [INFO] ProcessCollections : ********* Collection Started for collectionID : 12610 and Name : March Patches - London Endpoints ********* 
[ 2026-03-12 22:50:35:249 ] [ 24952 ] [INFO] GetTimeInSeconds : Time in Second : 1773355835
[ 2026-03-12 22:50:35:249 ] [ 24952 ] [INFO] ProcessCollActivePeriod: collstarttime : 1773360000 collendtime : -1 currentTimeInSec : 1773355835
[ 2026-03-12 22:50:35:249 ] [ 24952 ] [INFO] ProcessCollActivePeriod:As the current system time is less than the scheduled time. Hence the patches/softwares will be installed in the upcoming cycles. 
[ 2026-03-12 22:50:35:249 ] [ 24952 ] [INFO] CheckifCollectioninRetryNACollections : collectionid : 12610 is in retry
[ 2026-03-12 22:50:35:249 ] [ 24952 ] [INFO] WriteStatusinRegistry : Scheduled time not reached. The configuration will be applied on next upcoming cycles !!! 
[ 2026-03-12 22:50:35:250 ] [ 24952 ] [INFO] **************************************************************************
[ 2026-03-12 22:50:35:250 ] [ 24952 ] [INFO] ManageCollectionHolders: Source Collection Type is Retry Collection
[ 2026-03-12 22:50:35:250 ] [ 24952 ] [INFO] ManageCollectionHolders: Destination Collection Type is Retry Collection
[ 2026-03-12 22:50:35:250 ] [ 24952 ] [INFO] **************************************************************************
[ 2026-03-12 22:50:35:250 ] [ 24952 ] [INFO] OS_PLATFORM=1 not added
```



```prolog
26-03-12	Refresh	  Computer	    SYSTEM	                    	March Patches - London Endpoints	12610	      New Collection	  15:40:16	    2	  15:40:16                  SKIPPED	
```

