---
notion_id: "32143c23-a5e2-80d9-a28e-f7db05aec3bc"
notion_last_edited: "2026-04-22T12:42:00.000Z"
tags:
  - "db sync"
  - "linux"
  - "offline meta"
resolved: "False"
problem tags:
Solved by: "Others"
Date: "2026-03-12"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003450106096"
---

# Problem:

The usual dbsync successes but it fails while syncing offline meta of linux



# Analysis:

From the provided logs we could see that the **Ubuntu offline meta file** failed to download.

This indicates that the **connection was reset during the download process**, which usually happens due to **network instability, firewall interruption, proxy interference, or connectivity issues between the server and the Ubuntu repository**.

Kindly ask the cx to verify the **network connectivity from the server to the Ubuntu repository**, and also ensure that the required domains are **whitelisted in the firewall/proxy**. Once the connectivity issue is resolved, ask the cx to **retry the patch database sync again**.

# Log analysis:

```javascript
[01:15:14:132]|[03-09-2026]|[OfflineMetaDownloadLogger]|[INFO]|[509]|[SERVER-7712af68-67aa-4c83-98a8-63d87523d013]: GPG Meta verification not required for the flavor: ubuntu|
[01:20:53:860]|[03-09-2026]|[OfflineMetaDownloadLogger]|[INFO]|[509]|[SERVER-7712af68-67aa-4c83-98a8-63d87523d013]: https://archive.ubuntu.com/ubuntu/dists/jammy/multiverse/binary-i386/Packages.gz  -  10008|
[01:20:53:860]|[03-09-2026]|[OfflineMetaDownloadLogger]|[INFO]|[509]|[SERVER-7712af68-67aa-4c83-98a8-63d87523d013]: ..\webapps\DesktopCentral\client-data\patch-resources\linux\ubuntu\offline-meta\renamed_ubuntu_dists_jammy_multiverse_binary-i386_Packages.gz has been renamed to  : ..\webapps\DesktopCentral\client-data\patch-resources\linux\ubuntu\offline-meta\ubuntu_dists_jammy_multiverse_binary-i386_Packages.gz|
[01:20:53:882]|[03-09-2026]|[OfflineMetaDownloadLogger]|[INFO]|[509]|[SERVER-7712af68-67aa-4c83-98a8-63d87523d013]: ubuntu_dists_jammy_multiverse_binary-i386_Packages.gz is failed to Downloaded SocketTimeoutException/Premature EOF encountered|
[01:20:53:882]|[03-09-2026]|[OfflineMetaDownloadLogger]|[INFO]|[509]|[SERVER-7712af68-67aa-4c83-98a8-63d87523d013]: DOWNLOAD STATUS OF META : ubuntu_dists_jammy_multiverse_binary-i386_Packages.gz = DLOAD_FAILED|

[15:25:15:361]|[03-11-2026]|[OfflineMetaDownloadLogger]|[INFO]|[507]|[SERVER-8dbf2697-9895-4eec-8f6d-2b94ac3050c3]: ubuntu_dists_xenial-security_universe_binary-i386_Packages.gz is failed to Downloaded SocketTimeoutException/Premature EOF encountered|
```

```prolog
11:08:35:252]|[03-12-2026]|[OfflineMetaDownloadLogger]|[INFO]|[236]|[SERVER-eabf56ee-47d0-447a-9817-1addce8a1f5d]: DOWNLOAD STATUS OF META : ubuntu_dists_plucky-updates_universe_binary-amd64_Packages.gz = DLOAD_FAILED|
[

[11:07:33:590]|[03-12-2026]|[DownloadManager]|[INFO]|[1248]|[SERVER-9561570a-fe0b-4ade-a742-70def939b65d]: DomainValidator task :  Max value stored in DomainExceptionList table 1678097463000|
[11:08:35:237]|[03-12-2026]|[DownloadManager]|[INFO]|[236]|[SERVER-eabf56ee-47d0-447a-9817-1addce8a1f5d]: Error occurred while reading & writing : ..\webapps\DesktopCentral\client-data\patch-resources\linux\ubuntu\offline-meta\ubuntu_dists_plucky-updates_universe_binary-amd64_Packages.gz : java.net.SocketException: Connection reset|
[11:08:35:237]|[03-12-2026]|[DownloadManager]|[SEVERE]|[236]|[SERVER-eabf56ee-47d0-447a-9817-1addce8a1f5d]: Exception while downloading :| 
java.net.SocketException: Connection reset
	at java.base/java.net.SocketInputStream.read(SocketInputStream.java:186)
	at java.base/java.net.SocketInputStream.read(SocketInputStream.java:140)
	at java.base/sun.security.ssl.SSLSocketInputRecord.read(SSLSocketInputRecord.java:484)
	at java.base/sun.security.ssl.SSLSocketInputRecord.readHeader(SSLSocketInputRecord.java:478)
	at java.base/sun.security.ssl.SSLSocketInputRecord.bytesInCompletePacket(SSLSocketInputRecord.java:70)
	at java.base/sun.security.ssl.SSLSocketImpl.readApplicationRecord(SSLSocketImpl.java:1459)
	at java.base/sun.security.ssl.SSLSocketImpl$AppInputStream.read(SSLSocketImpl.java:1070)
	at org.apache.hc.core5.http.impl.io.SessionInputBufferImpl.fillBuffer(SessionInputBufferImpl.java:149)
	at org.apache.hc.core5.http.impl.io.SessionInputBufferImpl.readLine(SessionInputBufferImpl.java:280)
	at org.apache.hc.core5.http.impl.io.AbstractMessageParser.parse(AbstractMessageParser.java:247)
	at org.apache.hc.core5.http.impl.io.AbstractMessageParser.parse(AbstractMessageParser.java:54)
```

