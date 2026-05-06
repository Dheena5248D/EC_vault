---
notion_id: "31f43c23-a5e2-808e-972a-c9ff67131e9f"
notion_last_edited: "2026-04-05T09:58:00.000Z"
tags:
  - "patch-scan"
  - "patch-deployment"
resolved: "True"
problem tags:
Date: "2026-03-10"
---

# Issue

Cx stated Certain patches are listed under Missing Patches, while the remarks indicate “The version already exists.” 

# Analysis

Cx stated Certain patches are listed under Missing Patches, while the remarks indicate “The version already exists.” 



```plain text
The patch was first installed on `23-02-26 15:36:50`
```

```javascript
26-02-23 21068 Critical Patches Deploy and Reboot after hours Nov 7 ==43403== ==43403== APD Deploy 15:36:50 08:26:29 REBOOT_REQUIRED [i18n]Reboot Pending[/i18n]
```

and the system next rebooted on `02-03-26 08:42:00`

```javascript
26-03-02 08:42:00 Information Restart triggered by Endpoint Central from the Remote Shutdown tool.
```

and the patch is rollbacked after reboot

```javascript
[ 2026-03-02 12:08:28:422 ] [ 28340 ] [INFO] Reading ErrorIds From the Registry
2979
[ 2026-03-02 12:08:28:422 ] [ 28340 ] [INFO] ErrorId for the PatchID 43403 : ==14015==
```

The patch is installed and reboot pending on `02-03-26 15:45:11`

```javascript
26-03-02 24007 Missing Patches March 2 pt3 ==43403== 54656 Install Patch 15:01:32 15:45:11 REBOOT_REQUIRED [i18n]Reboot Pending[/i18n]
```

But the system is last rebooted on `02-03-26 08:48:33`

```javascript
26-03-02 08:48:33 Restart The process C:\Windows\servicing\TrustedInstaller
```

And the patches are deployed again resulting in “The version already exists.”

```javascript
26-03-02 24007 Missing Patches March 2 pt3 ==43403== 54656 Install Patch 15:01:32 15:45:11 REBOOT_REQUIRED [i18n]Reboot Pending[/i18n]
26-03-04 24020 Missing Patches March 3 ==43403== 54718 Install Patch 09:02:54 09:02:54 REBOOT_REQUIRED [i18n]dc.db.agent.patchinstall.already_inst[/i18n]
26-03-04 24024 Zero Day March 4 ==43403== 54751 Install Patch 09:05:40 09:05:40 REBOOT_REQUIRED [i18n]dc.db.agent.patchinstall.already_inst[/i18n]
```



