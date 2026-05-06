---
notion_id: "32d43c23-a5e2-804a-b05c-d70bfb367623"
notion_last_edited: "2026-03-24T16:11:00.000Z"
tags:
  - "post reboot"
  - "patch-deployment"
  - "APD"
resolved: "False"
problem tags:
  - "post reboot not working"
Date: "2026-03-24"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003494154473"
---

# Issuse:

Cx wants why The patch has been installed but the reboot is pending even though the reboot has been configured. 

# Analysis:

- The user has configured force reboot within deployment window ans skip reboot for server is disabled
- The meachine has successfully restarted after deployment
# Log traces:

```prolog
Local Computer Name                       -> atqsql1
Local Computer IP Address                 -> 192.168.0.9 
The remote office name is                 -> Longueuil - Servers (Proxy)
GetOSName: OS SP Name returned from global variable Windows Server 2016 Gold (x64)
IsServerOS : Os Name Windows Server 2016 Standard Edition (x64)
IsServerOS : TRUE  
```



```prolog
26-03-17		23:18:48		Restart		The process C:\Program Files (x86)\ManageEngine\UEMS_Agent\bin\dcmsghandler
```

```prolog
{
   "DepSettings" : {
      "638000000870607" : {
         "enable_notify" : false,
         "predeploy_action" : false,
         "reboot_during_awake" : false,
         "reboot_message" : "New Patches/Softwares are installed in your computer. It will be restarted.",
         "reboot_option" : 1,
         "reboot_timeout" : 5,
         "reboot_title" : "Reboot Message Title",
         "restart_and_shutdown" : false,
         "timezone" : "--"
      }
   },
   "ForceJobs" : [
      {
         "actionId" : 638000037993050,
         "collnId" : 638000032656021,
         "collnProcessedTime" : 1773803219,
         "configName" : "Servers - Microsoft Security Updates Only",
         "depPolicyId" : 638000000870607,
         "epochShowRebootPromptAt" : 0,
         "internalIsRebootType" : 1,
         "jobId" : 1
      }
   ]
}
```

