---
notion_id: "33a43c23-a5e2-80eb-9a81-d5f9ed7f2909"
notion_last_edited: "2026-04-06T15:16:00.000Z"
tags:
resolved: "False"
problem tags:
commented time: "2026-04-06T17:22:00.000+05:30"
Solved by: "ME"
Date: "2026-04-06"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003543222793"
---

**similar Tickets:** [[No. 7574443 decline patches]]

# Issue:

Declined Patches are still being listed as Missing in the console

# Analysis:

There is a known issue on the Cx build where the valid dynamic cg criteria fails so the agent sent the status as the patch missing resulting in the declined patch is in missing status.

The issue has fixed in latest builds, kindly suggest upgrade
[https://www.manageengine.com/products/desktop-central/service-packs.html](https://www.manageengine.com/products/desktop-central/service-packs.html)

# Log traces:

```sql
Local Computer Name                       -> AZINVMPHLW-14
Local Computer Domain controller          -> AZLINSDCPUN01 
DesktopCentral Agent Version              -> 11.5.2600.16.W 
The remote office name is                 -> FCIPL-YUGMA-AVD 
DesktopCentral Server Data Path           -> client-data/1/domains/fujitsuconsulti 
DC Distribution Server Enabled            -> yes 
Remote Office ID                          -> 2701 
```

```sql
<AffectedPatchStatus RESOURCE_ID="39984" PATCH_ID="357355" STATUS="Missing" STATUS_ID="202" UPDATED_TIME="0" REMARKS="" />
<AffectedProduct PATCHID="357355" PRODUCTID="102582" FIXEDINSP="0" />
```

```sql
[ 2026-04-02 05:11:38:137 ] [ 10708 ] [INFO] ChkForPatchAvailEx: 357355 is missing
[ 2026-04-02 05:11:38:137 ] [ 10708 ] [INFO] CheckForPatchAvailableEx ret val: 122
[ 2026-04-02 05:11:38:137 ] [ 10708 ] [INFO] End of the function checkforpatchapplicableex
[ 2026-04-02 05:11:38:137 ] [ 10708 ] [ERROR] processMandatoryChecks: checks pointer retruns null
[ 2026-04-02 05:11:38:137 ] [ 10708 ] [INFO] CheckForPatchApplicableEx ret val: 122
[ 2026-04-02 05:11:38:137 ] [ 10708 ] [INFO] ProcessPatchScanEx: Return Val for patchid 357355:122,remarks: 
[ 2026-04-02 05:11:38:137 ] [ 10708 ] [INFO] AddAffPatchStatusRow: added row patch 357355 to AffPatchStatus
[ 2026-04-02 05:11:38:137 ] [ 10708 ] [INFO] AddAffectedProductsRow : Successfully added the params row(patchid: 357355 , productid Id: 102582) to AffectedProduct Table


[ 2026-04-02 05:11:38:908 ] [ 10708 ] [INFO] ResourceToMSSoftware : pid:spid
[ 2026-04-02 05:11:38:908 ] [ 10708 ] [INFO] 102196:102304 , 102221:102329 , 102558:102668 , 102582:102692 , 1148:2169 , 1510:2619 , 1596:2707 , 1652:2964 , 1743:2861 , 1770:3252 , 1773:2902 , 1791:2902 , 1814:2952 , 1845:2999 , 1846:3000 , 1922:3095 , 1955:3139 , 1977:3162 , 2058:3252 , 2073:3270 , 81:2171 , 
[ 2026-04-02 05:11:38:908 ] [ 10708 ] [INFO] AffectedPatchStatus : patchid:status 
[ 2026-04-02 05:11:38:908 ] [ 10708 ] [INFO] 112729:201 , 112861:201 , 112862:201 , 113022:201 , 113124:201 , 336505:202 , 357355:202 , 42626:201 , 43229:201 , 43405:201 , 43411:201 , 43586:201 , 43662:201 , 43754:201 , 
[ 2026-04-02 05:11:38:908 ] [ 10708 ] [INFO] DeclinedAffPatchStatus : patchid:status 
[ 2026-04-02 05:11:38:908 ] [ 10708 ] [INFO] 113009:202 , 113145:202 , 
```

```sql
26-03-26 06:26:07	    Manual	1774506366	1774417587

{
	"0" : 
	{
		"AffectedPatchStatus" : 
		{
			"113113" : "202",
			"113115" : "201",
			"357355" : "202"
		}
	},
```

```sql
[ 2026-04-06 04:44:26:706 ] [ 5676 ] [INFO] getApplicableDeclinedDynamicGroups : There are no applicable declined dynamic groups 
```

```sql
[14:22:28:896]|[04-02-2026]|[CustomGroupLogger]|[INFO]|[494403]|[75a66b8c-6497-4b0f-94b9-00519859dfa2]: Create Custom group details: {membershipType=1, groupName=DeclinePatch-FCIPL-Yugma-AVD-VPN-All Versions-Software-FG-REQ0441915, groupType=1, groupCategory=2, criteriaList=[{comparator=equal, logicalOperator=OR, columnId=17, criteriaValue=[FUJITSUCONSULTI]}, {comparator=equal, logicalOperator=OR, columnId=21, criteriaValue=[FCIPL-YUGMA-AVD]}], criteriaPattern=( ( 1 ) OR 2 ), loginId=2702, userId=2702, loginName=khondumu}|

[14:22:29:009]|[04-02-2026]|[CustomGroupLogger]|[INFO]|[494403]|[75a66b8c-6497-4b0f-94b9-00519859dfa2]: Added/updated common data for CG ID: 42,668|

```

```sql
[ 2026-04-06 04:44:26:706 ] [ 5676 ] [INFO] Inside  FilterByCriteriaGroupMembersNew Method
[ 2026-04-06 04:44:26:706 ] [ 5676 ] [INFO] ProcessFilter : The configuration is for FUJITSUCONSULTI  and the filter id is 1 . 
[ 2026-04-06 04:44:26:706 ] [ 5676 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-06 04:44:26:706 ] [ 5676 ] [INFO] GetValueAndCompare : Compare Value   -> FUJITSUCONSULTI 
[ 2026-04-06 04:44:26:706 ] [ 5676 ] [INFO] GetValueAndCompare : Retrieved Server Value -> FUJITSUCONSULTI. Chassis value -> (null) 
[ 2026-04-06 04:44:26:706 ] [ 5676 ] [INFO] ProcessFilter : The configuration is for FCIPL-YUGMA-AVD  and the filter id is 35 . 
[ 2026-04-06 04:44:26:706 ] [ 5676 ] [ERROR] ChangeAnsiToUTF8Str: ansiString is empty! 
[ 2026-04-06 04:44:26:706 ] [ 5676 ] [INFO] GetValueAndCompare : Compare Value   -> FCIPL-YUGMA-AVD 
[ 2026-04-06 04:44:26:706 ] [ 5676 ] [INFO] GetValueAndCompare : Retrieved Server Value -> FCIPL-YUGMA-AVD. Chassis value -> (null) 
[ 2026-04-06 04:44:26:706 ] [ 5676 ] [INFO] FilterByCriteriaGroupMembers : Included Type -> Loggedon username (null) or loggedon computer name AZINVMPHLW-6 is not available in the custom group 42668
```



