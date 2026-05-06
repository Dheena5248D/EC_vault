---
notion_id: "32843c23-a5e2-8058-aaa8-d530ec930b99"
notion_last_edited: "2026-03-19T11:18:00.000Z"
tags:
  - "APD"
  - "patch-deployment"
resolved: "False"
problem tags:
  - "patch not deployed in apd"
Date: "2026-03-19"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003493752117"
---

# Problem:

43571 patch released on 10th Mar.

Deployment Criteria ----> Deploy patches after 0 days from vendor release

Microsoft Updates ---> Security (Critical, Important, Moderate, Low, Unrated) , Non Security (Critical, Important, Moderate, Low, Unrated) , Service Pack, Rollups, Optional Updates

Deployment window configured ---> All Months --->All Weeks --->Thursday 01:00 to 06:00

All Months ---> All Weeks Wednesday ---> 23:00 to 23:59

patch still showing as missing . based on APD criteria patch should have been detected and installed  last week Thursday



# Analysis:

Since it is before 1 week the logs are rotated but i highly suspect that the patches are approved later so the patch is skipped in previous deployment window.



# Log traces

```javascript
[ 2026-03-16 17:23:43:041 ] [ 6068 ] [INFO] PatchID 43571 found in approved-patches.xml
```



