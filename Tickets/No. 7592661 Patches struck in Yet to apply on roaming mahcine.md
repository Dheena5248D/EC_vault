---
notion_id: "32443c23-a5e2-80b1-af1b-e361d18e8afb"
notion_last_edited: "2026-03-19T04:44:00.000Z"
tags:
  - "patch-deployment"
  - "roaming devices"
resolved: "False"
problem tags:
  - "collection struck at ready to execute"
Date: "2026-03-16"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003444410876"
---

# Problem:

customer concern: Patches struck in Yet to apply 



# Analysis

The Cx claims that the patch is ready to execute state but on log analyze, the user logged on is not available in custom group target

# Log traces

```javascript
[ 2026-02-24 10:41:48:683 ] [ 7752 ] [INFO] Local Computer Name -> DOM40
[ 2026-02-24 10:41:48:683 ] [ 7752 ] [INFO] Local Computer IP Address -> 192.168.4.97
[ 2026-02-24 10:41:48:683 ] [ 7752 ] [INFO] DC Distribution Server Enabled -> no

```

```javascript
26-03-10	   Refresh	  Système	Automate deployment patch	910	  15:23:35	Configuration_Retried	  15:23:39
```

```javascript
[ 2026-02-24 12:13:51:072 ] [ 12488 ] [INFO] processDeletedCG : File name C:\Program Files (x86)\ManageEngine\UEMS_Agent\data\custom-groups\3017.json
4485
[ 2026-02-24 12:13:51:072 ] [ 12488 ] [INFO] processDeletedCG : DeleteFile is Succeeded: C:\Program Files (x86)\ManageEngine\UEMS_Agent\data\custom-groups\3017.json
4486
[ 2026-02-24 12:13:51:072 ] [ 12488 ] [INFO] updateStaticGroupDetailsInRegistryJSONHandling : Updating static group id's in registry, AddorRemove : 1
4487
[ 2026-02-24 12:13:51:072 ] [ 12488 ] [INFO] updateStaticGroupDetailsInRegistryJSONHandling : Registry key not found.
4488
[ 2026-02-24 12:13:51:072 ] [ 12488 ] [INFO] updateStaticGroupDetailsInRegistryJSONHandling : NO entry is found in staticGroup Registry
4489
[ 2026-02-24 12:13:51:072 ] [ 12488 ] [INFO] updateStaticGroupDetailsInRegistryJSONHandling : Function ends.
4490
[ 2026-02-24 12:13:51:072 ] [ 12488 ] [INFO] FilterByCutomGroupMembers : Included Type -> Loggedon username Système or loggedon computer name DOM40 is not available in the custom group 3017
4491
[ 2026-02-24 12:13:51:072 ] [ 12488 ] [INFO] @@@@@@@@ End Of FilterByCutomGroupMembers Method @@@@@@@@
4492
[ 2026-02-24 12:13:51:072 ] [ 12488 ] [INFO] @@@@@@@@@@@@@@@@@@@@@@@@ End of ProcessNewFilter method @@@@@@@@@@@@@@@@@
4493
[ 2026-02-24 12:13:51:072 ] [ 12488 ] [INFO] @@@@@@@@ End Of ProcessFilter Method @@@@@@@@
4494
[ 2026-02-24 12:13:51:072 ] [ 12488 ] [INFO] Collection Automate deployment patch is not applicable for this target computer or target user.
```

