---
notion_id: "33743c23-a5e2-8094-b840-fce15b426b0a"
notion_last_edited: "2026-04-05T07:30:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "Others"
Date: "2026-04-03"
ticket_url: "#7732805"
---

# Issue:



# Analysis:

The target is not applicable in the system the logs are rotated so we don’t know the reason for the target being not applicable

# Log traces:

```sql
 Local Computer Name                       -> HGSVR3 
 Local Computer IP Address                 -> 192.168.134.207 
 Local Computer Domain controller          -> HGSVR3 
 DC Distribution Server  Name      			-> HGSVR2 
 DC Distribution Server  IPAddress 			-> 192.168.134.206 
```

```sql
 26-03-26	   Refresh	    SYSTEM	Microsoft Updates - Wednesdays	2201000000245761	  11:54:32	Target_Not_Applicable	  11:54:32 
 26-03-27	   Refresh	    SYSTEM	Microsoft Updates - Wednesdays	2201000000245761	  11:54:24	Target_Not_Applicable	  11:54:24
 26-03-27	   Refresh	    SYSTEM	Microsoft Updates - Wednesdays	2201000000245761	  19:24:31	Target_Not_Applicable	  19:24:31
 26-03-28	   Refresh	    SYSTEM	Microsoft Updates - Wednesdays	2201000000245761	  02:54:40	Target_Not_Applicable	  02:54:40
```

