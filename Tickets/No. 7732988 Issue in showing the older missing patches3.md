---
notion_id: "33743c23-a5e2-8006-a9c5-cbbd824151c6"
notion_last_edited: "2026-04-05T06:59:00.000Z"
tags:
resolved: "False"
problem tags:
  - "patch scan failure"
  - "collection not processed"
Solved by: "Others"
Date: "2026-04-03"
---

# Issue:

User reported that patch installation is failing for the patch ID 112729 - Feature Pack Update for Windows 11 (25H2) (x64) (Windows 11 to Windows 11)

# Analysis:

From the provided logs we could see that the patch deployment failed with **ISO file extraction failed**. Since the logs have been rotated, we are unable to identify the exact root cause.

Kindly ask the cx to **reproduce the issue and immediately collect and share the agent logs**. This will help us analyze the issue and provide a fix

# Log traces:

```sql

26-03-20	106203	W11 EOL Machines - 25H2 Feature Deployment Part 1	112729		106803		Install Patch	09:28:25	09:28:47	FAILURE	[i18n]ISO file extraction failed. (50004)[/i18n]
```

