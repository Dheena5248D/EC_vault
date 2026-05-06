---
notion_id: "32d43c23-a5e2-8075-8e56-e1feeb6c0ccb"
notion_last_edited: "2026-03-24T16:09:00.000Z"
tags:
  - "checksum failure"
resolved: "False"
problem tags:
Date: "2026-03-24"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003510656127"
---

# Issue:

Cumulative patch deployment failed with checksum error

# Analysis:

The download is failed due to checksum mismatch the retry attempt is exhausted so the patch no longer downloads in server it is suspected that there is issue from the crawller on so the Cx is asked to modify the apd settings or mannually deploy the patches 

# Log traces:

```prolog
26-03-23	33906	Windows ODD +3d	43586		43586		APD Deploy	12:10:41	12:10:48	SKIPPED	Download Success but checksum failed Error : 60000.
26-03-23	33906	Windows ODD +3d	113059		113059		APD Deploy	12:10:48	12:10:51	SKIPPED	Download Success but checksum failed Error : 60000.
```

