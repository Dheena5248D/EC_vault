---
notion_id: "34843c23-a5e2-8024-a22d-d07514771fe8"
notion_last_edited: "2026-04-20T14:58:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-20"
---

# Issue:

Cx facing agent communication error  with codes on 12019 \ 12030 \ 5930

# Analysis:

On analysing the log the agent can't communicate to the server right after agent installation

kindy follow this zask

[https://zask.pali.io/zask/EMSTechAsk/questions/8333049788](https://zask.pali.io/zask/EMSTechAsk/questions/8333049788),

if the issue still presits after following the steps kindly collect screenshots of steps like domain reachability page from agent troubleshoot tabe, console accessed from the browser of the agent and file download from the server on agent

# Log traces:

```prolog
DesktopCentral Server Name                -> patch-agent0.manageengine.uk
DesktopCentral Agent Version              -> 11.5.2606.07.W
DesktopCentral Product Code               -> PMPODEE  
Local Computer Name                       -> SSTU-AAPAGE01 
Local Computer IP Address                 -> 164.11.7.170 
The remote office name is                 -> Default Remote Office 
Local Computer Domain controller          -> DGEN-CAMPUS01
The Agent Machine Resource Id is given by -> (null)
```

```prolog
26-04-10	02:01:55	(null)	INSTALL		11.5.2606.07.W	SUCCESS	[NOT APPROVED]
26-04-16	08:12:56	(null)	INSTALL	MANUAL	11.5.2606.07.W	SUCCESS	[NOT APPROVED]
26-04-16	08:44:41	(null)	UNINSTALL	11.5.2606.07.W	FAILURE
26-04-16	09:31:17	(null)	INSTALL	Manual	11.5.2606.07.W	SUCCESS	[NOT APPROVED]
```

```prolog
[ 2026-04-10 02:01:59:220 ] [ 3796 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by /ClientCSRSigningServlet 
[ 2026-04-10 02:01:59:220 ] [ 3796 ] [INFO] AgentSendRequest: EnablePocoCommunication is [1] 
[ 2026-04-10 02:01:59:220 ] [ 3796 ] [INFO] InternetSendRequestEx : DesktopCentral Server & Port -> patch-agent0.manageengine.uk : 443 
[ 2026-04-10 02:01:59:220 ] [ 3796 ] [INFO] InternetSendRequestEx : Send request with NO proxy 
[ 2026-04-10 02:01:59:236 ] [ 3796 ] [INFO] Not Sending Compression header to Server...(compressedData=0)
[ 2026-04-10 02:01:59:236 ] [ 3796 ] [ERROR] InternetSendRequestEx : lpszHeaders is NULL.
[ 2026-04-10 02:01:59:236 ] [ 3796 ] [INFO] agent direct communication with server, so validating certificate
[ 2026-04-10 02:01:59:236 ] [ 3796 ] [ERROR] CreateClientAuthSignatureHeader: dcAgentResourceID is empty,clientauthsign_header not added
 [ 2026-04-10 02:01:59:298 ] [ 3796 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2026-04-10 02:01:59:298 ] [ 3796 ] [INFO] InternetSendRequestEx: Client Certificate set successfullly 
[ 2026-04-10 02:01:59:298 ] [ 3796 ] [INFO] InternetSendRequestEx:This is the correct file where the changes are available: inside Non Multipart[ 2026-04-10 02:01:59:298 ] [ 3796 ] [INFO] InternetSendRequestEx : Going to close the request handle and going to resending the data to the server patch-agent0.manageengine.uk 
[ 2026-04-10 02:01:59:314 ] [ 3796 ] [INFO] InternetSendRequestEx : Send request with NO proxy 
[ 2026-04-10 02:01:59:314 ] [ 3796 ] [INFO] Not Sending Compression header to Server...(compressedData=0)
[ 2026-04-10 02:01:59:314 ] [ 3796 ] [ERROR] InternetSendRequestEx : lpszHeaders is NULL.
[ 2026-04-10 02:01:59:314 ] [ 3796 ] [INFO] agent direct communication with server, so validating certificate
[ 2026-04-10 02:01:59:314 ] [ 3796 ] [ERROR] CreateClientAuthSignatureHeader: dcAgentResourceID is empty,clientauthsign_header not added
 [ 2026-04-10 02:01:59:392 ] [ 3796 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2026-04-10 02:01:59:392 ] [ 3796 ] [INFO] InternetSendRequestEx: Client Certificate set successfullly 
[ 2026-04-10 02:01:59:392 ] [ 3796 ] [INFO] InternetSendRequestEx:This is the correct file where the changes are available: inside Non Multipart[ 2026-04-10 02:01:59:407 ] [ 3796 ] [ERROR] InternetSendRequestEx :  Error in WinHttpSendRequest -> 12030 
[ 2026-04-10 02:01:59:407 ] [ 3796 ] [ERROR] HttpGetLastError: The connection with the server has been terminated or an incompatible SSL protocol was encountered .
[ 2026-04-10 02:01:59:407 ] [ 3796 ] [INFO] Message : The operation completed successfully.  

```

