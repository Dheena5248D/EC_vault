---
notion_id: "33b43c23-a5e2-8044-9ef8-e89390d47c0f"
notion_last_edited: "2026-04-07T13:11:00.000Z"
tags:
  - "patch-deployment"
  - "manual-deployment"
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-07"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003561242999"
---

# Issue:

Cx reported that Patch not get deployed on the machine even if the machine is online.

# Analysis:

On analysing the log and the configuration pdf the deployment was created at Apr 6, 2026 03:06 PM and the agent should have processed the collection on the next refresh cycle which happened on Apr 6, 2026 04:08 PM but on that refresh cycle the agent didn't download domain-related XML (computer.xml, computer-rw.xml) files which holds the information about the collection

For further analysis need the following:

1. server logs
1. client-data [C:\Program Files\UEMS_CentralServer\webapps\DesktopCentral\client-data]
# Log traces:

```sql
DesktopCentral Server Flat Name           -> ASTVWMESEP01 
DesktopCentral Agent Version              -> 11.4.2535.01.W 
Local Computer Name                       -> ASTWTEST01 
Local Computer IP Address                 -> 10.235.99.51
DC Distribution Server Enabled            -> no 
Local Computer Domain controller          -> ASTVWDC02
```

```sql
26-04-06	        Refresh	  16:08:00	       16:08:50
26-04-06	        Refresh	  17:38:31	       17:39:20
26-04-06	        Refresh	  19:08:42	       19:09:31
26-04-06	        Refresh	  20:38:28	       20:39:22
26-04-06	        Refresh	  22:09:01	       22:09:50
26-04-06	        Refresh	  23:39:13	       23:40:02
26-04-07	        Refresh	  01:09:24	       01:10:13
26-04-07	        Refresh	  02:39:36	       02:40:24
26-04-07	        Refresh	  04:09:13	       04:10:02
26-04-07	        Refresh	  05:39:13	       05:40:08
26-04-07	        Refresh	  07:09:48	       07:10:36
26-04-07	        Refresh	  08:39:51	       08:40:40
26-04-07	        Refresh	  10:09:21	       10:10:16
26-04-07	        Refresh	  11:39:56	       11:40:45
26-04-07	        Refresh	  13:09:26	       13:10:15
26-04-07	        Refresh	  14:40:00	       14:40:48
26-04-07	        Refresh	  16:10:04	       16:10:52
```

```sql
[ 2026-04-06 16:08:01:074 ] [ 1496 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by client-data/1/domains/ast/meta-data.xml 
[ 2026-04-06 16:08:01:074 ] [ 1496 ] [INFO] AgentSendRequest: EnablePocoCommunication is [0] 
[ 2026-04-06 16:08:01:074 ] [ 1496 ] [INFO] InternetGetRequestEx : DesktopCentral Server & Port -> 10.235.99.50 : 8383 
[ 2026-04-06 16:08:01:074 ] [ 1496 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2026-04-06 16:08:01:074 ] [ 1496 ] [INFO] GetInternetRequestHandle : Send request with Auto proxy or Default System proxy 
[ 2026-04-06 16:08:01:081 ] [ 1496 ] [INFO] GetInternetRequestHandle :  GET Request 
[ 2026-04-06 16:08:01:081 ] [ 1496 ] [INFO] Inside SetAuthentication 
[ 2026-04-06 16:08:01:093 ] [ 1496 ] [INFO] SetAuthentication: Authenticated successfully 
[ 2026-04-06 16:08:01:093 ] [ 1496 ] [INFO] End of SetAuthentication 
[ 2026-04-06 16:08:01:093 ] [ 1496 ] [INFO] Get request to reporting server
[ 2026-04-06 16:08:01:093 ] [ 1496 ] [INFO] GetSecFlags: Security certificate installed, so validating certificate AND Certificate flags are ignored 
[ 2026-04-06 16:08:01:119 ] [ 1496 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2026-04-06 16:08:01:119 ] [ 1496 ] [INFO] GetInternetRequestHandle: Client Certificate set successfullly 
[ 2026-04-06 16:08:01:119 ] [ 1496 ] [ERROR] GetInternetRequestHandle :  WINHTTP_DISABLE_REDIRECTS --> success 
[ 2026-04-06 16:08:01:184 ] [ 1496 ] [INFO] writeValue : Valuename or Valuedata is Empty 
[ 2026-04-06 16:08:01:184 ] [ 1496 ] [INFO] GetInternetRequestHandle : WinHttpQueryHeaders http status code 200 
[ 2026-04-06 16:08:01:202 ] [ 1496 ] [INFO] DeletePrivateKeys: Deleted using a0cc35e6cb9741e49c82f658f2a368e378a5a2353611c61d44ec374a6c1c37682a08c4f9f17aaf02912b38d5b289596a KeyContainer from Microsoft Software Key Storage Provider
[ 2026-04-06 16:08:01:202 ] [ 1496 ] [ERROR] Response Header doesn't contain Content-Encoding. 
[ 2026-04-06 16:08:01:202 ] [ 1496 ] [INFO] InternetGetRequestEx : Content Length of the request file: 7832 Bytes
[ 2026-04-06 16:08:01:202 ] [ 1496 ] [INFO] CreateFolder : The Directory to create is C:\Program Files (x86)\ManageEngine\UEMS_Agent\data\ 
[ 2026-04-06 16:08:01:204 ] [ 1496 ] [INFO] Bytes read reached the contenlength
[ 2026-04-06 16:08:01:204 ] [ 1496 ] [INFO] InternetGetRequestEx : Total Time Taken for download : 0.000 seconds
[ 2026-04-06 16:08:01:207 ] [ 1496 ] [INFO] InternetGetRequestEx : Total bytes read = 7832
[ 2026-04-06 16:08:01:207 ] [ 1496 ] [INFO] InternetGetRequestEx : GetFileSize returns :  7832
[ 2026-04-06 16:08:01:207 ] [ 1496 ] [INFO] InternetGetRequestEx : File completely downloaded..!
[ 2026-04-06 16:08:01:212 ] [ 1496 ] [INFO] InternetGetRequestEx : Successfully downloaded the file client-data/1/domains/ast/meta-data.xml?agentResourceIdentifier=3313&ResourceID=3313&uniqueValue=VMWARE-42%203F%20E7%2082%2083%202E%20A6%20DB-58%2045%20DC%20ED%2058%2079%2075%20D1 from the server 10.235.99.50 to the destination file C:\Program Files (x86)\ManageEngine\UEMS_Agent\data\meta-data.xml
```

