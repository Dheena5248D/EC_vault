---
notion_id: "32843c23-a5e2-8095-9f55-d9881dfbe555"
notion_last_edited: "2026-03-19T13:31:00.000Z"
tags:
  - "APD"
resolved: "False"
problem tags:
Date: "2026-03-19"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003496698561"
---

# Issue:

CX deployed the APD task on FEB 26 and configured to force install the patch after 3 days in user notification. but CX observed that remarks for some machine where the user skipped the deployment on 18th MARCH.

CX confirm that they didn't approved any patch after the task deployment. also they have configured force deployment then how user skipped after the long time from the task created date.why the force deployment didn't worked and allowed user to skip.

# Analysis:

The Cx cliams they never approved a patch but patch 112861 is already approved and it is found missing on 17/03/2026 so the patch is processed and deployed via apd

# Log traces:

```javascript
Local Computer Name                       -> ALP-4795
DesktopCentral Agent Version              -> 11.5.2600.26.W 
```

```javascript

[ 2026-03-17 22:42:31:088 ] [ 16712 ] [INFO] CheckCollectionDataVersion : CollectionData target Version are not matched ( 1773666293 - 1773752948 ). Hence proceed to apply the collection WS India
[ 2026-03-17 22:42:31:088 ] [ 16712 ] [INFO] CheckCollectionDataVersion : CollectionData Version are matched ( 1773152071 - 1773152071 ). Hence no need to apply the collection WS India . 
```

```javascript
[ 2026-03-17 22:43:22:812 ] [ 16712 ] [INFO] patchId : 112861 
[ 2026-03-17 22:43:22:812 ] [ 16712 ] [INFO] updateType : 1 
[ 2026-03-17 22:43:22:812 ] [ 16712 ] [INFO] severityId : 0 
[ 2026-03-17 22:43:22:812 ] [ 16712 ] [INFO] patchId : 112861 updateType : 1 severityId: 0
[ 2026-03-17 22:43:22:812 ] [ 16712 ] [INFO] Update Type : 1 present in map
[ 2026-03-17 22:43:22:812 ] [ 16712 ] [INFO] isMemberOfList : Item found.Hence 0 is a member of list 
[ 2026-03-17 22:43:22:812 ] [ 16712 ] [INFO] patchId : 112861 passed os_filterType EXCLUDE_FEW 
[ 2026-03-17 22:43:22:812 ] [ 16712 ] [INFO] patchId : 112861 passed os_filterType INCLUDE_FEW 
[ 2026-03-17 22:43:22:835 ] [ 16712 ] [INFO] PatchID 112861 found in approved-patches.xml
[ 2026-03-17 22:43:25:490 ] [ 16712 ] [INFO] SendConfigStatusUpdateEx : Data to Send to Server -> 
 <?xml version="1.0" encoding="UTF-8"?>
<agent-params>
<AgentParams AGENT_PARAM_ID="17" PARAM_NAME="COLL_STATUS" PARAM_VALUE="3" />
<AgentParams AGENT_PARAM_ID="17" PARAM_NAME="COLL_REMARKS" PARAM_VALUE="[i18n]dc.db.agent.config.common.colln_started[/i18n]" />
<AgentParams AGENT_PARAM_ID="17" PARAM_NAME="COLL_REMARKS_EN" PARAM_VALUE="Deployment is in progress." />

[ 2026-03-17 22:43:26:528 ] [ 16712 ] [INFO] ExecuteWithToken : Process successfully created for application "C:\Program Files (x86)\ManageEngine\UEMS_Agent\bin\dcmsghandler.exe" -config 0 config -> 21360

[ 2026-03-17 23:02:58:366 ] [ 16712 ] [INFO] PrePostData : {
   "S-1-5-18" : {
      "20203000000271129" : {
         "20203000192079171" : "User has skipped deployment.\t 17-03-2026 23:02:58",
         "CollectionStartedStatusSent" : 1,
         "ProcessedActionIDs" : "20203000192079171",
         "UserNotificationPerformed" : 1
      }
   }
}
```

```javascript
26-03-17 22:09:45	       APD	1773765584	1773707353

{
	"0" : 
	{
		"AffectedPatchStatus" : 
		{
			"112861" : "202",
			"113091" : "202",
			"43718" : "201"
		},

```

