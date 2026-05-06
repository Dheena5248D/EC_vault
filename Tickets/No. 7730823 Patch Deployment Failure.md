---
notion_id: "33643c23-a5e2-80a6-aa27-da04b0116b4d"
notion_last_edited: "2026-04-02T13:16:00.000Z"
tags:
resolved: "False"
problem tags:
  - "patch upload failure"
Date: "2026-04-02"
---

# Issue:

Patchinstallation failure with error 404 for TightVNC Server (x64) (2.8.87)

It seems download failure

# Analysis:



# Log traces:



```sql
 DesktopCentral Server Name                -> TCG-UEM.sucralliance.fr 
 DesktopCentral Server Flat Name           -> TCG-UEM 
 DesktopCentral Server IPAddress           -> 172.18.63.4 
 Local Computer Name                       -> PO21794 
 DC Distribution Server  Name      			-> CRT-US1 
 DC Distribution Server  IPAddress 			-> 172.20.9.217 
 DC Distribution Server  Sec IPAddress         		-> (null) 
 DC Distribution Server  Port      			-> 8384  [INFO] DC Distribution Server  Last Access Name		-> CRT-US1 
 DC Distribution Server  Protocol  			-> https 
 Remote Office ID                          -> 601 
```





```sql
26-04-01	2179	DeployCorrectifTest	357623		357623		APD Deploy	23:03:05	23:03:05	FAILURE	Failed to download the patch from Server. Error : 404
26-04-01	10505	DeployCorrectifProd_Copy21	357623		357623		APD Deploy	23:03:54	23:03:54	FAILURE	Failed to download the patch from Server. Error : 404
26-04-01	10505	DeployCorrectifProd_Copy21	357623		357623		APD Deploy	23:17:41	23:17:41	FAILURE	Failed to download the patch from Server. Error : 404
26-04-01	2179	DeployCorrectifTest	357623		357623		APD Deploy	23:18:39	23:18:39	FAILURE	Failed to download the patch from Server. Error : 404
26-04-02	10505	DeployCorrectifProd_Copy21	357623		357623		APD Deploy	00:47:28	00:47:28	FAILURE	Failed to download the patch from Server. Error : 404
26-04-02	2179	DeployCorrectifTest	357623		357623		APD Deploy	00:48:20	00:48:20	FAILURE	Failed to download the patch from Server. Error : 404
```



```sql
[ 2026-04-02 00:48:20:434 ] [ 10768 ] [ERROR] IsFileExist : The File Name C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\357623-tightvnc-2.8.87-gpl-setup-server-64bit.msi is not found 2
[ 2026-04-02 00:48:20:434 ] [ 10768 ] [ERROR] ReadRegSZ: Error while opening registry key Software\AdventNet\DesktopCentral\DCAgent\CollectionHistory\2179\cs_mismatch ,and the error is  2 
[ 2026-04-02 00:48:20:434 ] [ 10768 ] [INFO] Message : L’opération a réussi.  
[ 2026-04-02 00:48:20:434 ] [ 10768 ] [INFO] InsertResumeDownloadFileSizeParams: Adding urlToDownload: /store/357623-tightvnc-2.8.87-gpl-setup-server-64bit.msi 	 checkSumValue: aa256612c5b8bb387355e9c4bce6068bf9ba77ef849f54efcf6087d86b86f52a,SHA256 
[ 2026-04-02 00:48:20:434 ] [ 10768 ] [ERROR] IsFileExist : The File Name C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\357623-tightvnc-2.8.87-gpl-setup-server-64bit.msi is not found 2
[ 2026-04-02 00:48:20:434 ] [ 10768 ] [INFO] OS_PLATFORM=1 not added
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by /store/357623-tightvnc-2.8.87-gpl-setup-server-64bit.msi 
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [ERROR] AgentSendRequest : gv_dcDSServerSecIPAddress is NULL.Hence not copied to dcServerSecIPAddressW.
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [INFO] AgentSendRequest: EnablePocoCommunication is [0] 
	[ 2026-04-02 00:48:20:480 ] [ 10768 ] [ERROR] isJsonorXmlRequest : gv_dcDynamicDownloadServer is NULL. Hence not copied to dynamicDownloadServer.
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [INFO] InternetGetDownloader : DesktopCentral Server & Port -> CRT-US1 : 8384 
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [INFO] InternetGetDownloader : Download Mode 1
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [INFO] httpRequestObjOld.m_externalVendorServer = 0 
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [ERROR] Initialize: proxyServerName is NULL.Hence not copied to m_proxyServerName.
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [ERROR] Initialize: proxyExceptionAddr is NULL.Hence not copied to m_proxyExceptionAddr.
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [ERROR] Initialize: proxyUserName is NULL.Hence not copied to m_proxyUserName.
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [ERROR] Initialize: proxyPassword is NULL.Hence not copied to m_proxyPassword.
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [INFO] Inside PreCheckForRangeRequest
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2026-04-02 00:48:20:480 ] [ 10768 ] [INFO] GetInternetRequestHandle : Send request with NO proxy 
[ 2026-04-02 00:48:20:485 ] [ 10768 ] [INFO] GetInternetRequestHandle :  HEAD Request 
[ 2026-04-02 00:48:20:485 ] [ 10768 ] [INFO] Inside SetAuthentication DS
[ 2026-04-02 00:48:20:485 ] [ 10768 ] [INFO] SetAuthenticationToDS : DS Authentication is disabled
[ 2026-04-02 00:48:20:528 ] [ 10768 ] [INFO] SetAuthentication: Authenticated successfully 
[ 2026-04-02 00:48:20:528 ] [ 10768 ] [INFO] Get request not to reporting server
[ 2026-04-02 00:48:20:528 ] [ 10768 ] [INFO] GetSecFlags: Security certificate installed, so validating certificate AND Certificate flags are ignored 
[ 2026-04-02 00:48:20:607 ] [ 10768 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2026-04-02 00:48:20:607 ] [ 10768 ] [INFO] GetInternetRequestHandle: Client Certificate set successfullly 
[ 2026-04-02 00:48:20:607 ] [ 10768 ] [ERROR] GetInternetRequestHandle :  WINHTTP_DISABLE_REDIRECTS --> success 
[ 2026-04-02 00:48:20:655 ] [ 10768 ] [INFO] writeValue : Valuename or Valuedata or Subkey is NULL
[ 2026-04-02 00:48:20:655 ] [ 10768 ] [INFO] LogHttpResponseHeaders: {Status:HTTP/1.1 404 Not Found, Content-Type:text/html, Content-Length:146, Server:nginx}
[ 2026-04-02 00:48:20:655 ] [ 10768 ] [INFO] GetInternetRequestHandle : WinHttpQueryHeaders http status code 404 
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [INFO] DeletePrivateKeys: Deleted using 9d6ea4fa51bce727c6579bc331c5f38bd377ea281a69e09e50d57bd82776baf04aa65508802480634d3d8e6586c59284 KeyContainer from Microsoft Software Key Storage Provider
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [ERROR] PreDownloadHandling : Failed with the http status code, 404 
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [INFO] Proceeding for PostDownloadHandling 
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [ERROR] @@@@@@@@ End Of ResumeGetRequestEx Method @@@@@@@@ 
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [INFO] InternetGetDownloader : ResumeGetRequestEx errorCode = 404 
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [ERROR] deleteValue:  Delete value downloadInProgress failure! 
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [ERROR]  Error Message: Impossible de cr�er un fichier d�j� existant.


[ 2026-04-02 00:48:20:724 ] [ 10768 ] [INFO] Message : L’opération a réussi.  
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [INFO] AgentSendRequest : Updating key inside main send request
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [INFO] Message : L’opération a réussi.  
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [INFO] deleteValue:  Delete value DCCreateProcessStatus success! 
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [ERROR] Error occurred while downloading the patch : 357623-tightvnc-2.8.87-gpl-setup-server-64bit.msi
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [ERROR] operation : GetEPMErrorIDByProductID; remarks : "Failed to get product id for the patch id : 0"; return_value : FALSE;
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [INFO] Inside GetFamilyIdForPatchId Method
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [INFO] *** Inside GetEPMErrorId method *** 
[ 2026-04-02 00:48:20:724 ] [ 10768 ] [INFO] Error ID : 92 and reamarks : [i18n]Problem while downloading the patch. HTTP Error : 404[/i18n] from EPMErrorCodes.
```

