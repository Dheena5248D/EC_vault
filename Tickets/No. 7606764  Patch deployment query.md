---
notion_id: "32543c23-a5e2-805c-9c1a-fae40ea3e3e5"
notion_last_edited: "2026-03-16T12:49:00.000Z"
tags:
  - "patch-deployment"
  - "manual-deployment"
resolved: "False"
problem tags:
  - "deploy imediatly not working"
Date: "2026-03-16"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003462193701"
---

# Issue:

Cx need some clarification regarding a patch deployment in PMP.

Patch details:

- File size: 1 file (283 KB)
- Policy: Deploy any time at the earliest
- Action: Deploy Immediately
- Created: Mar 13, 2026 02:52 PM
- Replication to DS: Mar 13, 2026 02:59 PM (Success)
- Executed at endpoint: Mar 13, 2026 03:21 PM
- Execution mode: During Refresh
**Questions:**

1. Replication to the Distribution Server completed within 7 minutes, but the execution only started at 03:21 PM, which is about 22 minutes after replication. Since the action was set to Deploy Immediately, could you clarify why there was a delay before execution started?

2. The execution shows "Execute during Refresh". As I understand, the agent refresh cycle is around 90 minutes.

a) Is there a way to force the patch deployment immediately without waiting for the refresh cycle?

b) Can the refresh cycle be shortened or manually triggered for urgent patching?



# Analysis:

on analyzing to the logs the Cx deployed the patch using deploy and not using the feature deploy immediately because the deployment carried over in refresh cycle and not on ondemand

## Answers to Cx questions:

1. The Cx didn’t used deploy instead of deploy immediately so deployment only take place in refresh cycle
1. 
# Log trace:

```javascript
13-03-2026   113956000000338001 113956000000338 4130753    15:21:34    15:21:46    SUCCESS       [i18n]dc.db.agent.config.patchscan.success[/i18n]                                          LinuxGroup1-20260313
```

```javascript
13-03-2026 refresh 15:21:02 15:21:58
```

```javascript
13-03-2026 Refresh 113956000000338001 INSTALL_PATCH 1139560000003380 15:21:17 15:21:47 SUCCESS 1 2 0 -- LinuxGroup1-20260313
```

