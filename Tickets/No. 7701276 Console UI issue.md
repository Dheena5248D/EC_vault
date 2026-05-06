---
notion_id: "33343c23-a5e2-80aa-ac95-da14a0da1d6c"
notion_last_edited: "2026-03-31T12:01:00.000Z"
tags:
  - "query-exection"
  - "ui"
resolved: "False"
problem tags:
  - "ui rendering"
  - "pre-deployment script not working"
Date: "2026-03-30"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003517757002"
---

# Issue:

 Can't see the checkboxes in Threats & Patches - Managed systems - By Patches and we have analyzed the ticket and  If a customer customizes the product view while assigned a lower-level role (such as Read) and is later upgraded to a higher-level role (like Full Access or Write), the checkbox may not be visible due to the earlier saved personalization settings. we have provided a xml with query to delete applicableSystemFilterView from the view configuration table but even after the user run the cmd `ExecuteQuery.bat <file-name>.xml` the issue is not resolved



# Analysis:

On noticing the screenshot send by the Cx it is noted that the cmd failed due to not proper xml path is provided. It is suspected that user run cmd without double quotes resulting the query not executing successfully and `Please Enter valid XML Complete Path.If the directory names contain spaces, specify the path within double-quotes.`

Possible cmd run by the Cx:

`ExecuteQuery.bat Personalization removal.XML` 

correct Cmd needs to be executed:

`ExecuteQuery.bat "Personalization removal.XML"`



