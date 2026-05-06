---
notion_id: "35743c23-a5e2-80c0-9702-cbf25f07c851"
notion_last_edited: "2026-05-05T12:03:00.000Z"
tags:
resolved: "False"
problem tags:
Date: "2026-05-05"
Learning priority: "medium"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003655162798"
---

# Issue:

Patch scan fails with the error: “Patch scan/deployment operation failed due to Linux repository management tool execution failure.

# Analysis:

- From the logs, the failure is due to permission denied while executing: /usr/local/manageengine/uems_agent/bin/dcrepolistmanager.
* This indicates that the execution permission is missing or modified for the dcrepolistmanager binary.

* Based on the screenshot shared, the file permissions appear to have been altered.

* Request the customer to check System antivirus may modify file permissions.

* If the issue is not related to antivirus arrange a remote session.

* Dev Availability: Monday to Friday, 10:00 AM – 4:00 PM

# Log traces:

```sql
	M_localMachineName:"ROC-UAT-B2C-Drupal
	M_linuxAgentVersion:"11.5.2605.13.L"
	M_remoteOfficeName:"Local Office"
	M_dsEnabled:"no"

Log traces : 

03-05-2026 19:13:09.263246 | 7340 | INFO  | EXEC COMMAND : /usr/local/manageengine/uems_agent/bin/dcrepolistmanager  ERROR : fork/exec /usr/local/manageengine/uems_agent/bin/dcrepolistmanager: permission denied 
03-05-2026 19:13:09.263847 | 7340 | ERROR | Unable to Write server-dc.repo file.  {fork/exec /usr/local/manageengine/uems_agent/bin/dcrepolistmanager: permission denied -1}

03-05-2026 19:13:09.264549 | 7340 | INFO  | Error details matching the agent error code is:  {1012 Linux Repository Management Tool Failures  1203 618  Patch scan/deployment operation failed due to Linux repository management tool execution failure. Please contact support for further assistance. dc.db.agent.patch.repo_manager_operation_fail --}
03-05-2026 19:13:09.264870 | 7340 | INFO  | Error details available in the EPMErrorCodesLinux.xml file. map[CONFIG_ERROR_CODE:-1 CONFIG_REMARKS:[i18n]dc.db.agent.patch.repo_manager_operation_fail[/i18n] CONFIG_REMARKS_EN:Patch scan/deployment operation failed due to Linux repository management tool execution failure. Please contact support for further assistance. CONFIG_REMARK_TYPE:1103]
```

