---
notion_id: "33443c23-a5e2-809d-907f-d811a6f51551"
notion_last_edited: "2026-04-01T07:29:00.000Z"
tags:
resolved: "False"
problem tags:
  - "post server-upgrade"
  - "scheduled_reports"
Date: "2026-04-01"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003392741963"
---

# Issue:

The Cx recently migrated to endpoint central from PMP they have scheduled reported on PMP now they don’t have them still they receive emails from scheduled reports

# Analysis:



To analyze this issue further need server logs and the query results of the following command

```sql
  select * from taskdetails
```

# Log traces:



