---
notion_id: "32043c23-a5e2-800e-8797-e8699109257b"
notion_last_edited: "2026-04-30T05:34:00.000Z"
tags:
  - "test and approve"
  - "ui"
resolved: "False"
problem tags:
Date: "2026-03-11"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003433851185"
---

# Issue:



# Analysis:

it was observed that the collection ID present in the HAR file differs from the one shown in the screenshot shared by the customer. Due to this mismatch, it is suspected that the CGID value might have been null, which could have resulted in the reported error.

# Log traces:



