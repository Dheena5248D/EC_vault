---
notion_id: "33c43c23-a5e2-80bb-8b53-ea1a4e232041"
notion_last_edited: "2026-04-08T06:22:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "Others"
Date: "2026-04-08"
---

# Issue:

Cx reported an issue in the Patch deployment functionality.

Issue : Regarding **intermittent execution of post-deployment scripts** in Patch Management.

**Customer Observation:**

- The behavior appears inconsistent during testing
- A **pre-deployment script** successfully stops a service (httpd.service) on the endpoint
- The server then proceeds with patch deployment, but in some cases, **no applicable patches are found**
- In such scenarios, the **post-deployment script does not execute**, resulting in the service not being restarted
**Customer Concern:**

The expectation is that the post-deployment script should execute regardless of whether patches are applied, to ensure service restoration.

**Scripts Shared by Customer:**

**Pre-Deployment Script:**

- Executes `/usr/local/manageengine/prepatch`
- Stops the httpd service before patching
**Post-Deployment Script:**

- Executes `/usr/local/manageengine/postpatch`
- Starts the httpd service after patching
Both scripts include validation checks and return appropriate exit codes.

**Clarification Required:**

- Is the current product behavior designed to skip post-deployment scripts when no patches are applicable?
- If so, can this behavior be modified or enhanced to ensure post-deployment scripts run regardless of patch applicability?
Kindly review and provide your inputs on the expected behavior and possible solutions.

# Analysis:



# Log traces:



