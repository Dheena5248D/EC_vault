---
notion_id: "33e43c23-a5e2-8012-baf4-ecb4853d410b"
notion_last_edited: "2026-04-10T13:21:00.000Z"
tags:
  - "ui"
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-10"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003574106025"
---

# Issue:

Patch ID is not showing in installed patches view

# Analysis:

The installed patches view only shows the patchs that are not missing in any systems.

while analyzing har log and screenshot the patch is missing in 14 systems so the patch is not displayed in the installed patch view

That is the reason why the count of Installed and Missing patches aligns with the Applicable Patches view if we show a patch in both missing and installed view the sum of the missing patch count and installed patch count should be greater than the applicable patch count.

if the customer wants to know the count of the installed systems for a particular patch kindly ask them to use applicable patch view and detailed patch view shows the more detailed info of the patches installed in each system

# Log traces:



