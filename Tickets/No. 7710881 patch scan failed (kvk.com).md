---
notion_id: "33a43c23-a5e2-80e7-ba3e-d320226a6e62"
notion_last_edited: "2026-04-06T15:15:00.000Z"
tags:
  - "distribution server"
  - "checksum failure"
resolved: "False"
Difficulty: "3"
problem tags:
commented time: "2026-04-06T20:44:00.000+05:30"
Solved by: "ME"
Date: "2026-04-06"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003525319616"
---

# Issue:

Patch Scan failed with the error Downloading Server DetectionChecks.dll.gz failed with error code: 404 

# Analysis:

On analysing the logs the ServerDetectionChecks.dll.gz is successfully downloaded in the distribution server but due to checksum mismatch the file is deleted and marked as replication failure this is the reason for 404 error code when the agent tries to download the ServerDetectionChecks.dll.gz from distribution server.

To analyse furthure why the replication fails in the distribution server need the followings:

1. Server logs

2. client-data

# Log traces:

```sql
DesktopCentral Server Secondary IPAddress -> mec.kvk.com
DesktopCentral Server IPAddress           -> 172.16.0.222 
Local Computer Name                       -> adnsrv 
Local Computer IP Address                 -> 172.17.128.10 
****************************************************************** 
DC Distribution Server  Name      			-> ADNSRV 
DC Distribution Server  IPAddress 			-> 172.17.128.10
```



```sql
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by client-data/vulnerable-resources/ServerDetectionChecks.dll.gz 
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [ERROR] AgentSendRequest : gv_dcDSServerSecIPAddress is NULL.Hence not copied to dcServerSecIPAddressW.
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [INFO] AgentSendRequest: EnablePocoCommunication is [0] 
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [ERROR] isJsonorXmlRequest : gv_dcDynamicDownloadServer is NULL. Hence not copied to dynamicDownloadServer.
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [INFO] InternetGetDownloader : DesktopCentral Server & Port -> 172.17.128.10 : 8384 
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [INFO] InternetGetDownloader : Download Mode 1
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [INFO] httpRequestObjOld.m_externalVendorServer = 0 
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [ERROR] Initialize: proxyServerName is NULL.Hence not copied to m_proxyServerName.
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [ERROR] Initialize: proxyExceptionAddr is NULL.Hence not copied to m_proxyExceptionAddr.
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [ERROR] Initialize: proxyUserName is NULL.Hence not copied to m_proxyUserName.
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [ERROR] Initialize: proxyPassword is NULL.Hence not copied to m_proxyPassword.
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [INFO] Inside PreCheckForRangeRequest
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [INFO] GetInternetRequestHandle : Send request with NO proxy 
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [INFO] GetInternetRequestHandle :  HEAD Request 
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [INFO] Inside SetAuthentication DS
[ 2026-03-25 23:16:08:214 ] [ 38808 ] [INFO] SetAuthenticationToDS : DS Authentication is disabled
[ 2026-03-25 23:16:08:230 ] [ 38808 ] [INFO] SetAuthentication: Authenticated successfully 
[ 2026-03-25 23:16:08:230 ] [ 38808 ] [INFO] Get request not to reporting server
[ 2026-03-25 23:16:08:230 ] [ 38808 ] [INFO] GetSecFlags: Ignoring Certificate check flags added for communication 
[ 2026-03-25 23:16:08:261 ] [ 38808 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2026-03-25 23:16:08:261 ] [ 38808 ] [INFO] GetInternetRequestHandle: Client Certificate set successfullly 
[ 2026-03-25 23:16:08:261 ] [ 38808 ] [ERROR] GetInternetRequestHandle :  WINHTTP_DISABLE_REDIRECTS --> success 
[ 2026-03-25 23:16:08:292 ] [ 38808 ] [INFO] writeValue : Valuename or Valuedata or Subkey is NULL
[ 2026-03-25 23:16:08:292 ] [ 38808 ] [INFO] GetInternetRequestHandle : WinHttpQueryHeaders http status code 404 
[ 2026-03-25 23:16:08:323 ] [ 38808 ] [INFO] DeletePrivateKeys: Deleted using 8c20d42166d445bc3c56f1e91bba4e3b2c7721f1d306fdf361729fc5c0ab167e1f35716e27e56fd423efe740dfb3e8fa KeyContainer from Microsoft Software Key Storage Provider
[ 2026-03-25 23:16:08:323 ] [ 38808 ] [ERROR] PreDownloadHandling : Failed with the http status code, 404 
[ 2026-03-25 23:16:08:323 ] [ 38808 ] [INFO] Proceeding for PostDownloadHandling 
[ 2026-03-25 23:16:08:323 ] [ 38808 ] [ERROR] @@@@@@@@ End Of ResumeGetRequestEx Method @@@@@@@@ 
[ 2026-03-25 23:16:08:323 ] [ 38808 ] [INFO] InternetGetDownloader : ResumeGetRequestEx errorCode = 404 
[ 2026-03-25 23:16:08:323 ] [ 38808 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-03-25 23:16:08:323 ] [ 38808 ] [ERROR] deleteValue:  Delete value downloadInProgress failure! 
[ 2026-03-25 23:16:08:323 ] [ 38808 ] [ERROR]  Error Message: Cannot create a file when that file already exists.


[ 2026-03-25 23:16:08:323 ] [ 38808 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-25 23:16:08:323 ] [ 38808 ] [ERROR] downloadXMLGZ : Download failure  filetoDownload : client-data/vulnerable-resources/ServerDetectionChecks.dll.gz
[ 2026-03-25 23:16:08:323 ] [ 38808 ] [INFO] downloadXMLGZ : extractXML is returning with status: 404
[ 2026-03-25 23:16:08:323 ] [ 38808 ] [ERROR] ProcessPatchResourceXML : Failed to download ServerDetectionChecks.dll.gz
```



```sql
[ 2026-03-27 12:04:30:420 ] [ 14304 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by client-data/vulnerable-resources/ServerDetectionChecks.dll.gz 
[ 2026-03-27 12:04:30:420 ] [ 14304 ] [INFO] AgentSendRequest: EnablePocoCommunication is [0] 
[ 2026-03-27 12:04:30:420 ] [ 14304 ] [ERROR] isJsonorXmlRequest : gv_dcDynamicDownloadServer is NULL. Hence not copied to dynamicDownloadServer.
[ 2026-03-27 12:04:30:420 ] [ 14304 ] [INFO] InternetGetDownloader : DesktopCentral Server & Port -> mec.kvk.com : 8383 
[ 2026-03-27 12:04:30:420 ] [ 14304 ] [INFO] InternetGetDownloader : Download Mode 1
[ 2026-03-27 11:31:53:071 ] [ 52168 ] [INFO] PostDownloadHandling : Successfully downloaded the file client-data/vulnerable-resources/ServerDetectionChecks.dll.gz?dsBranchIdentifier=2102&isDS=true&ResourceID=9681 from the server mec.kvk.com to the destination file C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\client-data\vulnerable-resources\ServerDetectionChecks.dll.gz
[ 2026-03-27 11:31:53:087 ] [ 52168 ] [INFO] ReplicateXML: client-data/vulnerable-resources/ServerDetectionChecks.dll.gz downloaded
[ 2026-03-27 14:54:46:561 ] [ 18004 ] [INFO] ValidateAndGetFileChecksum : Checksum value to compare : 4d5df084ba2b0631a303ae83da57d35d4453a952267f2f21b2d16101f3373664
[ 2026-03-27 14:54:46:561 ] [ 18004 ] [INFO] ValidateAndGetFileChecksum : Checksum value from file : 88e5b39882781a7abeb4bbc513bfea95b188802a91b787c34f6afa372736a606
[ 2026-03-27 14:54:46:561 ] [ 18004 ] [ERROR] ProcessGlobalMetadata : ServerDetectionChecks.dll.gz downloaded successfully. But checksum mismatch. So removing file. Marking replication process as failure to retry in next replication cycle.
```

