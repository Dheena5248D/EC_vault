---
notion_id: "33743c23-a5e2-804a-a727-f0d6c8aba184"
notion_last_edited: "2026-04-05T07:30:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "Others"
Date: "2026-04-03"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003536452452"
---

# Issue:

The CX report mentions that, even though the testing and approval process is completed successfully, not all patches are installed on the servers:



The 

# Analysis:



# Log traces:

```sql
DATE	COLLECTION-ID	CONFIGUARATION-NAME	PATCH-ID   CONFIG_DATA_ID  	TYPE		STARTTIME	ENDTIME	 STATUS	REMARKS
----	-------------	-------------------	--------   --------------  	----		---------	-------	 ------	--------	
26-03-27	110861000000604213	7 Zip	355988		110861000000753045		Install Patch	15:00:34	15:01:06	SUCCESS	The operation completed successfully.
26-03-27	110861000000754001	Windows 11 Update	43589		110861000000753071		Install Patch	15:27:20	15:27:20	NAPPLICABLE	[i18n]dc.db.agent.patchinstall.not_app[/i18n]
26-03-31	110861000000604213	7 Zip	355988		110861000000787021		Install Patch	14:57:16	14:57:16	NAPPLICABLE	[i18n]dc.db.agent.patchinstall.already_inst[/i18n]
26-03-31	110861000000604213	7 Zip	355990		110861000000787023		Install Patch	14:57:16	14:57:16	NAPPLICABLE	[i18n]dc.db.agent.patchinstall.not_app[/i18n]
26-03-31	110861000000787047	MyConfiguration18	113130		110861000000787049		Install Patch	15:15:36	19:33:15	REBOOT_REQUIRED	[i18n]Reboot Pending[/i18n]
```

```sql
26-04-01		08:49:51		ShutDown		�B�z�{�� C:\WINDOWS\servicing\TrustedInstaller
26-04-01		08:51:18		ShutDown		�B�z�{�� C:\WINDOWS\servicing\TrustedInstaller
26-04-01		08:51:18		ShutDown		�B�z�{�� C:\Windows\SystemApps\Microsoft.Windows.StartMenuExperienceHost_cw5n1h2txyewy\StartMenuExperienceHost
```

