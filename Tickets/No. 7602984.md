---
notion_id: "33543c23-a5e2-80d3-a87b-c319e737aee1"
notion_last_edited: "2026-04-01T17:48:00.000Z"
tags:
resolved: "False"
problem tags:
  - "checksum mismatch"
Solved by: "Others"
Date: "2026-04-01"
---

# Issue:



# Analysis:

The patch 40378 is the dependency patch of the main patch 43573 the download of the dependent patch returns status code 206 and the file size is126 mb where as the real file size is 509 mb 

# Log traces:

```sql
 2026-03-30 10:20:36:325 ] [ 13480 ] [INFO] InsertResumeDownloadFileSizeParams: Adding urlToDownload: /store/40378-windows11.0-kb5043080-x64_953449672073f8fb99badb4cc6d5d7849b9c83e8.msu?agentResourceIdentifier=2114&ResourceID=2114&uniqueValue=VMWARE-42%2011%2038%2033%200F%20E4%20D4%20A3-97%20B0%20DD%208E%2004%2099%20B3%2082 	 filesize: 126071685 
[ 2026-03-30 10:20:36:325 ] [ 13480 ] [INFO] isdownloadServerRequest 0
[ 2026-03-30 10:20:36:325 ] [ 13480 ] [INFO] Inside DownloadResumeHandler::Initialize
[ 2026-03-30 10:20:36:325 ] [ 13480 ] [INFO] Download folder = DownloadRepository\	periodic save limit = 1048576
[ 2026-03-30 10:20:36:327 ] [ 13480 ] [INFO] GetTimeInSeconds : Time in Second : 1774880436
[ 2026-03-30 10:20:36:327 ] [ 13480 ] [INFO] Formed Unique id for the file is 17748804361020013480.download
[ 2026-03-30 10:20:36:327 ] [ 13480 ] [INFO] Temporary file path is C:\Program Files (x86)\ManageEngine\UEMS_Agent\DownloadRepository\
[ 2026-03-30 10:20:36:327 ] [ 13480 ] [INFO] ResumeGetRequestEx : To update download count
[ 2026-03-30 10:20:36:329 ] [ 13480 ] [INFO] End of DownloadResumeHandler::Initialize
[ 2026-03-30 10:20:36:329 ] [ 13480 ] [ERROR] ResumeGetRequestEx: Content-Range Header message: Range: bytes=0-126071684
[ 2026-03-30 10:20:36:329 ] [ 13480 ] [INFO] Header message: Range: bytes=0-126071684 
[ 2026-03-30 10:20:36:329 ] [ 13480 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2026-03-30 10:20:36:329 ] [ 13480 ] [INFO] GetInternetRequestHandle : Send request with NO proxy 
[ 2026-03-30 10:20:36:329 ] [ 13480 ] [INFO] GetInternetRequestHandle :  GET Request 
[ 2026-03-30 10:20:36:329 ] [ 13480 ] [INFO] Inside SetAuthentication 
[ 2026-03-30 10:20:36:357 ] [ 13480 ] [INFO] SetAuthentication: Authenticated successfully 
[ 2026-03-30 10:20:36:358 ] [ 13480 ] [INFO] End of SetAuthentication 
[ 2026-03-30 10:20:36:358 ] [ 13480 ] [INFO] Get request not to reporting server
[ 2026-03-30 10:20:36:358 ] [ 13480 ] [INFO] GetSecFlags: Security certificate installed, so validating certificate AND Certificate flags are ignored 
[ 2026-03-30 10:20:36:422 ] [ 13480 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2026-03-30 10:20:36:422 ] [ 13480 ] [INFO] GetInternetRequestHandle: Client Certificate set successfullly 
[ 2026-03-30 10:20:36:422 ] [ 13480 ] [ERROR] GetInternetRequestHandle :  WINHTTP_DISABLE_REDIRECTS --> success 
[ 2026-03-30 10:20:36:472 ] [ 13480 ] [INFO] writeValue : Valuename or Valuedata or Subkey is NULL
[ 2026-03-30 10:20:36:472 ] [ 13480 ] [INFO] GetInternetRequestHandle : WinHttpQueryHeaders http status code 206 
[ 2026-03-30 10:20:36:497 ] [ 13480 ] [INFO] DeletePrivateKeys: Deleted using 589799cb8d62f02e86a561626e39ffca0c3da001cb81f5af8f4a94decddaf15ab541dfbef5582625fbfb3750c213a64f KeyContainer from Microsoft Software Key Storage Provider
[ 2026-03-30 10:20:36:497 ] [ 13480 ] [INFO] ResumeGetRequestEx: GetInternetRequestHandle function return code: 0
[ 2026-03-30 10:20:40:822 ] [ 13480 ] [INFO] ResumeGetRequestEx : Bytes read reached the contenlength
[ 2026-03-30 10:20:40:822 ] [ 13480 ] [INFO] ResumeGetRequestEx : Total Time Taken for download : 4.325 seconds
[ 2026-03-30 10:20:40:822 ] [ 13480 ] [INFO] ResumeGetRequestEx: Total bytes read = 126071685
[ 2026-03-30 10:20:40:826 ] [ 13480 ] [INFO] updated registry entries size  126071685 and last modified time Wed, 11 Mar 2026 12:19:14 GMT retry time 0
[ 2026-03-30 10:20:40:830 ] [ 13480 ] [INFO] Proceeding for PostDownloadHandling 
[ 2026-03-30 10:20:40:830 ] [ 13480 ] [INFO] Inside SaveToDestFile from C:\Program Files (x86)\ManageEngine\UEMS_Agent\DownloadRepository\17748804361020013480.download to C:\Program Files (x86)\ManageEngine\UEMS_Agent\patches\40378-windows11.0-kb5043080-x64_953449672073f8fb99badb4cc6d5d7849b9c83e8.msu
[ 2026-03-30 10:20:40:830 ] [ 13480 ] [INFO] CreateFolder : The Directory to create is C:\Program Files (x86)\ManageEngine\UEMS_Agent\patches\ 
[ 2026-03-30 10:20:41:144 ] [ 13480 ] [INFO] Inside CleanFileAndRegistry
[ 2026-03-30 10:20:41:169 ] [ 13480 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-03-30 10:20:41:169 ] [ 13480 ] [INFO] deleteValue:  Delete value / success! 
[ 2026-03-30 10:20:41:169 ] [ 13480 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-03-30 10:20:41:169 ] [ 13480 ] [ERROR] deleteValue:  Delete value / failure! 
[ 2026-03-30 10:20:41:169 ] [ 13480 ] [ERROR]  Error Message: The operation completed successfully.


[ 2026-03-30 10:20:41:169 ] [ 13480 ] [INFO] PostDownloadHandling : Successfully downloaded the file /store/40378-windows11.0-kb5043080-x64_953449672073f8fb99badb4cc6d5d7849b9c83e8.msu?agentResourceIdentifier=2114&ResourceID=2114&uniqueValue=VMWARE-42%2011%2038%2033%200F%20E4%20D4%20A3-97%20B0%20DD%208E%2004%2099%20B3%2082 from the server scg.promerica.com.do to the destination file C:\Program Files (x86)\ManageEngine\UEMS_Agent\patches\40378-windows11.0-kb5043080-x64_953449672073f8fb99badb4cc6d5d7849b9c83e8.msu 
[ 2026-03-30 10:20:41:173 ] [ 13480 ] [INFO] Successfully updated ecdatatransfer_access.log
[ 2026-03-30 10:20:41:173 ] [ 13480 ] [INFO] InternetGetDownloader : ResumeGetRequestEx errorCode = 0 
[ 2026-03-30 10:20:41:173 ] [ 13480 ] [ERROR] deleteValue:  Software\AdventNet\DesktopCentral\DCAgent\FileMetaData\17748804361020013480.download Key not found!: 2  
[ 2026-03-30 10:20:41:173 ] [ 13480 ] [ERROR]  Error Message: Cannot create a file when that file already exists.


[ 2026-03-30 10:20:41:173 ] [ 13480 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-30 10:20:41:173 ] [ 13480 ] [INFO] AgentSendRequest : Updating key inside main send request
[ 2026-03-30 10:20:41:175 ] [ 13480 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-30 10:20:43:379 ] [ 13480 ] [INFO] Checksum from file : 66706cf791efaea8d6c847613a8371c5cc48c20168f5baad8c0434221cadba68
[ 2026-03-30 10:20:43:379 ] [ 13480 ] [INFO] Checksum to compare : 819632610A101AF11C72907FB13FF05B5FB4222C0E263EE9A03BCC1D1D5F26A4
[ 2026-03-30 10:20:43:379 ] [ 13480 ] [INFO] Download succeeded but checksum failed.
```

