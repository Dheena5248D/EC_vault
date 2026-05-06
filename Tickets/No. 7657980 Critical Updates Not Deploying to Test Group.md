---
notion_id: "32743c23-a5e2-80b8-bca3-cfb7a6bb64b1"
notion_last_edited: "2026-03-26T13:24:00.000Z"
tags:
  - "APD"
  - "patch-deployment"
resolved: "False"
problem tags:
  - "apd not processed"
Date: "2026-03-19"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003491838511"
---



# Problem:

As per the task PDF, currently there are 2 patches missing for the above machine which is released on March 10 and detected as Missing on March 11 but not installed on the endpoint.

# Analysis:

The collection was last processed on 27/02/2026 but the patch was found missing at 11/03/2026.

After that the APD is not processed

# log traces:

```javascript
26-02-27	Refresh	  Computer	    SYSTEM	    Patch test group	STATIC-PATCH-R0-IT-PILOT-WINDOWS	32739000002229475	      New Collection	  13:24:29	    2	  13:25:29DC_ALLOWSKIP_REBOOT(skppd)                  SUCCESS	   --
```

```javascript
26-03-11 10:17:23	       APD	1773217043	1773152924

{
	"0" : 
	{
		"AffectedPatchStatus" : 
		{
			"43586" : "202",
			"43621" : "202"
		},
		"ResDBProdDetails" : [],
		"ResMCAVStatus" : 
```

