---
notion_id: "33d43c23-a5e2-805b-97f9-f67829e2b929"
notion_last_edited: "2026-04-09T13:37:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-09"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003570393378"
---

**Related back to Tickets:** [[No. 7792112  Download Success but checksum failed Error  60000.]]

# Issue:

patch failed with remarks Download Success but checksum failed Error: 60000, despite deleted the downloaded patch and redeployed.

# Analysis:

There is a known issue in the Cx build where the checksumType is being missed so the agent generate the hash with  wrong algorithm so the checksum mismatch occurs,

Issue fixed on 2605.13 and above, kindly suggest server upgrade

[https://www.manageengine.com/products/desktop-central/service-packs1.html](https://www.manageengine.com/products/desktop-central/service-packs1.html)

On analysing the log we observed that  the retry for deploying the patch has exhausted as the deployment failed caused by the known issue, so the patch patch deployment will fail after the server upgrade too.

Kindly ask the cx to modify the APD and save which resets the retry count of the APD task or deploy the failed patches manually after the server upgrade.

# Log traces:

```prolog
DesktopCentral Server Name                -> MGMT-EC01.woodsvalldata.co.uk 
DesktopCentral Server IPAddress           -> 172.24.0.24 
DesktopCentral Agent Version              -> 11.5.2605.12.W 
DesktopCentral Product Code               -> DCEE 
Local Computer Name                       -> PCI-DC1 
The Agent Machine Resource Id is given by -> 1206 
DC Distribution Server Enabled            -> no 
```

```prolog
26-04-08	32407	Automated Server Updates	357732		357732		APD Deploy	19:04:27	19:04:28	FAILURE	Download Success but checksum failed Error : 60000.
26-04-08	32407	Automated Server Updates	357732		357732		APD Deploy	19:56:37	19:56:38	FAILURE	Download Success but checksum failed Error : 60000.
26-04-08	32407	Automated Server Updates	357732		357732		APD Deploy	21:26:40	21:26:41	FAILURE	Download Success but checksum failed Error : 60000.
26-04-08	32407	Automated Server Updates	357732		357732		APD Deploy	22:56:40	22:56:41	FAILURE	Download Success but checksum failed Error : 60000.
26-04-09	32407	Automated Server Updates	357732		357732		APD Deploy	00:26:38	00:26:39	FAILURE	Download Success but checksum failed Error : 60000.
26-04-09	32407	Automated Server Updates	357732		357732		APD Deploy	01:56:37	01:56:38	FAILURE	Download Success but checksum failed Error : 60000.
26-04-09	32407	Automated Server Updates	357732		357732		APD Deploy	03:26:34	03:26:35	FAILURE	Download Success but checksum failed Error : 60000.
```

```prolog
[ 2026-04-08 07:56:01:211 ] [ 6548 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by /store/357732-duo-win-login-latest.exe 
[ 2026-04-08 07:56:01:211 ] [ 6548 ] [INFO] InternetGetRequestEx : DesktopCentral Server & Port -> ec.woodsvalldata.co.uk : 8383 
[ 2026-04-08 07:56:01:211 ] [ 6548 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2026-04-08 07:56:01:211 ] [ 6548 ] [INFO] GetInternetRequestHandle : Send request with NO proxy 
[ 2026-04-08 07:56:01:211 ] [ 6548 ] [INFO] GetInternetRequestHandle :  HEAD Request 
[ 2026-04-08 07:56:01:211 ] [ 6548 ] [INFO] Inside SetAuthentication 
[ 2026-04-08 07:56:01:586 ] [ 6548 ] [INFO] SetAuthentication: Authenticated successfully 
[ 2026-04-08 07:56:01:586 ] [ 6548 ] [INFO] End of SetAuthentication 
[ 2026-04-08 07:56:01:586 ] [ 6548 ] [INFO] Get request not to reporting server
[ 2026-04-08 07:56:01:586 ] [ 6548 ] [INFO] GetSecFlags: Security certificate installed, so validating certificate AND Certificate flags are ignored 
[ 2026-04-08 07:56:01:992 ] [ 6548 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2026-04-08 07:56:01:992 ] [ 6548 ] [INFO] GetInternetRequestHandle: Client Certificate set successfullly 
[ 2026-04-08 07:56:01:992 ] [ 6548 ] [ERROR] GetInternetRequestHandle :  WINHTTP_DISABLE_REDIRECTS --> success 
[ 2026-04-08 07:56:02:008 ] [ 6548 ] [INFO] writeValue : Valuename or Valuedata or Subkey is NULL
[ 2026-04-08 07:56:02:008 ] [ 6548 ] [INFO] LogHttpResponseHeaders: {Status:HTTP/1.1 200 OK, Content-Type:application/x-msdownload, Content-Length:81941848, Last-Modified:Wed, 08 Apr 2026 06:41:53 GMT}
[ 2026-04-08 07:56:02:008 ] [ 6548 ] [INFO] GetInternetRequestHandle : WinHttpQueryHeaders http status code 200 
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] DeletePrivateKeys: Deleted using f096c05914ce2153fd77737ce67d4e622666414e73af3003f5dc716b7a140c4c68e0cbe045da9090058b9f0873e076d2 KeyContainer from Microsoft Software Key Storage Provider
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] InternetGetRequestEx : Content Length of the request file: 81941848 Bytes
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] isAvailable 1
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] isPatchAvailableinStore : 357732 , ret : 1 
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] String from Registry : 0409 and Integer after Conversion : 1033
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] LanguageID : 1
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] isPatchAvailableinStore (depfiles) ret : 1 
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] Inside WhiteListUrlIfMachineQuarantined Method
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] No need to whitelist
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] End of WhiteListUrlIfMachineQuarantined Method
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] Inside RemovePatchErrorIdFromRegistry Method
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [ERROR] deleteValue:  Software\AdventNet\DesktopCentral\DCAgent\CollectionHistory\63676\PatchErrorDetails Key not found!: 2  
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [ERROR]  Error Message: The operation completed successfully.


[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] ProcessPreDependencyPatches : Pre-dependency patch installation starts here for PatchID : 357732.
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] ProcessPreDependencyPatches : Pre-dependency patch process ends here for PatchID : 357732 with status : 6
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] @@@ Inside DownloadDepFile Method @@@
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] String from Registry : 0409 and Integer after Conversion : 1033
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] LanguageID : 1
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] @@@ End of DownloadDepFile Method @@@
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] 	 @@@@@@@@ Inside IsPatchPartiallySuperseded Method @@@@@@@@
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] String from Registry : 0409 and Integer after Conversion : 1033
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] LanguageID : 1
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [ERROR] PMPatchAppType is NULL
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] String from Registry : 0409 and Integer after Conversion : 1033
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] LanguageID : 1
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] PatchStoreLocation criteria : patchid=357732 and (languageid=0 or languageid=1)
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] Destination Path : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\357732-duo-win-login-latest.exe
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [ERROR] ReadRegSZ: Error while opening registry key Software\AdventNet\DesktopCentral\DCAgent\CollectionHistory\63676\cs_mismatch ,and the error is  2 
[ 2026-04-08 07:56:02:398 ] [ 6548 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-08 07:56:03:290 ] [ 6548 ] [INFO] Checksum from file : 1dd07cae2fc6031857c486f24c5a42fa
[ 2026-04-08 07:56:03:290 ] [ 6548 ] [INFO] Checksum to compare : a74531f270247e6e11a6f537e7e0c3abca8df0c96642ce4a37300ad517d644ee
[ 2026-04-08 07:56:03:290 ] [ 6548 ] [INFO] Checksum does not match.
```

```prolog
[ 2026-04-08 19:04:28:578 ] [ 2380 ] [INFO] PatchStoreLocation criteria : patchid=357732 and (languageid=0 or languageid=1)
[ 2026-04-08 19:04:28:578 ] [ 2380 ] [INFO] Destination Path : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\357732-duo-win-login-latest.exe
[ 2026-04-08 19:04:28:578 ] [ 2380 ] [INFO] RegChecksumFromDB : a74531f270247e6e11a6f537e7e0c3abca8df0c96642ce4a37300ad517d644ee ChecksumFromDB : a74531f270247e6e11a6f537e7e0c3abca8df0c96642ce4a37300ad517d644ee are same and retry expired. Not proceeding to download.
```

