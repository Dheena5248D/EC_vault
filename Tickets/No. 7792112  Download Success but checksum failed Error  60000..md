---
notion_id: "33e43c23-a5e2-80db-a407-ed4dc0e8113c"
notion_last_edited: "2026-04-10T09:06:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-10"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003569192446"
---

**similar Tickets:** [[No. 7792112  Download Success but checksum failed Error  60000.]], [[No. 7721393 download success but checksum failed error]], [[No. 7699852 Google chrome checksum mismatch]], [[No. 7605992 checksum error]], [[No. 7793885 patche checksum mismatch]], [[No. 7791661 Download Success but checksum failed Error  60000]], [[No. 7602984 Download success but checksum dailed error  6000]], [[No. 7720777  Download Success but checksum failed Error  60000]], [[No. 7696839 Download success but checksum failed Error60000]]
**Related back to Tickets:** [[No. 7792112  Download Success but checksum failed Error  60000.]]

# Issue:

Download success but checksum failed fro duo application deployment 

# Analysis:

There is a known issue in the Cx build where the checksumType is being missed so the agent generate the hash with wrong algorithm so the checksum mismatch occurs,

**Workaround:**

After deployment is created ask the cx to perform Download Again using the button present in Downloaded Patches view for that patch.

The issue has been already fixed in 2605.13, but due to some critical issues in Patch SOM listener we cant able to suggest upgrade. The ETA for the fix would be Monday. Kindly move the ticket to WOE till Monday.

# Log traces:

```sql
DesktopCentral Server Name                -> RLSYSMON01.corp.rhinolinings.com
DesktopCentral Server Flat Name           -> RLSYSMON01  
DesktopCentral Product Code                -> PMP
Local Computer Name                        -> TX_C003188
Local Computer IP Address                  -> 10.10.10.127
Local Computer MAC Address                 -> 70:b5:e8:78:c0:88
Local Computer Subnet Mask                -> 255.255.255.0
DC Distribution Server Enabled             -> no
The remote office name is                 -> Greenville TX
DesktopCentral Agent HTTP Request Timeout -> 60000
Local Computer Domain controller           -> RLGVDC02
```

```sql
[ 2026-04-09 08:54:21:169 ] [ 16760 ] [INFO] Destination Path : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\357851-googlechromestandaloneenterprise64.msi
[ 2026-04-09 08:54:21:169 ] [ 16760 ] [ERROR] ReadRegSZ: Error while opening registry key Software\AdventNet\DesktopCentral\DCAgent\CollectionHistory\78622\cs_mismatch ,and the error is  2 
[ 2026-04-09 08:54:21:185 ] [ 16760 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-09 08:54:21:950 ] [ 16760 ] [INFO] Checksum from file : c837983efa128539cb4476503e9501b1
[ 2026-04-09 08:54:21:950 ] [ 16760 ] [INFO] Checksum to compare : 18e3e0bb47b434ce21513bded672ba5ca83b521a8e42d73b24fc7acf4889d4ab
[ 2026-04-09 08:54:21:950 ] [ 16760 ] [INFO] Checksum does not match.
```

```sql
26-04-09	34214	Automated Updates - TX Workstations	357851		357851		APD Deploy	03:12:04	03:12:05	FAILURE	Download Success but checksum failed Error : 60000.
26-04-09	78622	DLW TX 04-09-2026	357851		89142		Install Patch	08:54:20	08:56:51	FAILURE	Download Success but checksum failed Error : 60000.
26-04-09	78622	DLW TX 04-09-2026	357851		89142		Install Patch	09:12:04	09:14:34	FAILURE	Download Success but checksum failed Error : 60000.
```

