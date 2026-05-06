---
notion_id: "33e43c23-a5e2-80c3-b8af-e017a0258f23"
notion_last_edited: "2026-04-10T09:00:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-10"
---

# Issue:

Patch Download failed with error :  FAILURE Download Success but checksum failed Error : 60000.

# Analysis:

There is a known issue in the Cx build where the checksumType is being missed so the agent generate the hash with  wrong algorithm so the checksum mismatch occurs,

**Workaround:**

As a workaround After deployment is created ask the cx to perform Download Again using the button present in Downloaded Patches view for that patch



The issue has been already fixed in 2605.13, but due to some critical issues in Patch SOM listener we cant able to suggest upgrade. The ETA for the fix would be Monday. Kindly move the ticket to WOE till Monday.

# Log traces:

```sql
DesktopCentral Server Name                -> CA-GT-ME.UNILOCKGRP.COM
DesktopCentral Server Flat Name           -> CA-GT-ME 
DesktopCentral Product Code               -> DCEE 
DesktopCentral Agent Version              -> 11.5.2605.12.W 
Local Computer Name                       -> CA-GTO-LKBLAIR4 
Local Computer IP Address                 -> 10.99.1.217,172.16.10.170 
DC Distribution Server Enabled            -> no 


26-04-09	162301	MyConfiguration31578	357851		217801		Install Patch	12:24:18	12:24:32	FAILURE	Download Success but checksum failed Error : 60000.

[ 2026-04-09 09:42:19:522 ] [ 25556 ] [INFO] PatchStoreLocation criteria : patchid=357851 and (languageid=0 or languageid=1)
[ 2026-04-09 09:42:19:522 ] [ 25556 ] [INFO] Destination Path : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\357851-googlechromestandaloneenterprise64.msi
[ 2026-04-09 09:42:19:522 ] [ 25556 ] [INFO] RegChecksumFromDB : 18e3e0bb47b434ce21513bded672ba5ca83b521a8e42d73b24fc7acf4889d4ab ChecksumFromDB : 18e3e0bb47b434ce21513bded672ba5ca83b521a8e42d73b24fc7acf4889d4ab are same and retry expired. Not proceeding to download.
[ 2026-04-09 09:42:19:522 ] [ 25556 ] [ERROR] Error occurred while downloading the patch : 357851-googlechromestandaloneenterprise64.msi
```

