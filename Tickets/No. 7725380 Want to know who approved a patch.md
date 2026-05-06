---
notion_id: "33543c23-a5e2-8008-8ed6-d79ebe060097"
notion_last_edited: "2026-04-01T08:43:00.000Z"
tags:
resolved: "False"
problem tags:
  - "Cx wants to know which coll trigred a reboot"
Solved by: "Others"
Date: "2026-04-01"
---

# Issue:

Cx reports that *GlobalProtect 6.3.x* appeared on endpoints without being approved for deployment. The patch was later manually declined, but it had already been installed on some machines, indicating a possible bypass of the approval process.

**Queries from Cx:**

- Is there a way to track which user/process approved the patch?
- Are there audit logs for patch approval actions?
- Under what scenarios can a patch get approved/deployed without explicit admin approval?
**Requirement:**

Need to identify how the patch got approved/deployed and prevent recurrence

# Analysis:

- Is there a way to track which user/process approved the patch?
- Are there audit logs for patch approval actions?
- Under what scenarios can a patch get approved/deployed without explicit admin approval?
# Log traces:

```sql
[11:10:21:092]|[12-08-2025]|[PatchActionLogger]|[INFO]|[308]|[e430a446-a60f-4e0d-a639-4247800015a7]: approve patches for : Patches [351016] : Customers [1]|
15231
[11:10:21:185]|[12-08-2025]|[PatchActionLogger]|[INFO]|[308]|[e430a446-a60f-4e0d-a639-4247800015a7]: Approve Patch List is ::[351016]for customer ::1|
```



