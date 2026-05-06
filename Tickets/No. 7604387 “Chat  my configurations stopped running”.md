---
notion_id: "32243c23-a5e2-80d2-9d62-feec5d0f6772"
notion_last_edited: "2026-03-13T08:47:00.000Z"
tags:
  - "APD"
  - "filter"
  - "collection"
resolved: "False"
problem tags:
  - "collection not processed"
  - "meta-data files not modified"
Date: "2026-03-13"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003455646692"
---

# Problem:

The Cx has created a APT at 10:28 but the collection is not processed and patches are not deployed

# Analysis:

The Apd filter is never processed because the computer-rw.xml is not downloaded because the meta-data.xml is not modified so we need server logs,data folder and client-data from the Cx



```javascript
Local Computer Name                       -> AVONOIT01 
Local Computer IP Address                 -> 10.211.26.41 
DesktopCentral Agent Version              -> 11.4.2528.17.W 
DC Distribution Server Enabled            -> no 
```

```javascript
26-03-11	Refresh	  Computer	    SYSTEM	          APD Deploy	          DEFENDER_DEFINITIONS	11704	    Retry Collection	  22:41:07	    2	  22:41:28              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
26-03-12	Refresh	  Computer	    SYSTEM	          APD Deploy	          DEFENDER_DEFINITIONS	11704	    Retry Collection	  00:11:08	    2	  00:13:16              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
26-03-12	Refresh	  Computer	    SYSTEM	          APD Deploy	          DEFENDER_DEFINITIONS	11704	    Retry Collection	  01:41:07	    2	  01:41:28              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
26-03-12	Refresh	  Computer	    SYSTEM	          APD Deploy	          DEFENDER_DEFINITIONS	11704	    Retry Collection	  03:11:07	    2	  03:11:28              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
26-03-12	Refresh	  Computer	    SYSTEM	          APD Deploy	          DEFENDER_DEFINITIONS	11704	    Retry Collection	  04:41:07	    2	  04:41:28              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
26-03-12	Refresh	  Computer	    SYSTEM	          APD Deploy	          DEFENDER_DEFINITIONS	11704	    Retry Collection	  06:11:07	    2	  06:11:29              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
26-03-12	Refresh	  Computer	    SYSTEM	          APD Deploy	          DEFENDER_DEFINITIONS	11704	    Retry Collection	  07:41:07	    2	  07:41:28              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
26-03-12	Refresh	  Computer	    SYSTEM	          APD Deploy	          DEFENDER_DEFINITIONS	11704	    Retry Collection	  09:11:07	    2	  09:11:28              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
26-03-12	Refresh	  Computer	    SYSTEM	          APD Deploy	          DEFENDER_DEFINITIONS	11704	    Retry Collection	  10:41:16	    2	  10:47:28              DC_NO_REBOOT      RETRY_UNTIL_SUCCESS	   --
```

```javascript
[ 2026-03-12 10:40:13:539 ] [ 8112 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by client-data/1/domains/nsps/meta-data.xml 
[ 2026-03-12 10:40:13:539 ] [ 8112 ] [INFO] AgentSendRequest: EnablePocoCommunication is [0] 
[ 2026-03-12 10:40:13:539 ] [ 8112 ] [INFO] InternetGetRequestEx : DesktopCentral Server & Port -> 10.210.11.100 : 8383 
[ 2026-03-12 10:40:13:539 ] [ 8112 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2026-03-12 10:40:13:539 ] [ 8112 ] [INFO] GetInternetRequestHandle : Send request with Auto proxy or Default System proxy 
[ 2026-03-12 10:40:13:555 ] [ 8112 ] [INFO] GetInternetRequestHandle :  GET Request 
[ 2026-03-12 10:40:13:555 ] [ 8112 ] [INFO] Inside SetAuthentication 
[ 2026-03-12 10:40:13:571 ] [ 8112 ] [INFO] SetAuthentication: Authenticated successfully 
[ 2026-03-12 10:40:13:571 ] [ 8112 ] [INFO] End of SetAuthentication 
[ 2026-03-12 10:40:13:571 ] [ 8112 ] [INFO] Get request to reporting server
[ 2026-03-12 10:40:13:571 ] [ 8112 ] [INFO] GetSecFlags: Ignoring Certificate check flags added for communication 
[ 2026-03-12 10:40:13:634 ] [ 8112 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2026-03-12 10:40:13:634 ] [ 8112 ] [INFO] GetInternetRequestHandle: Client Certificate set successfullly 
[ 2026-03-12 10:40:13:762 ] [ 8112 ] [INFO] writeValue : Valuename or Valuedata is Empty 
[ 2026-03-12 10:40:13:762 ] [ 8112 ] [INFO] GetInternetRequestHandle : WinHttpQueryHeaders http status code 304 
```



