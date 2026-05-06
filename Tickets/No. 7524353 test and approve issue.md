---
notion_id: "34243c23-a5e2-805a-b7f5-f58c41055171"
notion_last_edited: "2026-04-15T05:23:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-14"
---

# Issue:



# Analysis:

1. Why test and approve not processing the patches

- On analysing the server logs the auto approval of the patches are working as expected If the customer still belives the patchs are not auto approving kindly ask the the Cx to verify where the deployed patchs via test and approve is approving

- for example on the pdf the patch 43976 is released on april 8 if the agent is in online the patch should have deployed on april 10 and there is 0 failed systems and it will auto approve in april 15

2. why suspeseded patches are there because he is in cloud and scan is a automated process

-the patches are found missing in the agent when the patch is not missing when the patches are not superseded and the agent didn't scanned so the patch remains missing so the patch is added to the test and approve

for example the patch 354833 is missing on meachines JCE-LT-MXTDM, JCE-LT-WRKEXP1, JCE-LT-WRKEXP2

# Log traces:



