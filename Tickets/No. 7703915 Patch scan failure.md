---
notion_id: "33443c23-a5e2-8094-b5ad-e7cee3786f8a"
notion_last_edited: "2026-03-31T12:30:00.000Z"
tags:
  - "patch-scan"
  - "distribution server"
resolved: "False"
problem tags:
  - "patch scan failure"
Date: "2026-03-31"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003519677878"
---

# Issue:

Issue reported : Patch Scan failure.

# Analysis:

On analyzing the log there is communication issue between the agent and distribution server on the Cx end.

# Log traces:

```javascript
 DesktopCentral Server Name                -> SRV-PATCH-UPDATE 
  DesktopCentral Agent Version              -> 11.3.2435.1.W 
  Local Computer Name                       -> gis 
  Local Computer IP Address                 -> 192.168.21.30 
  DC Distribution Server  Name      			-> chowacoIIS 
  DC Distribution Server  IPAddress 			-> 192.168.21.63 
```

```javascript
[ 2025-01-11 11:54:53:378 ] [ 17112 ] [INFO]  @@@@@@@@@@@@ Inside InternetDownloadFileIfmodifiedSince method @@@@@@@@@@@@@
[ 2025-01-11 11:54:53:378 ] [ 17112 ] [INFO] If Modified Since variable is empty
[ 2025-01-11 11:54:53:378 ] [ 17112 ] [INFO] OS_PLATFORM=1 not added
[ 2025-01-11 11:54:53:385 ] [ 17112 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by client-data/global-meta-data.xml 
[ 2025-01-11 11:54:53:385 ] [ 17112 ] [ERROR] ChangeUtf8ToWideStr: utf8 is empty! 
[ 2025-01-11 11:54:53:386 ] [ 17112 ] [INFO] AgentSendRequest: EnablePocoCommunication is [0] 
[ 2025-01-11 11:54:53:386 ] [ 17112 ] [INFO] InternetGetRequestEx : DesktopCentral Server & Port -> 192.168.21.63 : 8384 
[ 2025-01-11 11:54:53:386 ] [ 17112 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2025-01-11 11:54:53:387 ] [ 17112 ] [INFO] GetInternetRequestHandle :  GET Request 
[ 2025-01-11 11:54:53:387 ] [ 17112 ] [INFO] Inside SetAuthentication DS
[ 2025-01-11 11:54:53:387 ] [ 17112 ] [INFO] InitializeAuthParamsForDownload :Encryption Key is disabled
[ 2025-01-11 11:54:53:406 ] [ 17112 ] [INFO] InitializeAuthParamsForDownload : Authtoken is available. 
[ 2025-01-11 11:54:53:406 ] [ 17112 ] [INFO] End of SetAuthentication DS
[ 2025-01-11 11:54:53:406 ] [ 17112 ] [INFO] SetAuthentication: Authenticated successfully 
[ 2025-01-11 11:54:53:406 ] [ 17112 ] [ERROR] CheckFileExists -> Invalid File Handle. 3 
[ 2025-01-11 11:54:53:406 ] [ 17112 ] [ERROR] GetInternetRequestHandle: destination file is not present, hence if-modified-since header is not applied
[ 2025-01-11 11:54:53:406 ] [ 17112 ] [INFO] Get request not to reporting server
[ 2025-01-11 11:54:53:406 ] [ 17112 ] [INFO] GetSecFlags: Security certificate installed, so validating certificate AND Certificate flags are ignored 
[ 2025-01-11 11:54:53:460 ] [ 17112 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2025-01-11 11:54:53:460 ] [ 17112 ] [INFO] GetInternetRequestHandle: Client Certificate set successfullly 
[ 2025-01-11 11:55:14:479 ] [ 17112 ] [INFO] DeletePrivateKeys: Deleted using d6fc44c08ada9321a68ff46f2decb1be7fe313b214aff2f3f55c4bba0f5b4bd19c1e63a148e71686a0d7bfbe9484f53f KeyContainer from Microsoft Software Key Storage Provider
[ 2025-01-11 11:55:14:479 ] [ 17112 ] [ERROR] GetInternetRequestHandle :  Error in WinHttpSendRequest -> 12002 
[ 2025-01-11 11:55:14:479 ] [ 17112 ] [ERROR] HttpGetLastError: The request has timed out.
[ 2025-01-11 11:55:14:479 ] [ 17112 ] [ERROR] Error in WinHttpQueryHeaders --> 12019 
[ 2025-01-11 11:55:14:479 ] [ 17112 ] [ERROR] HttpGetLastError: The requested operation can not be carried out because the handle supplied is not in the correct state.
[ 2025-01-11 11:55:14:480 ] [ 17112 ] [INFO] Successfully updated ecdatatransfer_access.log
[ 2025-01-11 11:55:14:480 ] [ 17112 ] [INFO] validateDSIPAddress: DS IP is not having multiple ip address, hence returning from the function
[ 2025-01-11 11:55:14:480 ] [ 17112 ] [INFO] AgentGetRequestHeader: DS IP updated:
```



