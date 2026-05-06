---
notion_id: "32d43c23-a5e2-804d-b9f2-d82aaddd483e"
notion_last_edited: "2026-03-24T12:54:00.000Z"
tags:
resolved: "False"
problem tags:
Date: "2026-03-24"
---

# Issue:

ios password protection shows unprotected. As checked the logs, password protection shows fals. Cx mapped the credentials in console

# Analysis:

```prolog
[ 2026-03-18 14:40:03:373 ] [ 14596 ] [INFO] Connected to ROOT\CIMV2 WMI namespace
[ 2026-03-18 14:40:03:407 ] [ 14596 ] [ERROR] GetValuesUsingWMIQuery : The required Value is given by: 3
[ 2026-03-18 14:40:03:407 ] [ 14596 ] [INFO] [EC_BIOS::CredentialMappingForBios::GetAndStorePasswordProtectedStatus] => Setting Password protected status as 3
```

