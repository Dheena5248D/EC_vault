---
notion_id: "33c43c23-a5e2-8036-b5cb-f83761a1f66c"
notion_last_edited: "2026-04-08T09:13:00.000Z"
tags:
resolved: "False"
problem tags:
commented time: "2026-04-08T15:00:00.000+05:30"
Solved by: "ME"
Date: "2026-04-08"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003566128714"
---

# Issue:

I am using Tenable SC integration. I noticed vulnerabilities do not dissappear once resolved on the systems as they are tied to scans on the tenable.sc server. I deleted a bunch of old scans from the tenable.sc server and inititaed a "Sync" in endpoint central. The sync has been running for over 3 hours and is still going.

CX wanted to know which log he could refer the see the integration log and error .

# Analysis:

The logs related to 3rd party integration tools like tenable are logged on `ThreatScannerIntegration.log` and `serverout` on the server logs.

if the customer has furthur queries kindly loop us in with the server logs

# Log traces:



