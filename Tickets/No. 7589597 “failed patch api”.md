---
notion_id: "32043c23-a5e2-8044-9404-c6d0d9337dd9"
notion_last_edited: "2026-04-08T14:04:00.000Z"
tags:
  - "API"
resolved: "False"
problem tags:
  - "api-querry"
Solved by: "Others"
Date: "2026-03-11"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003442204514"
---

**Related back to Tickets:** [[No. 7789789 API updated]]

# Issue:

We want failed patches across all the resources 

# Analysis:

Upon verification, it was observed that in the API /api/1.4/patch/allpatchdetails, the option to retrieve data using only patchstatusfilter has been removed in the recent builds. Currently, the API will return results only when the Patch ID is also included in the request. SFIC.

To achieve the requested requirement (viewing failed patches across all resources), the customer can navigate to:

Threats & Patches → Patches → Detailed View, and create a filter with:

Deployment Status = Failed, which will provide the expected results.

Additionally, we will consider this as a feature request for future enhancements.

# Log traces:



