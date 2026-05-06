---
notion_id: "34843c23-a5e2-8046-ae89-f674430154ee"
notion_last_edited: "2026-04-20T12:52:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-20"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003588564300"
---

# Issue:

The cx has removed the device from SOM since the device was offline for long time. Now when the device is back online, the device does not show up in approval/managed though the agent is able to communicate.

# Analysis:

The remove computer feature is used to remove the computes from the manage engine console and db and the uninstallation will happen on the refresh cycle in the agent,

since the meachine was not online the uninstallation cannot be performed when the agent came online again the agent is present in the machine but when the agent tries to comunicate to the server the server returned 404 because the server can't find the computer from the db

since the agent is removed from the db the lincence will be freed up,

Kindly ask the Customer to uninstall the agent and install new agent

# Log traces:

```prolog
DesktopCentral Server Name                -> endpointcentral-agent8.manageengine.com 
DesktopCentral Agent Version              -> 11.4.2540.18.W 
DesktopCentral Customer Name	           -> Mike Tan 
DesktopCentral Client Namespace           -> EUROKARS 
DesktopCentral Server Data Path           -> client-data/85434000000213084/domains/eurokars 
The remote office name is                 -> Default Remote Office


[ 2026-03-18 17:39:07:938 ] [ 12348 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by /statusUpdate?computerName=SA-L20012&domainName=EUROKARS&domainType=2&actionToCall=1&actions=22&ResourceID=85434000006789353 


[ 2026-03-18 17:39:07:943 ] [ 12348 ] [INFO] InternetSendRequestEx:This is the correct file where the changes are available: inside Non Multipart[ 2026-03-18 17:39:08:148 ] [ 12348 ] [ERROR] InternetSendRequestEx : Failed to post the data to the server endpointcentral-agent8.manageengine.com with http status code 404 

```

