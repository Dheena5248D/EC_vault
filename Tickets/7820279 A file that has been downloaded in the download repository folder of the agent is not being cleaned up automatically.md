---
ticket_id: "#7820279"
status: "Done"
date: "2026-04-13"
url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003582399114"
tags: ["patch clean up"]
solved_by: "ME"
---

# Issue:
A file that has been downloaded in the downloadrepository folder of the agent is not being cleaned up automatically.

# Analysis:
The incomplete downloaded files in download repository will be deletected in download repositary clean-up which happens in the intervel of 30 days, the 30 days clean-up window haven't reached so the file is not deleted

The patch was installed in 10/04/2026 in 13:02 and in the reboot pending state and still the patch is re downloaded in10/04/2026 in 17:50 and while downloading the system shoutdowned by the user which caused the incomplete download in download repository

re-downloading the patch that is already deplyed and in download pending state is not a expected behaviour,

[Aravindraja S](https://medcsupport.zohodesk.com/agent/medcsupport/all/setup#setup/users-control/agents/220709002120223987) please take care as discussed

# Log traces:
```prolog
26-04-10	16501	NEIN-MICROSOFT  PATCH -SYSTEM	43586	\t43586	\tAPD Deploy	12:34:02	13:02:14	REBOOT_REQUIRED	[i18n]Reboot Pending[/i18n]
```

```prolog
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by /store/43586-windows11.0-kb5079473-x64-25H2_win11.msu 
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [INFO] AgentSendRequest: EnablePocoCommunication is [0] 
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [ERROR] isJsonorXmlRequest : gv_dcDynamicDownloadServer is NULL. Hence not copied to dynamicDownloadServer.
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [INFO] InternetGetDownloader : DesktopCentral Server & Port -> NEINME.nittsu.co.in : 8383 
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [INFO] InternetGetDownloader : Download Mode 1
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [INFO] httpRequestObjOld.m_externalVendorServer = 0 
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [ERROR] Initialize: proxyServerName is NULL.Hence not copied to m_proxyServerName.
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [ERROR] Initialize: proxyExceptionAddr is NULL.Hence not copied to m_proxyExceptionAddr.
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [ERROR] Initialize: proxyUserName is NULL.Hence not copied to m_proxyUserName.
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [ERROR] Initialize: proxyPassword is NULL.Hence not copied to m_proxyPassword.
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [INFO] Inside PreCheckForRangeRequest
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [INFO] GetInternetRequestHandle : Send request with NO proxy 
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [INFO] GetInternetRequestHandle :  HEAD Request 
[ 2026-04-10 17:50:59:405 ] [ 28204 ] [INFO] Inside SetAuthentication 
[ 2026-04-10 17:50:59:433 ] [ 28204 ] [INFO] SetAuthentication: Authenticated successfully 
[ 2026-04-10 17:50:59:433 ] [ 28204 ] [INFO] End of SetAuthentication 
[ 2026-04-10 17:50:59:433 ] [ 28204 ] [INFO] Get request to reporting server
[ 2026-04-10 17:50:59:434 ] [ 28204 ] [INFO] GetSecFlags: Security certificate installed, so validating certificate AND Certificate flags are ignored 
[ 2026-04-10 17:50:59:486 ] [ 28204 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2026-04-10 17:50:59:486 ] [ 28204 ] [INFO] GetInternetRequestHandle: Client Certificate set successfullly 
[ 2026-04-10 17:50:59:486 ] [ 28204 ] [ERROR] GetInternetRequestHandle :  WINHTTP_DISABLE_REDIRECTS --> success 
[ 2026-04-10 17:51:01:102 ] [ 28204 ] [INFO] writeValue : Valuename or Valuedata or Subkey is NULL
[ 2026-04-10 17:51:01:102 ] [ 28204 ] [INFO] GetInternetRequestHandle : WinHttpQueryHeaders http status code 200 
[ 2026-04-10 17:51:01:134 ] [ 28204 ] [INFO] DeletePrivateKeys: Deleted using bcfeb2163c94a110484955c6ddc46394c9bbd11cc04e60b5dc2a6a91afa53feb024671a166d8d35f232e0d9cc20cf1be KeyContainer from Microsoft Software Key Storage Provider
[ 2026-04-10 17:51:01:134 ] [ 28204 ] [INFO] PreDownloadHandling : Content Length of the request file: 4209613965 Bytes
[ 2026-04-10 17:51:01:134 ] [ 28204 ] [INFO] InsertResumeDownloadFileSizeParams: Adding urlToDownload: /store/43586-windows11.0-kb5079473-x64-25H2_win11.msu?agentResourceIdentifier=15009&ResourceID=15009&uniqueValue=5CD91710WC \t filesize: 4209613965 
[ 2026-04-10 17:51:01:134 ] [ 28204 ] [INFO] isdownloadServerRequest 0
[ 2026-04-10 17:51:01:134 ] [ 28204 ] [INFO] Inside DownloadResumeHandler::Initialize
[ 2026-04-10 17:51:01:134 ] [ 28204 ] [INFO] Download folder = DownloadRepository\\\tperiodic save limit = 1048576
[ 2026-04-10 17:51:01:134 ] [ 28204 ] [INFO] GetTimeInSeconds : Time in Second : 1775823661
[ 2026-04-10 17:51:01:134 ] [ 28204 ] [INFO] Formed Unique id for the file is 17758236613028828204.download
```

```prolog
26-04-10		18:38:47		ShutDown		The process C:\\WINDOWS\\SystemApps\\Microsoft.Windows.StartMenuExperienceHost_cw5n1h2txyewy\\StartMenuExperienceHost
```

```prolog
26-04-10	         Logoff	  18:35:45	       18:35:48
26-04-11	        StartUp	  06:52:45	
```
