---
notion_id: "34a43c23-a5e2-8070-bc65-cd284c298676"
notion_last_edited: "2026-04-22T12:54:00.000Z"
tags:
  - "ui"
  - "known issue"
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-22"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003601788981"
---

**similar Tickets:** [[No. 7667636 domain block prompt in the server console]]

# Issue:

The customer got the message "Unable to access specific domains" in Patch Manager Plus, which stays visible, but when the customer clicks on it, they see no domains.

# Analysis:

Analysis:

There is a known issue in the customer build where a false positive alert has shown to the customer when no domains are listed as failed; the issue does not indicate an actual connectivity problem.

The alerts will be cleared once a day during patch cleanup. The known case is where the alert is not cleared during patch cleanup.

The issue has been fixed in 2605.13 and above. Kindly ask the customer to upgrade to the latest version.

[https://www.manageengine.com/patch-management/service-packs.html](https://www.manageengine.com/patch-management/service-packs.html)



//Internal

The feature to clear the alert on demand is in development and will be released in the master

# Log traces:



`build.number=115260509`

