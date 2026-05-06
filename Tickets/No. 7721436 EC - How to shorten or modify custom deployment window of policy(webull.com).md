---
notion_id: "33543c23-a5e2-8022-ab84-e98ed374e400"
notion_last_edited: "2026-04-02T07:03:00.000Z"
tags:
  - "ui"
  - "patch-deployment"
  - "deployment_window"
resolved: "False"
problem tags:
  - "ui rendering"
  - "patch not deleted from the agent after deployment"
Solved by: "Others"
Date: "2026-04-01"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003535181987"
---

# Issue:

Cx  requests to shorten the custom deployment window for a policy, as the current minimum allowed duration of 3 hours is too long for their non-working hours software installation needs, particularly during a 1.5-hour lunch break

# Analysis:

The deployment window’s minimum limit will be 3 hours if download Only during the deployment window is enabled and if download any time the agent contacts the server is selected the minimum window limit is 60 minutes



To shorten the deployment window, you can enable the "any time agent contacts the server" from the "Download patches from server to agent" option.

With this option enabled, the patches are pre-downloaded to the agent machine during the regular refresh cycle (staging). This means the agent does not wait for the deployment window to start downloading patches.

During the actual deployment window, only the installation is performed. With this option, you can configure the deployment window for 1.5 hours.

# Log traces:



