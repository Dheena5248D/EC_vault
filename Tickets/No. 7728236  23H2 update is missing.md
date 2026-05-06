---
notion_id: "33a43c23-a5e2-80bd-b339-c222ec8ffeb1"
notion_last_edited: "2026-04-06T06:13:00.000Z"
tags:
resolved: "False"
problem tags:
Date: "2026-04-06"
---

# Issue:



# Analysis:



# Log traces:

```sql
26-04-02	22501	Upgrade from 23H2-25H2	112729		22501		Install Patch	07:09:14	07:09:15	SKIPPED	[i18n]dc.db.agent.patchinstall.not_avail_dload[/i18n]
```

```sql
[ 2026-04-02 07:09:15:007 ] [ 23532 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by /store/112729-windows11-25H2-prereq-handler_x64_en.exe 
[ 2026-04-02 07:09:15:007 ] [ 23532 ] [INFO] InternetGetRequestEx : DesktopCentral Server & Port -> 10.40.48.199 : 8384 
[ 2026-04-02 07:09:15:007 ] [ 23532 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2026-04-02 07:09:15:007 ] [ 23532 ] [INFO] GetInternetRequestHandle : Send request with NO proxy 
[ 2026-04-02 07:09:15:007 ] [ 23532 ] [INFO] GetInternetRequestHandle :  HEAD Request 
[ 2026-04-02 07:09:15:007 ] [ 23532 ] [INFO] Inside SetAuthentication DS
[ 2026-04-02 07:09:15:007 ] [ 23532 ] [INFO] SetAuthenticationToDS : DS Authentication is disabled
[ 2026-04-02 07:09:15:023 ] [ 23532 ] [INFO] SetAuthentication: Authenticated successfully 
[ 2026-04-02 07:09:15:023 ] [ 23532 ] [INFO] Get request not to reporting server
[ 2026-04-02 07:09:15:023 ] [ 23532 ] [INFO] GetSecFlags: Security certificate installed, so validating certificate AND Certificate flags are ignored 
[ 2026-04-02 07:09:15:077 ] [ 23532 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2026-04-02 07:09:15:077 ] [ 23532 ] [INFO] GetInternetRequestHandle: Client Certificate set successfullly 
[ 2026-04-02 07:09:15:077 ] [ 23532 ] [ERROR] GetInternetRequestHandle :  WINHTTP_DISABLE_REDIRECTS --> success 
[ 2026-04-02 07:09:15:114 ] [ 23532 ] [INFO] writeValue : Valuename or Valuedata or Subkey is NULL
[ 2026-04-02 07:09:15:114 ] [ 23532 ] [INFO] GetInternetRequestHandle : WinHttpQueryHeaders http status code 404 
[ 2026-04-02 07:09:15:127 ] [ 23532 ] [INFO] DeletePrivateKeys: Deleted using 720d598272985027f96cbb77e70599c3accd10bca72c8d898de24ea3c1eef6fe39fb09c53e471686a9399592c68d780f KeyContainer from Microsoft Software Key Storage Provider
[ 2026-04-02 07:09:15:127 ] [ 23532 ] [ERROR] InternetGetRequestEx : Failed with the http status code, 404 
[ 2026-04-02 07:09:15:128 ] [ 23532 ] [INFO] Patch marked as available, but file size query failed with 404.
```



