---
notion_id: "33c43c23-a5e2-8030-a037-ec41345b2c50"
notion_last_edited: "2026-04-08T15:20:00.000Z"
tags:
  - "known issue"
resolved: "False"
problem tags:
commented time: "2026-04-08T20:50:00.000+05:30"
Date: "2026-04-08"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003561242999"
---

# Issue:

Patch not get deployed on the machine even if the machine is online and in yet to apply status

# Analysis:

There is a known issue on the customers build where refreshing the console while the deployment is created and a download is in progress.

This issue is fixed on latest builds, kindly suggest server upgrade for the custo

# Log traces:

```sql
build.number=114253501

[15:06:34:233]|[04-06-2026]|[ConfigLogger]|[INFO]|[337]|[863701b7-8e71-4e3c-bd5e-15232909f733]: Configuration has been persisted with :: Collection ID : 1205 collectionName : Patch Deploy Test 06042026_002|

[15:06:37:843]|[04-06-2026]|[CollectionStatusLogger]|[INFO]|[53410]|[df635008-28fd-4202-9778-fa40a1a55c2b]: Starting Refresh for collection: 1205 at: Apr 6, 2026 03:06 PM|

```

