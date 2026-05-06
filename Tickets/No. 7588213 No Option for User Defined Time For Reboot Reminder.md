---
notion_id: "32043c23-a5e2-8020-b19a-ec0a2f762e51"
notion_last_edited: "2026-03-22T13:06:00.000Z"
tags:
  - "APD"
  - "post-deployment"
  - "reboot prompt"
resolved: "False"
problem tags:
Date: "2026-03-12"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003440788528"
---

# Problem

The deployment policy is configured to allow users to set a specific reminder time; however, it is not permitting them to do so. The option appears to be limited to a maximum of 8 hours, and there is no option to set a specific time. 


## Analysis:

```javascript
DesktopCentral Agent Version   -> 11.5.2600.23.W 
```

# Solution

> [!info] [https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003393132997](https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003393132997)

According to this ticket the date-time picker in the reboot prompt was implemented using a JavaScript library. Since this library was later identified as vulnerable, it was removed, which resulted in the option to select a specific time being unavailable.





> [!info] But the build in the previous ticket  is  `11.5.2604.01.W` but in the new ticket is `11.5.2600.23.W` Not sure if it removed in this build too



