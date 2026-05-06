---
notion_id: "33e43c23-a5e2-805a-ab78-e3228740f390"
notion_last_edited: "2026-04-10T09:02:00.000Z"
tags:
resolved: "False"
problem tags:
Date: "2026-04-10"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003571773091"
---

<u>***Agent Details :***</u>

DesktopCentral Server Name                -> NG-MANAGEENG.ad.nordsterngroup.com

DesktopCentral Agent Version              -> 11.5.2605.12.W

Local Computer Name                       -> NG-CMP0107

DC Distribution Server Enabled            -> no

The remote office name is                 -> Local Office

<u>***Analysis Done:***</u>

This is a known issue where the checksumType is being missed to setup for isvalrequired = 0 patches.

<u>***Workaround***</u>:

After deployment is created ask the cx to perform Download Again using the button present in Downloaded Patches view for that patch.

**#################################**

The issue has been already fixed in 2605.13, but due to some critical issues in Patch SOM listener we cant able to suggest upgrade. The ETA for the fix would be Monday. Kindly move the ticket to WOE till Monday.

<u>***Log traces :***</u>

[ 2026-04-09 09:12:43:729 ] [ 4232 ] [INFO] PostDownloadHandling : Successfully downloaded the file /store/357851-googlechromestandaloneenterprise64.msi?agentResourceIdentifier=27601&ResourceID=27601&uniqueValue=MXL3493VCW from the server NG-MANAGEENG.ad.nordsterngroup.com to the destination file C:\Program Files (x86)\ManageEngine\UEMS_Agent\patches\357851-googlechromestandaloneenterprise64.msi

[ 2026-04-09 09:12:43:732 ] [ 4232 ] [INFO] Successfully updated ecdatatransfer_access.log

[ 2026-04-09 09:12:43:732 ] [ 4232 ] [INFO] InternetGetDownloader : ResumeGetRequestEx errorCode = 0

[ 2026-04-09 09:12:43:732 ] [ 4232 ] [ERROR] deleteValue:  Software\AdventNet\DesktopCentral\DCAgent\FileMetaData\1775743962153204232.download Key not found!: 2

[ 2026-04-09 09:12:43:732 ] [ 4232 ] [ERROR]  Error Message: Cannot create a file when that file already exists.

[ 2026-04-09 09:12:43:732 ] [ 4232 ] [INFO] Message : The operation completed successfully.

[ 2026-04-09 09:12:43:732 ] [ 4232 ] [INFO] AgentSendRequest : Updating key inside main send request

[ 2026-04-09 09:12:43:732 ] [ 4232 ] [INFO] Message : The operation completed successfully.

[ 2026-04-09 09:12:44:439 ] [ 4232 ] [INFO] Checksum from file : c837983efa128539cb4476503e9501b1

[ 2026-04-09 09:12:44:439 ] [ 4232 ] [INFO] Checksum to compare : 18e3e0bb47b434ce21513bded672ba5ca83b521a8e42d73b24fc7acf4889d4ab

[ 2026-04-09 09:12:44:439 ] [ 4232 ] [INFO] Download succeeded but checksum failed.

[ 2026-04-09 09:12:44:439 ] [ 4232 ] [INFO] deleteValue:  Key found ...!: 0

[ 2026-04-09 09:12:44:439 ] [ 4232 ] [INFO] deleteValue:  Delete value DCCreateProcessStatus success!

[ 2026-04-09 09:12:44:439 ] [ 4232 ] [ERROR] IsFileExist : Invalid Handle returned for C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\�S�E�� - 123

[ 2026-04-09 09:12:44:439 ] [ 4232 ] [ERROR] ReadRegSZ: Error while opening registry key Software\AdventNet\DesktopCentral\DCAgent\CollectionHistory\91803\cs_mismatch ,and the error is  2

[ 2026-04-09 09:12:44:439 ] [ 4232 ] [INFO] Message : The operation completed successfully.

[ 2026-04-09 09:12:44:439 ] [ 4232 ] [ERROR] Error occurred while downloading the patch : 357851-googlechromestandaloneenterprise64.msi



