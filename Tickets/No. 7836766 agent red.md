---
notion_id: "34843c23-a5e2-80f4-bf25-e499b980b493"
notion_last_edited: "2026-04-20T07:20:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-20"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003592338457"
---

# Issue:

cx reported that the live status was not updated in the console and it was shown as red despite the connectivity is good

# Analysis:

On analysing the logs there is a known issue in the customers build where dcondemand.exe hangs if the agent to DMS connection gets disconnected within 20 seconds.

kindly ask the customer to upgrade the server to 11.5.2605.14 or above

[https://www.manageengine.com/products/desktop-central/service-packs.html](https://www.manageengine.com/products/desktop-central/service-packs.html)

# Log traces:

```prolog
DesktopCentral Server Name                -> endpointcentral-agent2.manageengine.eu
DesktopCentral Product Code               -> DCODEE 
Local Computer Name                       -> FJFDUARTE
DesktopCentral Agent Version              -> 11.5.2605.02.W 
DC Distribution Server Enabled            -> no 
The remote office name is                 -> Default Remote Office 
The Agent Machine Resource Id is given by -> 33141000000326051 



[ 2026-03-28 22:00:00:337 ] [ 14500 ] [INFO] AsyncWsHandler::RegisterEventHandlers - Event handlers registered successfully[ 2026-03-28 22:00:00:337 ] [ 14500 ] [INFO] AsyncWsHandler::ConnectDirectly:	Connecting[ 2026-03-28 22:00:00:692 ] [ 14500 ] [INFO] retDate :: 1774735200
[ 2026-03-28 22:00:00:692 ] [ 14500 ] [INFO] Connected successfully	with dms server at 1774735200
[ 2026-03-28 22:00:00:761 ] [ 46088 ] [INFO] Inside method OnTextMsg,bytes received is 58
[ 2026-03-28 22:00:00:761 ] [ 46088 ] [INFO] AsyncWsHandler::OnTextMsg:	Entered OnTextMsg	Text Message - [{"msg":{"reason":"INVALID_KEY"},"mtype":"-5","prd":"PM"}] : bytesReceived - 58
[ 2026-03-28 22:00:00:761 ] [ 46088 ] [INFO] @@@ Inside CDCJson::StringToJson
[ 2026-03-28 22:00:00:761 ] [ 46088 ] [INFO] @@@ End of CDCJson::StringToJson
[ 2026-03-28 22:00:00:761 ] [ 46088 ] [INFO] Mtype is -5
[ 2026-03-28 22:00:00:761 ] [ 46088 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-03-28 22:00:00:761 ] [ 46088 ] [INFO] deleteValue:  Delete value Dms_BlockConnection success! 
[ 2026-03-28 22:00:00:761 ] [ 46088 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-03-28 22:00:00:761 ] [ 46088 ] [ERROR] deleteValue:  Delete value dms_sid failure! 
[ 2026-03-28 22:00:00:765 ] [ 46088 ] [ERROR]  Error Message: Imposs�vel criar um ficheiro quando esse ficheiro j� existe.


[ 2026-03-28 22:00:00:765 ] [ 46088 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-03-28 22:00:00:765 ] [ 46088 ] [ERROR] deleteValue:  Delete value dms_uid failure! 
[ 2026-03-28 22:00:00:765 ] [ 46088 ] [ERROR]  Error Message: Imposs�vel criar um ficheiro quando esse ficheiro j� existe.


[ 2026-03-28 22:00:00:765 ] [ 46088 ] [INFO] Message : A operação foi concluída com êxito.  
[ 2026-03-28 22:00:00:765 ] [ 46088 ] [INFO] OnError: Socket Error - 1008 : Error Msg : Server closed the connection
[ 2026-03-28 22:00:00:765 ] [ 46088 ] [INFO] OnClose: Socket Error - 1008 : Error Msg : Server closed the connection
[ 2026-03-28 22:00:00:765 ] [ 46088 ] [INFO] WebSocket connection closed
[ 2026-03-28 22:00:00:765 ] [ 46088 ] [INFO] Setting connection failed event
[ 2026-03-28 22:00:00:765 ] [ 46088 ] [INFO] main thread already in wait state
[ 2026-03-28 22:00:01:769 ] [ 46088 ] [INFO] Created New Connection failed event
[ 2026-03-28 22:00:01:769 ] [ 35872 ] [INFO] wait handle actiontocall is 0 and errorCode is 0
[ 2026-03-28 22:00:01:769 ] [ 35872 ] [INFO] Going to kill current ws connection
[ 2026-03-28 22:00:01:769 ] [ 35872 ] [INFO] Successfully killed the current ws connection
[ 2026-03-28 22:00:01:769 ] [ 35872 ] [INFO] random interval is 6118
[ 2026-03-28 22:00:01:769 ] [ 35872 ] [INFO] Random timeout = 6118
[ 2026-03-28 22:00:01:769 ] [ 35872 ] [INFO] Wait for 87886118 milli seconds before next try
[ 2026-03-28 22:00:20:714 ] [ 14500 ] [INFO] End of wsconnection
```

