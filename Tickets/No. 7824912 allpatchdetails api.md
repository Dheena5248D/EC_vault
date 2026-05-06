---
notion_id: "34343c23-a5e2-800b-990d-dba73f838c9d"
notion_last_edited: "2026-04-15T07:35:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-15"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003585261820"
---

**similar Tickets:** [[No. 7801614 API error returning. null data]]

# Issue:

/patch/allpatchdetails api is failing where it is working fine previously

# Analysis:

The API api/1.4/allpatchdetails has been updated, and the patchid parameter is now mandatory. As a result, requests made without the patchid parameter will fail and return no data.

Since the patch id is now manditory now the api request is failing

Kindly ask the customer to try the API mentioned below:

[https://www.manageengine.com/patch-management/api/system-and-patch-details-patch-management.html](https://www.manageengine.com/patch-management/api/system-and-patch-details-patch-management.html)

# Log traces:



