---
notion_id: "33443c23-a5e2-80db-8f49-d98d65db2a33"
notion_last_edited: "2026-03-31T12:19:00.000Z"
tags:
  - "direct-download"
  - "patch-deployment"
resolved: "False"
problem tags:
  - "proxy issue on Cx end"
Date: "2026-03-31"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003487252262"
---

# Issue:

To enable the direct download functionality, we have requested cx to apply the script on a test machine and deploy a patch to check the source of download before applying the script on other machines on environment.

CX reported that he deployed the patch but it is not deployed.

# Analysis:

The direct download is working as expected but there is communication issue that prevents the Agent from communicating with [patchdb.manageengine.com](http://patchdb.manageengine.com/) on Cx end. Cx  needs to whitelist the domain in order for the agent to download files properly from the internet. 

# Log traces:

```javascript
Local Computer Name                       -> MJPC-1082
 Local Computer IP Address                 -> 172.16.3.134 
 Local Computer Domain controller          -> MJKOLDC-01
  DirectDownloadEnabled : TRUE
```

```javascript
 26-03-31	  Ondemand	    SYSTEM	           MJPC-1082	16206	  10:46:44	      Filter_Success	  10:47:53
```

```javascript
[ 2026-03-31 10:47:47:214 ] [ 18684 ] [INFO] End of ExternalDCDownloadHanlder::DownloadFile method[ 2026-03-31 10:47:47:214 ] [ 18684 ] [ERROR] downloadXMLGZ : Download failure  filetoDownload : https://patchdb.manageengine.com//dc-crs/definitiondata/1.4/patchdata/1.9/dcdriverupdates.dll.gz
[ 2026-03-31 10:47:47:214 ] [ 18684 ] [INFO] downloadXMLGZ : extractXML is returning with status: 12007
[ 2026-03-31 10:47:47:214 ] [ 18684 ] [ERROR] ProcessPatchResourceXML : Failed to download dcdriverupdates.dll.gz
[ 2026-03-31 10:47:47:214 ] [ 18684 ] [ERROR] LoadPatchScanResourceXMLs : Problem while loading PatchResource XMLs
[ 2026-03-31 10:47:47:214 ] [ 18684 ] [ERROR] Unable to get last posted collection status data.
[ 2026-03-31 10:47:47:214 ] [ 18684 ] [INFO] GetRetryStatusData : TotalFailureRetryCount read sucess 
[ 2026-03-31 10:47:47:214 ] [ 18684 ] [INFO] GetRetryStatusData : ExecutedRetryCount Can't read 
[ 2026-03-31 10:47:47:214 ] [ 18684 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-31 10:47:47:214 ] [ 18684 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-31 10:47:47:214 ] [ 18684 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-31 10:47:47:214 ] [ 18684 ] [INFO] Inside ProcessPatchConfigTSStatus Method
[ 2026-03-31 10:47:47:230 ] [ 18684 ] [ERROR] IsFileExist : The required file (C:\Program Files (x86)\ManageEngine\UEMS_Agent\History\Configuration\patchConfigHistory.txt) size is 0 bytes. Hence returning file not found.
[ 2026-03-31 10:47:47:230 ] [ 18684 ] [INFO] SendConfigStatusUpdateEx : Data to Send to Server -> 
 <?xml version="1.0" encoding="UTF-8"?>
<agent-params>
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="NAME" PARAM_VALUE="MJPC-1082" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="DOMAIN_NETBIOS_NAME" PARAM_VALUE="MJ" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="RESOURCE_ID" PARAM_VALUE="13506" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="DOMAIN_TYPE" PARAM_VALUE="2" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="COMPUTER_NAME" PARAM_VALUE="MJPC-1082" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="UNIQUE_VALUE" PARAM_VALUE="18D38Q2" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="OS_PLATFORM" PARAM_VALUE="1" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="MSP_NAME" PARAM_VALUE="DC_MSP" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="RESOURCE_TYPE" PARAM_VALUE="1" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="REMARKS" PARAM_VALUE=" " />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="REMARKS_EN" PARAM_VALUE=" " />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="CONFIG_DATA_ID" PARAM_VALUE="0" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="DOWNLOAD_STATUS_ID" PARAM_VALUE="200" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="STATUS" PARAM_VALUE="8" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="ERROR_CODE" PARAM_VALUE="-1" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="COLLECTION_ID" PARAM_VALUE="16206" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="IP_ADDRESS" PARAM_VALUE="172.16.3.134" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="LAST_RETRY_ATTEMPT" PARAM_VALUE="0" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="TOTAL_RETRY_COUNT" PARAM_VALUE="2" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="NEXT_APPLY_TYPE" PARAM_VALUE="--" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="APPLY_TYPE" PARAM_VALUE="Ondemand" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="COMPUTER_DOMAIN_NAME" PARAM_VALUE="MJ" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="AGENT_TIME" PARAM_VALUE="1774934267000" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="COLL_STATUS" PARAM_VALUE="7" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="COLL_REMARKS" PARAM_VALUE="[i18n]dc.patch.configremarks.xml.downloadfailure@@@dcdriverupdates.dll.gz@@@12007[/i18n]" />
<AgentParams AGENT_PARAM_ID="0" PARAM_NAME="COLL_REMARKS_EN" PARAM_VALUE="Failed to download dcdriverupdates.dll.gz with error code : 12007" />
```

