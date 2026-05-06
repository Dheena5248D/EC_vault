---
notion_id: "34243c23-a5e2-80fa-af0e-d912269428d3"
notion_last_edited: "2026-04-14T07:23:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-14"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003385159088"
---

# Issue:

Test and approve not deploying patches

# Analysis:

On analysing the deployment of patches in the agent is functioning as expected.

But the patches in the screenshot like 356165, 353936, 354833 are superseded patch cannot be downloaded as it is no longer supported by the vendor.

kindly ask the customer to deploy latest patches

# Log traces:

```prolog
DesktopCentral Server Name                -> endpointcentral-agent0.manageengine.eu 
 DesktopCentral Agent Version              -> 11.5.2605.12.W 
Local Computer Name                       -> JCE-DT-HillC 
Local Computer IP Address                 -> 10.1.9.152 

 DC Distribution Server  Name      			-> ogc-apps 
```



```prolog
26-04-02	Refresh	  Computer	    SYSTEM	    Patch test group	                  PatchTesters	2407000000100447	      New Collection	  13:07:10	    2	  13:15:53              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	    0
26-04-02	Refresh	  Computer	    SYSTEM	    Patch test group	                  PatchTesters	2407000000100447	      New Collection	  14:37:08	    2	  14:37:36              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
26-04-02	Refresh	  Computer	    SYSTEM	    Patch test group	                  PatchTesters	2407000000100447	      New Collection	  16:07:10	    2	  16:07:38              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
26-04-13	Refresh	  Computer	    SYSTEM	    Patch test group	                  PatchTesters	2407000000100447	    Retry Collection	  09:11:19	    2	  09:17:37              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --

26-04-13	Refresh	  Computer	    SYSTEM	    Patch test group	                  PatchTesters	2407000000100447	    Retry Collection

```

```prolog
[ 2026-04-13 07:11:33:808 ] [ 20580 ] [INFO] PatchFile - 356637-googlechromestandaloneenterprise64.msi PatchID - 356637 PatchName - googlechromestandaloneenterprise64.msi
[ 2026-04-13 07:11:33:808 ] [ 20580 ] [INFO] 	 @@@@@@@@ Inside IsPatchPartiallySuperseded Method @@@@@@@@
[ 2026-04-13 07:11:33:813 ] [ 20580 ] [INFO] Patch ID : 356637 is partially superseded
[ 2026-04-13 07:11:33:813 ] [ 20580 ] [INFO] PatchId : 356637 is Partially superseded. So skipping it.
```

