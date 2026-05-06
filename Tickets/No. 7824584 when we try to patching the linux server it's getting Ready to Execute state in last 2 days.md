---
notion_id: "34243c23-a5e2-809a-acd2-fa6cbc4bde55"
notion_last_edited: "2026-04-14T08:49:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-14"
---

# Issue:

linux patch status is showing as Ready to execute even though the agent connectivity having no issues.

# Analysis:

The  configuration “AZ-Maildaemon1_11-April-26” is created at Apr 11, 2026 12:41 PM and during next refresh which is happened 11 apr, 2026 13:38  on  agent the collection should be processed and the patches should have processed but the collection is not processed during the following refresh cycles 



To analyse furthur on this need the followings:

1. server logs
1. client-data folder
# Log traces:

```prolog
M_dcServerName:"I3LPATCHPLUSLNX.ITCINFOTECH.com"
M_agentVersion:"11.4.2528.17.W"
M_domainAdName:"linuxosgroup"
M_domainNetbiosName:"linuxosgroup"
M_localMachineName:"AZ-Maildaemon1"
M_productCode:"PMP"
```

```prolog
11-04-2026	refresh			13:38:11	13:38:53
11-04-2026	refresh			15:08:11	15:08:13
11-04-2026	refresh			16:38:10	16:38:13
11-04-2026	refresh			18:08:11	18:13:00
11-04-2026	refresh			19:38:11	19:43:01
11-04-2026	refresh			21:08:11	21:12:56
11-04-2026	refresh			22:38:11	22:42:52
12-04-2026	refresh			00:08:10	00:08:13
12-04-2026	refresh			01:38:11	01:43:00
```

```prolog
11-04-2026    12:08:48    12:08:48       lw10s7U_11th April_2026   17131                     18331                false             AZ-Maildaemon1  equals  LW10S7U,                                                                                                                                                                                                                           
11-04-2026    13:38:26    13:38:26       kondorapp1_11th April-26  17143                     18343                false             AZ-Maildaemon1  equals  KONDORAPP1,          
```

