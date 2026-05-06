---
notion_id: "34243c23-a5e2-8056-a442-dc35f2524fb9"
notion_last_edited: "2026-04-15T07:08:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "Others"
Date: "2026-04-14"
---

**Related back to Tickets:** [[No. 7824912 allpatchdetails api]]

# Issue:

     since patchid is required is there a wildcard that will allow me to get them all? also if I use the page tag page={page}&pagelimit={PageLimit} my query fails. I need to be able to pull patch details for every single patch not just a single one and I need to be able to get multiple pages but I can only get one page currently because adding the page tag causes my script to fault

# Analysis:

Since patchid is a mandatory parameter, there is no wildcard option to fetch all records without specifying it.

Kindly ask the customer to try the API mentioned below:

[https://www.manageengine.com/patch-management/api/system-and-patch-details-patch-management.html](https://www.manageengine.com/patch-management/api/system-and-patch-details-patch-management.html)

For pagination, please ask them to use:

**page=1&pageLimit=30**

If the issue still persists, kindly ask them to share screenshots so we can investigate further.

# Log traces:



