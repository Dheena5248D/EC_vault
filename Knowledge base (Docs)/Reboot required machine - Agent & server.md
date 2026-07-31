

# After installing Reboot required patches

After installing a reboot required patch installed the reboot required status will be sent to the server 

```xml|| log trace
<AgentParams AGENT_PARAM_ID="2" PARAM_NAME="OS_PLATFORM" PARAM_VALUE="1" />
<AgentParams AGENT_PARAM_ID="2" PARAM_NAME="FQDN_NAME" PARAM_VALUE="TBG-JLUSHEFSKI1.BG.local" />
<AgentParams AGENT_PARAM_ID="2" PARAM_NAME="REBOOT_REQUIRED_STATUS" PARAM_VALUE="0" />
<AgentParams AGENT_PARAM_ID="2" PARAM_NAME="REBOOT_REQUIRED_REASON" PARAM_VALUE="--" />
</agent-params>
```


# In server

The server will receive the post sent by agent and update the [[Tables#ResourceToRebootDetails]] table

Log trace to look for:

```log | powerreport.log

[10:28:13:310]|[03-16-2026]|[PowerReportLogger]|[INFO]|[2258]|[e53320e4-d4f5-435e-b835-aacdd8caba9d]: AgentParams received : {MSP_NAME=DC_MSP, REBOOT_REQUIRED_REASON=--, FQDN_NAME=dd, CUSTOMER_NAME=DC_CUSTOMER, RESOURCE_ID=606, OS_PLATFORM=1, UNIQUE_VALUE=VMWARE-56 4D 86 BD 47 1B D1 23-17 AA 72 22 A9 54 AE 98, REBOOT_REQUIRED_STATUS=0, DOMAIN_TYPE=1, DOMAIN_NETBIOS_NAME=WORKGROUP, NAME=dd}|
```

