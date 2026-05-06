---
notion_id: "34443c23-a5e2-8050-8507-ea84a89c4bcf"
notion_last_edited: "2026-04-16T05:52:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "Others"
Date: "2026-04-16"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003531425915"
---

# Issue:

Patch downloads for Office 2024 and Firefox Updates fail

# Analysis:

- The connection timed out while downloading the Firefox patch binaries from the vendor site [https://download-installer.cdn.mozilla.net](https://download-installer.cdn.mozilla.net/) . Kindly request the customer to check with their network team for any network-level restrictions.
- Regarding the Office patch failure, it appears that the patch was not downloaded successfully on the central server, which caused the agent-side installation to fail with a 404 error.
- Please ask the customer to perform Step 2 from the following knowledge base article:
[https://www.manageengine.com/products/desktop-central/help/patch_management/microsoft-365-patch-download-failure.html](https://www.manageengine.com/products/desktop-central/help/patch_management/microsoft-365-patch-download-failure.html)

- The error level should be 0 if there are no network restrictions on the server when downloading files from the Microsoft CDN.
# Log traces:

```prolog
DesktopCentral Agent Version              -> 11.4.2516.35.W 
DesktopCentral Product Code               -> DCEE 
Local Computer Name                       -> NUC-SVD-PI1-006 
DC Distribution Server Enabled            -> no

[11:02:37:032]|[04-08-2026]|[PatchDownloadLogger]|[INFO]|[8943]|[SERVER-3a10b0fb-f09b-458f-b115-25fce08bd431]: Patch 	357378-Firefox Setup_149.0_x64.exe	https://download-installer.cdn.mozilla.net/pub/firefox/releases/149.0/win64/en-US/Firefox Setup 149.0.exe	0	DLOAD_FAILED REMARKS: java.net.ConnectException: Connection timed out: connect|

[11:02:15:958]|[04-08-2026]|[DownloadManager]|[INFO]|[8943]|[SERVER-3a10b0fb-f09b-458f-b115-25fce08bd431]: Going to establish connecton for https://download-installer.cdn.mozilla.net/pub/firefox/releases/149.0/win64/en-US/Firefox%20Setup%20149.0.exe|
[11:02:37:032]|[04-08-2026]|[DownloadManager]|[INFO]|[8943]|[SERVER-3a10b0fb-f09b-458f-b115-25fce08bd431]: Error occurred while reading & writing : D:\patch-repo\357378-Firefox Setup_149.0_x64.exe : java.net.ConnectException: Connection timed out: connect|

26-04-09	611	NUC-CSVC-CLT-APatch-MRestart-Continuel	43662		43662		APD Deploy	09:49:37	09:58:37	FAILURE	Failed to download office patch meta json with error code : 404

[ 2026-04-09 09:49:38:087 ] [ 5084 ] [INFO] execute : Process successfully created for application 43662-Office2024_installer_16.0.17932.20700_volume_x64.exe -pid 43661 -ch PerpetualVL2024 -oce 64 -v 16.0.17932.20700 -in 40014-officedeploymenttool_2024_volume.exe -prid ProPlus2024Volume 
[ 2026-04-09 09:58:37:514 ] [ 5084 ] [ERROR] Error Code : 404 , Error Message : The cloud file provider exited unexpectedly.  
[ 2026-04-09 09:58:37:514 ] [ 5084 ] [INFO] executeFileEx : Exit code for the application : 404 
[ 2026-04-09 09:58:37:514 ] [ 5084 ] [INFO] executeFileEx : Remarks from the CreateProcess is The cloud file provider exited unexpectedly.  for the executable 43662-Office2024_installer_16.0.17932.20700_volume_x64.exe -pid 43661 -ch PerpetualVL2024 -oce 64 -v 16.0.17932.20700 -in 40014-officedeploymenttool_2024_volume.exe -prid ProPlus2024Volume 

[ 2026-04-09 09:58:37:335 ] [ 8572 ] [INFO] executeFileEx : Remarks from the CreateProcess is Unknown Error. Code : -2147012852 for the executable "C:\Program Files (x86)\ManageEngine\UEMS_Agent\patches\office\43661\setup.exe" /configure "C:\Program Files (x86)\ManageEngine\UEMS_Agent\patches\office\43661\configure.xml" 
[ 2026-04-09 09:58:37:335 ] [ 8572 ] [ERROR] Office installation failed with error code : -2147012852
[ 2026-04-09 09:58:37:335 ] [ 8572 ] [INFO] Processing the Office Logs 
[ 2026-04-09 09:58:37:335 ] [ 8572 ] [INFO] CopyPath: C:\Program Files (x86)\ManageEngine\UEMS_Agent\\logs\43662\office_log_NUC-SVD-PI1-006-20260409-0956.log
[ 2026-04-09 09:58:37:337 ] [ 8572 ] [INFO] C:\Windows\Temp\NUC-SVD-PI1-006-20260409-0956.log log file copied successfully
[ 2026-04-09 09:58:37:337 ] [ 8572 ] [INFO] ************** Parsing started for file C:\Program Files (x86)\ManageEngine\UEMS_Agent\\logs\43662\office_log_NUC-SVD-PI1-006-20260409-0956.log ************** 
[ 2026-04-09 09:58:37:354 ] [ 8572 ] [INFO] Error Code: 30183, Error Type: "HttpTransportError", Error Message: "HttpTransportError (Sending Http GET request. Error: ClientCertificateRequired (0x80072f0c) , SourcePath: https://nuc-meec.itn.axusr.net:8383/store/office/43661/Office/Data/v64_16.0.17932.20700.cab' 
[ 2026-04-09 09:58:37:354 ] [ 8572 ] [INFO] Error Code: 30183, Error Type: "HttpTransportError", Error Message: "HttpTransportError (Sending Http GET request. Error: ClientCertificateRequired (0x80072f0c) , SourcePath: https://nuc-meec.itn.axusr.net:8383/store/office/43661/Office/Data/v64_16.0.17932.20700.cab' 
[ 2026-04-09 09:58:37:354 ] [ 8572 ] [INFO] Error Code: 30183, Error Type: "HttpTransportError", Error Message: "HttpTransportError (Sending Http GET request. Error: ClientCertificateRequired (0x80072f0c) , SourcePath: https://nuc-meec.itn.axusr.net:8383/store/office/43661/Office/Data/v64_16.0.17932.20700.cab' 
[ 2026-04-09 09:58:37:354 ] [ 8572 ] [INFO] Error Code: 30183, Error Type: "HttpTransportError", Error Message: "HttpTransportError (Sending Http GET request. Error: ClientCertificateRequired (0x80072f0c) , SourcePath: https://nuc-meec.itn.axusr.net:8383/store/office/43661/Office/Data/v64_16.0.17932.20700.cab' 
[ 2026-04-09 09:58:37:354 ] [ 8572 ] [INFO] Error Code: 30183, Error Type: "HttpTransportError", Error Message: "HttpTransportError (Sending Http GET request. Error: ClientCertificateRequired (0x80072f0c) , SourcePath: https://nuc-meec.itn.axusr.net:8383/store/office/43661/Office/Data/v64_16.0.17932.20700.cab' 
[ 2026-04-09 09:58:37:356 ] [ 8572 ] [INFO] ************** Parsing ended for log file C:\Program Files (x86)\ManageEngine\UEMS_Agent\\logs\43662\office_log_NUC-SVD-PI1-006-20260409-0956.log **************
```

