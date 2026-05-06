---
notion_id: "32843c23-a5e2-800c-90bf-dd420d356445"
notion_last_edited: "2026-03-24T16:13:00.000Z"
tags:
  - "upload patch"
resolved: "False"
problem tags:
Date: "2026-03-19"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003424997286"
---

# issue:

Cx is trying to upload a iso for manual upload patch required patch but it results in network error


# Analysis:

A similar ticket [[No. 7521412 unable to upload patch - network error]] 



There is a known issue in the build 15260019 where uploading patches higher than 3gb



The workaround for that is access the server using port 8443, while uploading such patches 

