---
notion_id: "33343c23-a5e2-8007-869c-ff2c00898875"
notion_last_edited: "2026-03-31T11:59:00.000Z"
tags:
  - "db sync"
resolved: "False"
problem tags:
  - "DB_sync_failure"
Date: "2026-03-30"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003520945060"
---

# Issue:

DB Sync failure even though patch.manageengine.com is accessible from the server installed machine



# Analysis:

On analyzing the log the DB sync is failing because it  failed to resolve the domain name into an IP address So it is suspected that there is a DNS issue on customer end.

# Log trace:

```javascript
[14:46:35:558]|[03-26-2026]|[CRSLogger]|[INFO]|[482]|[SERVER-849086ab-8f6b-426e-ab67-1b72a76bd0b8]: XML File download failed for the path : ..\conf\CRSData\PatchDBUpdate\dc-crs\definitiondata\1.11\\linux-vulnerable-patch-scan-details.xml and Download status : 10,008|
[14:46:35:558]|[03-26-2026]|[CRSLogger]|[SEVERE]|[482]|[SERVER-849086ab-8f6b-426e-ab67-1b72a76bd0b8]: Error while downloading files| 
java.lang.Exception: XML file failed to download: ..\conf\CRSData\PatchDBUpdate\dc-crs\definitiondata\1.11\\linux-vulnerable-patch-scan-details.xml, and download status : 10008

[14:46:35:611]|[03-26-2026]|[DownloadManager]|[INFO]|[482]|[SERVER-849086ab-8f6b-426e-ab67-1b72a76bd0b8]: Error occurred while reading & writing : ..\conf\dms\localmeta\db-sync.json : java.net.UnknownHostException: patchdb.manageengine.com|
[14:46:35:611]|[03-26-2026]|[DownloadManager]|[SEVERE]|[482]|[SERVER-849086ab-8f6b-426e-ab67-1b72a76bd0b8]: Exception while downloading :| 
java.net.UnknownHostException: patchdb.manageengine.com
[15:54:48:832]|[03-26-2026]|[DownloadManager]|[INFO]|[504]|[SERVER-9a84db13-c584-4503-abad-ea9e7c37aae1]: *Going to establish connection for :https://patchdb.manageengine.com/uems/dbsync-meta.json|
[15:54:48:832]|[03-26-2026]|[DownloadManager]|[INFO]|[504]|[SERVER-9a84db13-c584-4503-abad-ea9e7c37aae1]: Connection https://patchdb.manageengine.com/uems/dbsync-meta.json , No Proxy|
[15:54:59:901]|[03-26-2026]|[DownloadManager]|[INFO]|[504]|[SERVER-9a84db13-c584-4503-abad-ea9e7c37aae1]: Error occurred while reading & writing : ..\conf\dms\localmeta\db-sync.json : java.net.UnknownHostException: No such host is known (patchdb.manageengine.com)|
[15:54:59:901]|[03-26-2026]|[DownloadManager]|[SEVERE]|[504]|[SERVER-9a84db13-c584-4503-abad-ea9e7c37aae1]: Exception while downloading :| 
java.net.UnknownHostException: No such host is known (patchdb.manageengine.com)
	at java.base/java.net.Inet6AddressImpl.lookupAllHostAddr(Native Method)
	at java.base/java.net.InetAddress$PlatformNameService.lookupAllHostAddr(Unknown Source)
	at java.base/java.net.InetAddress.getAddressesFromNameService(Unknown Source)
	at java.base/java.net.InetAddress$NameServiceAddresses.get(Unknown Source)
	at java.base/java.net.InetAddress.getAllByName0(Unknown Source)
	at java.base/java.net.InetAddress.getAllByName(Unknown Source)
	at java.base/java.net.InetAddress.getAllByName(Unknown Source)
```

