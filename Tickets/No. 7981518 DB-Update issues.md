---
notion_id: "35743c23-a5e2-803b-bcda-f8bce0a8cc8f"
notion_last_edited: "2026-05-05T11:41:00.000Z"
tags:
resolved: "False"
problem tags:
Date: "2026-05-05"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003657306565"
---

# Issue:

Cx states that db sync has ben structed long time. Showing in progress since the weekend.

# Analysis:

The Linux offline metadata sync occurs every 1 hour if there are any new changes in the file. This ensures that the agent is patched with the latest data. As per the logs, the sync is happening every 1 hour on their server.

Additionally, there is a connection timeout issue that is delaying the sync process. The timeout occurs while connecting to the URLs mentioned in the log traces. Kindly ask the customer to ensure that the required URLs are whitelisted and accessible from their network.

# Log traces:

```sql
[10:09:50:265]|[05-04-2026]|[OfflineMetaDownloadLogger]|[INFO]|[472]|[SERVER-24f9cd5b-4c05-422f-a780-3322e5394443]: Unable to download Offline meta : File not found, org.apache.hc.client5.http.HttpHostConnectException: Connect to https://archive.ubuntu.com:443 [archive.ubuntu.com/91.189.92.24, archive.ubuntu.com/185.125.190.83, archive.ubuntu.com/91.189.92.23, archive.ubuntu.com/91.189.91.83, archive.ubuntu.com/91.189.91.81, archive.ubuntu.com/185.125.190.81, archive.ubuntu.com/91.189.91.82, archive.ubuntu.com/185.125.190.82] failed: Connection timed out: connect|


[07:58:08:018]|[05-04-2026]|[OfflineMetaDownloadLogger]|[INFO]|[472]|[SERVER-24f9cd5b-4c05-422f-a780-3322e5394443]: ************************* Download Started for Flavor - ubuntu *************************|
[07:58:08:019]|[05-04-2026]|[OfflineMetaDownloadLogger]|[INFO]|[472]|[SERVER-24f9cd5b-4c05-422f-a780-3322e5394443]: OfflineMetaParams:Parameter added in DB:- param name: ubuntu_STATUS  param value: 220|
[07:58:08:019]|[05-04-2026]|[OfflineMetaDownloadLogger]|[INFO]|[472]|[SERVER-24f9cd5b-4c05-422f-a780-3322e5394443]: OfflineMetaParams:Parameter added in DB:- param name: 

[08:21:05:782]|[05-04-2026]|[OfflineMetaDownloadLogger]|[INFO]|[472]|[SERVER-24f9cd5b-4c05-422f-a780-3322e5394443]: Setting last modified :: ubuntu_dists_plucky-updates_restricted_binary-amd64_Packages.gz :: Mon, 19 Jan 2026 08:30:17 GMT|
[08:21:11:693]|[05-04-2026]|[OfflineMetaDownloadLogger]|[INFO]|[472]|[SERVER-24f9cd5b-4c05-422f-a780-3322e5394443]: https://archive.ubuntu.com/ubuntu/dists/plucky-updates/restricted/binary-amd64/Packages.gz  -  10,010|
```

