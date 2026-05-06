---
notion_id: "34343c23-a5e2-8029-b005-c44aee81f9fb"
notion_last_edited: "2026-04-15T07:35:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-15"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003385159088"
---

# Issue:

Test and approve not deploying patches

# Analysis:

- On analysing the server logs the auto approval of the patches are working as expected If the customer still belives the patchs are not auto approving kindly ask the the Cx to verify where the deployed patchs via test and approve is approving

- for example on the pdf the patch 43976 is released on april 8 if the agent is in online the patch should have deployed on april 10 and there is 0 failed systems and it will auto approve in april 15

**2. why suspeseded patches are there because he is in cloud and scan is a automated process**

-the user has enabled superseded patches so the superseded are appearing in the test and approve

# Log traces:

[ 2026-04-13 10:43:57:068 ] [ 4708 ] [INFO] Enable_Superseded value is true

