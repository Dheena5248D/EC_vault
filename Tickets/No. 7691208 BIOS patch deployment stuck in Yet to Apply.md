---
notion_id: "32d43c23-a5e2-8023-a2a1-f96ce1590432"
notion_last_edited: "2026-03-24T16:11:00.000Z"
tags:
  - "patch-deployment"
resolved: "False"
problem tags:
  - "collection struck at ready to execute"
Date: "2026-03-24"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003511279279"
---

# Issue:

BIOS patch deployment stuck in Yet to Apply

# Analysis:

- The cellection is set to depoy only on sundays
- The filter is succeeded on 19/03/2026 but it due it dosn’t fall on the deployment window it is not processed
- On deployment window 22/03/2026 the collection is not processed.
- may need client data folder for furthur validation
# Log traces:

```prolog
26-03-19	Refresh	  Computer	    SYSTEM	       Install Patch	     OptiPlex 3090 BIOS Update	100754000018446061	      New Collection	  09:02:51	    2	  09:02:51              DC_NO_REBOOT                  SKIPPED	   --
26-03-19	Refresh	  Computer	    SYSTEM	       Install Patch	     OptiPlex 3090 BIOS Update	100754000018446061	      New Collection	  10:31:57	    2	  10:31:57              DC_NO_REBOOT                  SKIPPED	   --
```

 

