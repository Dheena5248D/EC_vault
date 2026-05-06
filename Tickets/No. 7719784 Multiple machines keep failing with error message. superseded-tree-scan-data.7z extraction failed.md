---
notion_id: "33443c23-a5e2-80f9-8cdb-d9e7f424d32b"
notion_last_edited: "2026-03-31T12:54:00.000Z"
tags:
  - "distribution server"
  - "patch-scan"
  - "checksum failure"
resolved: "False"
problem tags:
  - "checksum mismatch"
  - "patch scan failure"
Date: "2026-03-31"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003533477398"
---

# Issue:

**Multiple machines keep failing with error message. superseded-tree-scan-data.7z extraction failed**



# Analysis:

The `superseded-tree-scan-data.7z` was replicated in 29/03/2026 the agent downloaded the file from ds on 30/03/2026 but the checksum from the file is different than the file on the DS

The patch scan data xml file is downloaded successfully from the patchdb and stored in the TempXMLRepository but it fails in moving the file to `\UEMS_DistributionServer\Replication\` 

So old patch scan data xml file is send to the agent which results in agent comparing new files checksum with old checksum the Cx needs to manually check if they can move the file to the location without issues.

# Log traces:

```javascript
[ 2026-03-30 11:11:27:831 ] [ 6240 ] [INFO] PostDownloadHandling : Successfully downloaded the file client-data/patch-resources/superseded-tree-scan-data.7z?agentResourceIdentifier=88173000015042273&ResourceID=88173000015042273&uniqueValue=J11Y8H4 from the server 10.190.2.243 to the destination file C:\Program Files (x86)\ManageEngine\UEMS_Agent\\client-data\patch-resources\superseded-tree-scan-data.7z 
[ 2026-03-30 11:11:27:831 ] [ 6240 ] [ERROR] ResumeGetRequestEx : gv_dcConfigPolicy is NULL.
[ 2026-03-30 11:11:27:831 ] [ 6240 ] [INFO] Successfully updated ecdatatransfer_access.log
[ 2026-03-30 11:11:27:831 ] [ 6240 ] [INFO] InternetGetDownloader : ResumeGetRequestEx errorCode = 0 
[ 2026-03-30 11:11:27:831 ] [ 6240 ] [ERROR] deleteValue:  Software\AdventNet\DesktopCentral\DCAgent\FileMetaData\1774883487122366240.download Key not found!: 2  
[ 2026-03-30 11:11:27:831 ] [ 6240 ] [ERROR]  Error Message: Cannot create a file when that file already exists.


[ 2026-03-30 11:11:27:831 ] [ 6240 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-30 11:11:27:831 ] [ 6240 ] [INFO] AgentSendRequest : Last Access Address is 10.190.2.243 
[ 2026-03-30 11:11:27:831 ] [ 6240 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-30 11:11:27:831 ] [ 6240 ] [INFO] AgentSendRequest : Updating key inside main send request
[ 2026-03-30 11:11:27:831 ] [ 6240 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-30 11:11:27:857 ] [ 6240 ] [INFO] ValidateAndGetFileChecksum : Checksum value to compare : 83850ef6e6f75e3ea28e3b8c4205033cc07c7b08b9d6a5f8a60b95cf5893a817
[ 2026-03-30 11:11:27:857 ] [ 6240 ] [INFO] ValidateAndGetFileChecksum : Checksum value from file : c111cc35261e35921ae181a857308778e9add53323a924250980fe1f5c8c7b05
[ 2026-03-30 11:11:27:857 ] [ 6240 ] [ERROR] loadPatchXmlGZs : superseded-tree-scan-data.7z downloaded successfully. But checksum mismatch.
[ 2026-03-30 11:11:29:578 ] [ 6240 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by /patchscan?actionToCall=error&computerName=PBFSPWEXECWHM2&domainName=BENEDOMAIN&domainType=2&scanMode=1&scanType=TrayIcon&remarks=[i18n]dc.patch.configremarks.xml.extractfailure@@@superseded-tree-scan-data.7z[/i18n]&errorCode=5107 
```

```javascript
26/03/30:09:19:29,dcconfig.exe,9712,Refresh,GET,10.190.2.243,8384,88173000015042273,client-data/patch-resources/patch-scan-data.xml.gz?agentResourceIdentifier=88173000015042273&ResourceID=88173000015042273&uniqueValue=J11Y8H4,220777,220777,0.000,0,C:\Program Files (x86)\ManageEngine\UEMS_Agent\\client-data\patch-resources\patch-scan-data.xml.gz
26/03/30:11:11:27,dcpatchscan.exe,6240,-,GET,10.190.2.243,8384,88173000015042273,client-data/patch-resources/superseded-tree-scan-data.7z?agentResourceIdentifier=88173000015042273&ResourceID=88173000015042273&uniqueValue=J11Y8H4,319543,319543,0.000,0,C:\Program Files (x86)\ManageEngine\UEMS_Agent\\client-data\patch-resources\superseded-tree-scan-data.7z
```

## DS:

```javascript
[ 2026-03-29 11:20:27:926 ] [ 31940 ] [INFO] InsertResumeDownloadFileSizeParams: Adding urlToDownload: /dc-crs/definitiondata/1.11/patchscan/1.270/superseded-tree-scan-data.7z 	 filesize: 320938 
[ 2026-03-29 11:20:27:926 ] [ 31940 ] [INFO] isdownloadServerRequest 0
[ 2026-03-29 11:20:27:926 ] [ 31940 ] [INFO] Inside DownloadResumeHandler::Initialize
[ 2026-03-29 11:20:27:926 ] [ 31940 ] [INFO] Download folder = DownloadRepository\	periodic save limit = 1048576
[ 2026-03-29 11:20:27:926 ] [ 31940 ] [INFO] GetTimeInSeconds : Time in Second : 1774797627
[ 2026-03-29 11:20:27:926 ] [ 31940 ] [INFO] Formed Unique id for the file is 17747976273835231940.download
[ 2026-03-29 11:20:27:928 ] [ 31940 ] [INFO] Temporary file path is C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\DownloadRepository\
[ 2026-03-29 11:20:27:928 ] [ 31940 ] [INFO] ResumeGetRequestEx : To update download count
[ 2026-03-29 11:20:27:928 ] [ 31940 ] [INFO] End of DownloadResumeHandler::Initialize
[ 2026-03-29 11:20:27:928 ] [ 31940 ] [ERROR] ResumeGetRequestEx: Content-Range Header message: Range: bytes=0-320937
[ 2026-03-29 11:20:27:928 ] [ 31940 ] [INFO] Header message: Range: bytes=0-320937 
[ 2026-03-29 11:20:27:928 ] [ 31940 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2026-03-29 11:20:27:928 ] [ 31940 ] [INFO] GetInternetRequestHandle : Send request with NO proxy 
[ 2026-03-29 11:20:27:928 ] [ 31940 ] [INFO] GetInternetRequestHandle :  GET Request 
[ 2026-03-29 11:20:27:928 ] [ 31940 ] [INFO] ExternalDownloadEnabled so skipping Auth Token
[ 2026-03-29 11:20:27:928 ] [ 31940 ] [INFO] Get request not to reporting server
[ 2026-03-29 11:20:27:928 ] [ 31940 ] [INFO] master agent and dccloud defined, so validating certificate
[ 2026-03-29 11:20:28:029 ] [ 31940 ] [INFO] GetInternetRequestHandle : WinHttpQueryHeaders http status code 206 
[ 2026-03-29 11:20:28:029 ] [ 31940 ] [INFO] ResumeGetRequestEx: GetInternetRequestHandle function return code: 0
[ 2026-03-29 11:20:28:151 ] [ 31940 ] [INFO] ResumeGetRequestEx : Bytes read reached the contenlength
[ 2026-03-29 11:20:28:151 ] [ 31940 ] [INFO] ResumeGetRequestEx : Total Time Taken for download : 0.122 seconds
[ 2026-03-29 11:20:28:151 ] [ 31940 ] [INFO] ResumeGetRequestEx: Total bytes read = 320938
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [INFO] updated registry entries size  320938 and last modified time Sun, 29 Mar 2026 07:51:34 GMT retry time 0
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [INFO] Proceeding for PostDownloadHandling 
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [INFO] Inside SaveToDestFile from C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\DownloadRepository\17747976273835231940.download to C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\TempXMLRepository\client-data\patch-resources\superseded-tree-scan-data.7z
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [INFO] CreateFolder : The Directory to create is C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\TempXMLRepository\client-data\patch-resources\ 
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [INFO] Inside CleanFileAndRegistry
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [INFO] deleteValue:  Delete value / success! 
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [ERROR] deleteValue:  Delete value / failure! 
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [ERROR]  Error Message: The operation completed successfully.


[ 2026-03-29 11:20:28:167 ] [ 31940 ] [INFO] PostDownloadHandling : Successfully downloaded the file /dc-crs/definitiondata/1.11/patchscan/1.270/superseded-tree-scan-data.7z from the server patchdb.manageengine.com to the destination file C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\TempXMLRepository\client-data\patch-resources\superseded-tree-scan-data.7z 
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [ERROR] ResumeGetRequestEx : gv_dcConfigPolicy is NULL.
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [INFO] InternetGetDownloader : ResumeGetRequestEx errorCode = 0 
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [ERROR] deleteValue:  Software\AdventNet\DesktopCentral\DCDistributionServer\FileMetaData\17747976273835231940.download Key not found!: 2  
[ 2026-03-29 11:20:28:167 ] [ 31940 ] [ERROR]  Error Message: Cannot create a file when that file already exists.


[ 2026-03-29 11:20:28:167 ] [ 31940 ] [INFO] End of ExternalDCDownloadHanlder::DownloadFile method[ 2026-03-29 11:20:28:199 ] [ 31940 ] [INFO] ValidateAndGetFileChecksum : Checksum value to compare : 83850ef6e6f75e3ea28e3b8c4205033cc07c7b08b9d6a5f8a60b95cf5893a817
[ 2026-03-29 11:20:28:199 ] [ 31940 ] [INFO] ValidateAndGetFileChecksum : Checksum value from file : 83850ef6e6f75e3ea28e3b8c4205033cc07c7b08b9d6a5f8a60b95cf5893a817
```

```javascript
26/03/29:11:20:28,dcreplication.exe,31940,-,GET,patchdb.manageengine.com,443,88173000000383041,/dc-crs/definitiondata/1.11/patchscan/1.270/superseded-tree-scan-data.7z,320938,320938,0,C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\TempXMLRepository\client-data\patch-resources\superseded-tree-scan-data.7z
26/03/30:11:23:10,dcreplication.exe,26032,-,GET,patchdb.manageengine.com,443,88173000000383041,/dc-crs/definitiondata/1.11/patchscan/1.270/patch-scan-data.xml.gz,220777,220777,0.000,0,C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\client-data/patch-resources/patch-scan-data.xml.gz
```

```javascript
[ 2026-03-27 03:18:37:873 ] [ 43464 ] [INFO] ReplicatePatchScanDataXML:  Move the files to actual path if Failed count is 0
[ 2026-03-27 03:18:37:907 ] [ 43464 ] [ERROR] MovePatchFiles: Files moving failed from C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\\TempXMLRepository\ to path: C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\ 
[ 2026-03-27 03:18:37:907 ] [ 43464 ] [ERROR] ReplicatePatchScanDataXML: Number of Resources Failed to Download : 0 for PatchScanData 
[ 2026-03-30 11:23:12:103 ] [ 26032 ] [INFO] @@@@@@@@@@@@@  Inside ReplicatePatchScanDataXML @@@@@@@@@@@@@@@
[ 2026-03-30 11:23:12:103 ] [ 26032 ] [INFO] Max version of PatchScanData : 1774765134 
[ 2026-03-30 11:23:12:103 ] [ 26032 ] [INFO] ReplicatePatchScanDataXML : Number of files changed 0 
[ 2026-03-30 11:23:12:103 ] [ 26032 ] [INFO] ReplicatePatchScanDataXML:  Move the files to actual path if Failed count is 0
[ 2026-03-30 11:23:12:119 ] [ 26032 ] [ERROR] MovePatchFiles: Files moving failed from C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\\TempXMLRepository\ to path: C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\ 
[ 2026-03-30 11:23:12:119 ] [ 26032 ] [ERROR] ReplicatePatchScanDataXML: Number of Resources Failed to Download : 0 for PatchScanData 
[ 2026-03-30 11:23:12:119 ] [ 26032 ] [INFO] @@@@@@@@@@@@@  End of ReplicatePatchScanDataXML @@@@@@@@@@@@@@@
[ 2026-03-30 11:23:12:119 ] [ 26032 ] [INFO] @@@@@@@@@@@@@  Inside ReplicatePatchScanDataXML @@@@@@@@@@@@@@@
[ 2026-03-30 11:23:12:119 ] [ 26032 ] [INFO] Max version of AdvPatchScanDetails : 1774765165 
[ 2026-03-30 11:23:12:119 ] [ 26032 ] [INFO] ReplicatePatchScanDataXML : Number of files changed 0 
[ 2026-03-30 11:23:12:135 ] [ 26032 ] [INFO] ReplicatePatchScanDataXML:  Move the files to actual path if Failed count is 0
[ 2026-03-30 11:23:12:141 ] [ 26032 ] [ERROR] MovePatchFiles: Files moving failed from C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\\TempXMLRepository\ to path: C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\ 
[ 2026-03-30 11:23:12:141 ] [ 26032 ] [ERROR] ReplicatePatchScanDataXML: Number of Resources Failed to Download : 0 for AdvPatchScanDetails 
[ 2026-03-30 11:23:12:141 ] [ 26032 ] [INFO] @@@@@@@@@@@@@  End of ReplicatePatchScanDataXML @@@@@@@@@@@@@@@
[ 2026-03-30 11:23:12:141 ] [ 26032 ] [INFO] @@@@@@@@@@@@@  Inside ReplicatePatchScanDataXML @@@@@@@@@@@@@@@
[ 2026-03-30 11:23:12:141 ] [ 26032 ] [INFO] Max version of HardwarePatchDetails : 1774619146 
[ 2026-03-30 11:23:12:141 ] [ 26032 ] [INFO] ReplicatePatchScanDataXML : Number of files changed 0 
[ 2026-03-30 11:23:12:141 ] [ 26032 ] [INFO] ReplicatePatchScanDataXML:  Move the files to actual path if Failed count is 0
[ 2026-03-30 11:23:12:151 ] [ 26032 ] [ERROR] MovePatchFiles: Files moving failed from C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\\TempXMLRepository\ to path: C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\ 
[ 2026-03-30 11:23:12:151 ] [ 26032 ] [ERROR] ReplicatePatchScanDataXML: Number of Resources Failed to Download : 0 for HardwarePatchDetails 
[ 2026-03-30 11:23:12:151 ] [ 26032 ] [INFO] @@@@@@@@@@@@@  End of ReplicatePatchScanDataXML @@@@@@@@@@@@@@@
```

