---
notion_id: "33343c23-a5e2-80c3-9675-d6bb5999dda7"
notion_last_edited: "2026-03-31T11:36:00.000Z"
tags:
  - "pre deployment"
  - "pre deployment script"
resolved: "False"
problem tags:
  - "pre-deployment script not working"
  - "system reboot while other config is in process"
Date: "2026-03-30"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003520809368"
---

# Issue:

Cx is afraid of the use case in which the battery is low and the machine is rebooted. something that in some OS patches or BIOS updates can causes issues.

Cx wants to add a script in the predeployment that will stop the patch installation if battery is low.



# Analysis:

```javascript
$battery = Get-CimInstance -ClassName Win32_Battery

if (-not $battery) {
    # No battery (desktop/VM)
    exit -1
}

$charge = $battery.EstimatedChargeRemaining

if ($charge -gt 30) {
    exit 0
} else {
    exit -1
}
```

Using this script with exit code 0 will check for battery percentage and proceedes with the patch deployment.



