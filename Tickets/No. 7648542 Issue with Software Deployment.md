---
notion_id: "32f43c23-a5e2-805f-bb80-dbd506098f77"
notion_last_edited: "2026-03-26T07:19:00.000Z"
tags:
  - "APD"
  - "post reboot"
resolved: "False"
problem tags:
  - "system reboot while other config is in process"
  - "post reboot not working"
Date: "2026-03-26"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003483554799"
---

# Issue:

The customer initiated a software deployment targeting machines with Git versions below 2.53.0.2. As part of the deployment workflow, the system checks for the existing version, uninstalls it if present, and proceeds with installing the configured version.

However, during the installation phase, another Automated Patch Deployment (APD) task triggered a system restart. This interruption caused the software installation process to cut abruptly.

After the restart and completion of patch deployment, Endpoint Central retried the software deployment. As per the flow, we will initiate the deployment from beginning, but now the system detected that the software was not present, as it was uninstalled previously before the reboot.



# Analysis:



# Log traces



