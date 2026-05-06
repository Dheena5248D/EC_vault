---
notion_id: "33c43c23-a5e2-8062-9cac-e5bce38ba64c"
notion_last_edited: "2026-04-08T14:03:00.000Z"
tags:
  - "API"
resolved: "False"
problem tags:
commented time: "2026-04-08T19:33:00.000+05:30"
Solved by: "ME"
Date: "2026-04-08"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003567661680"
---

**similar Tickets:** [[No. 7589597 “failed patch api”]]

# Issue:

Cx is receiving no data when using the API api/1.4/allpatchdetails. It was working previously, but it is not working now.

# Analysis:

The API api/1.4/allpatchdetails has been updated, and the patchid parameter is now mandatory. As a result, requests made without the patchid parameter will fail and return no data.

If the customer is trying to generate a report using the API, this can be achieved from:**Threats & Patches → Patches → Detailed View**, by leveraging the available filters and column chooser and export it as a report.

If the customer still requires the API, kindly ask for their business use case so that we can analyze further.

# Log traces:



