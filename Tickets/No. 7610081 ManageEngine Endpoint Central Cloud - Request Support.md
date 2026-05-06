---
notion_id: "32443c23-a5e2-8002-b59e-ea1ad78b7a17"
notion_last_edited: "2026-03-22T13:39:00.000Z"
tags:
  - "post reboot"
resolved: "False"
problem tags:
  - "post reboot not working"
Date: "2026-03-16"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003468474202"
---

# Problem:

User has configured the reboot on the deployment the deployment was success but the reboot prompt was not shown to user 



# Analysis:

After successful deplopyment of the patch the agent tries to process reboot but while doing it, dcconfigaccess.log crashed

there is a ticket that is simat to [[No. 7599467 “I need help on deployment policy - reboot prompt.”]] 

# Log trace:

```javascript
 Local Computer Name -> PC-NG-0152
 Local Computer IP Address -> 10.0.10.147,192.168.56.1
 DC Distribution Server Enabled -> no
```

```javascript
26-03-14 Ondemand Computer SYSTEM Install Patch pc-ng-0152 - testing restart notification 4270000003595755 New Collection 12:26:04 2 12:27:20 DC_NO_REBOOT SKIPPED --
26-03-14 AppCtrlPolicyDeployment Computer SYSTEM Install Patch pc-ng-0152 - testing restart notification 4270000003595755 New Collection 12:39:28 2 12:50:26
```

```javascript
26-03-14 4270000003595755 pc-ng-0152 - testing restart notification 112862 4270000003595919 Install Patch 12:48:30 12:50:23 REBOOT_REQUIRED [i18n]Reboot Pending[/i18n]
```



```javascript
<?xml version="1.0" encoding="UTF-8"?>
<agent-params>
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="NAME" PARAM_VALUE="PC-NG-0152" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="DOMAIN_NETBIOS_NAME" PARAM_VALUE="CARECORP" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="RESOURCE_ID" PARAM_VALUE="4270000000352667" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="DOMAIN_TYPE" PARAM_VALUE="2" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="COMPUTER_NAME" PARAM_VALUE="PC-NG-0152" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="UNIQUE_VALUE" PARAM_VALUE="CZC448550D" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="OS_PLATFORM" PARAM_VALUE="1" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="MSP_NAME" PARAM_VALUE="DC_MSP" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="RESOURCE_TYPE" PARAM_VALUE="1" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="REMARKS" PARAM_VALUE="[i18n]Reboot Pending[/i18n]" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="REMARKS_EN" PARAM_VALUE="[i18n]Reboot Pending[/i18n]" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="CONFIG_DATA_ID" PARAM_VALUE="4270000003595919" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="DOWNLOAD_STATUS_ID" PARAM_VALUE="200" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="STATUS" PARAM_VALUE="17" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="ERROR_CODE" PARAM_VALUE="328" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="COLLECTION_ID" PARAM_VALUE="4270000003595755" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="IP_ADDRESS" PARAM_VALUE="10.0.10.147,192.168.56.1" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="LAST_RETRY_ATTEMPT" PARAM_VALUE="0" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="TOTAL_RETRY_COUNT" PARAM_VALUE="0" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="NEXT_APPLY_TYPE" PARAM_VALUE="--" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="APPLY_TYPE" PARAM_VALUE="AppCtrlPolicyDeployment" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="COMPUTER_DOMAIN_NAME" PARAM_VALUE="CARECORP" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="AGENT_TIME" PARAM_VALUE="1773492510000" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="COLL_STATUS" PARAM_VALUE="6" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="COLL_REMARKS" PARAM_VALUE="[i18n]Reboot Pending[/i18n]" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="COLL_REMARKS_EN" PARAM_VALUE="[i18n]Reboot Pending[/i18n]" />
<AgentParams AGENT_PARAM_ID="3" PARAM_NAME="ERROR_GROUP_ID" PARAM_VALUE="8" />
</agent-params>
5099
[ 2026-03-14 13:04:52:709 ] [ 4908 ] [INFO] operation : ConstructRebootRequiredProps; collection_id : 4270000003595755; config_id : 151; restart_option : 3; is_exclude_server : FALSE;
[ 2026-03-14 13:04:52:709 ] [ 4908 ] [INFO] Restart  : DC_ALLOWSKIP_REBOOT ,timeoutToReboot  : 999 ,isthisMachineExcluded  : 0, rebootOnlyIfReq : 1
[ 2026-03-14 13:04:52:709 ] [ 4908 ] [INFO] installStatus  : 1 ,isRebootRequired  : 1 ,isMarkedforScheduled(is10008)  : 0
[ 2026-03-14 13:04:52:709 ] [ 4908 ] [INFO] operation : ConstructRebootRequiredProps; collection_id : 4270000003595755; config_id : 151; restart_option : 3; is_exclude_server : FALSE;
[ 2026-03-14 13:04:52:709 ] [ 4908 ] [INFO] operation : ProcessRebootPolicy; reboot_required_reason_id : 0; remarks : "Temporarily assigning as not-applicable";
[ 2026-03-14 14:07:58:622 ] [ 1240 ] [INFO] Log open time: 2026-03-14 14:07:58:622
[ 2026-03-14 14:07:58:622 ] [ 1240 ] [INFO] =====> Time: 14:7:58 14/3/2026 
```



