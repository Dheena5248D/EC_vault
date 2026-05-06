---
notion_id: "32f43c23-a5e2-8029-be95-c55e9c562763"
notion_last_edited: "2026-03-26T09:02:00.000Z"
tags:
  - "checksum failure"
  - "patch-scan"
resolved: "False"
problem tags:
  - "checksum mismatch"
Date: "2026-03-26"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003516647153"
---

# Issue:

 CX reported that they having an issue with the deployment failing with error: ailed patch-scan-data.xml.gz download failed due to checksum mismatch error

# Analysis:

> [!info] I think that if i need to download a file is confirmed by validating the checksum if the checksum mismatches then it downloads the file????

If my above assumption is correct then the issue here is

The `patch-scan-data.xml.gz` file is not downloading in the DS due to issue on proxy or internet so the old `patch-scan-data.xml.gz` is downloaded in the agent resulting in checksum mismatch

Since It is cloud the ds directly downloads the file from the internet.

ask the Cx to open the link and download the `patch-scan-data.xml.gz` using a web browser by following the bellow link.

`https://patchdb.manageengine.com/dc-crs/definitiondata/1.11/patchscan/1.265/patch-scan-data.xml.gz` 



> [!info] If my above analyses is corrrect there is some questions to be answered
1.  How and where does the DS know the checksum of the file



# Log traces:

```javascript
[ 2026-03-24 14:54:21:756 ] [ 13036 ] [INFO] downloadXMLGZ : extractXML is returning with status: 0
[ 2026-03-24 14:54:21:764 ] [ 13036 ] [INFO] ValidateAndGetFileChecksum : Checksum value to compare : 628ed27657de8a22ce85ac56ea60d190f89b56e15f561d3c5496b912663ecbb6
[ 2026-03-24 14:54:21:764 ] [ 13036 ] [INFO] ValidateAndGetFileChecksum : Checksum value from file : b72dbca4f89cee695c05406c95ecb6e718fb0175e3ed6d0b3d9116a3fbe77f04
[ 2026-03-24 14:54:21:764 ] [ 13036 ] [ERROR] patch-scan-data.xml.gz checksum mismatch.
```

```javascript
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] @@@@@@@@@@@@@  Inside loadPatchResource @@@@@@@@@@@@@@@
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] ValidateAndGetFileChecksum : Checksum value to compare : 628ed27657de8a22ce85ac56ea60d190f89b56e15f561d3c5496b912663ecbb6
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] ValidateAndGetFileChecksum : Checksum value from file : b72dbca4f89cee695c05406c95ecb6e718fb0175e3ed6d0b3d9116a3fbe77f04
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] External file url is https://patchdb.manageengine.com/dc-crs/definitiondata/1.11/patchscan/1.265/patch-scan-data.xml.gz
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] Inside ExternalDCDownloadHanlder::DownloadFile method 
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] Dowloading File Path : C:\Program Files (x86)\ManageEngine\UEMS_DistributionServer\Replication\client-data/patch-resources/patch-scan-data.xml.gz 
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] ExternalDCDownloadHandler::DownloadFile: Setting org name/user agent for the attempt  1
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] server hash id is 1748951312
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] ExternalDCDownloadHanlder::DownloadFile : The User-Agent header value is set to the organization name: 1748951312 
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] protocol is https	Path is /dc-crs/definitiondata/1.11/patchscan/1.265/patch-scan-data.xml.gz
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] ExternalDownloadHandler::DownloadFile: EnablePocoCommunication is [0] 
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] InternetGetRequestEx : DesktopCentral Server & Port -> patchdb.manageengine.com : 443 
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] GetInternetRequestHandle : Send request with NO proxy 
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] GetInternetRequestHandle :  GET Request 
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] ExternalDownloadEnabled so skipping Auth Token
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] Get request not to reporting server
[ 2026-03-24 00:30:48:614 ] [ 2240 ] [INFO] master agent and dccloud defined, so validating certificate
[ 2026-03-24 00:30:48:630 ] [ 2240 ] [INFO] GetInternetRequestHandle : Going to close the request handle and going to resending the data to the server patchdb.manageengine.com 
[ 2026-03-24 00:30:48:630 ] [ 2240 ] [INFO] GetInternetRequestHandle : Send request with NO proxy 
[ 2026-03-24 00:30:48:630 ] [ 2240 ] [INFO] GetInternetRequestHandle :  GET Request 
[ 2026-03-24 00:30:48:630 ] [ 2240 ] [INFO] ExternalDownloadEnabled so skipping Auth Token
[ 2026-03-24 00:30:48:630 ] [ 2240 ] [INFO] Get request not to reporting server
[ 2026-03-24 00:30:48:630 ] [ 2240 ] [INFO] master agent and dccloud defined, so validating certificate
[ 2026-03-24 00:30:48:661 ] [ 2240 ] [ERROR] GetInternetRequestHandle :  Error in WinHttpSendRequest -> 12007 
[ 2026-03-24 00:30:48:661 ] [ 2240 ] [ERROR] HttpGetLastError: The server name could not be resolved.
[ 2026-03-24 00:30:48:661 ] [ 2240 ] [INFO] Inside CalculateNetworkBandwidth
[ 2026-03-24 00:30:49:672 ] [ 2240 ] [ERROR] InternetGetRequestEx :GetInternetRequestHandle failed with error code:12007
[ 2026-03-24 00:30:49:672 ] [ 2240 ] [INFO] End of ExternalDCDownloadHanlder::DownloadFile method
```

