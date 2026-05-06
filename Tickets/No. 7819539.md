---
Status: "Done"
tags:
problem tags:
Solved by: "ME"
Date: "2026-04-16"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003581914014"
---

# Issue:

Download Success but checksum failed Error : 60000.

# Analysis:

There is a known issue in the Cx build where the checksumType is being missed so the agent generate the hash with  wrong algorithm so the checksum mismatch occurs,

Issue fixed on 2605.13 and above, kindly suggest server upgrade

[https://www.manageengine.com/products/desktop-central/service-packs1.html](https://www.manageengine.com/products/desktop-central/service-packs1.html)

On analysing the log we observed that  the retry for deploying the patch has exhausted as the deployment failed caused by the known issue, so the patch patch deployment will fail after the server upgrade too.

Kindly ask the cx to modify the APD and save which resets the retry count of the APD task or deploy the failed patches manually after the server upgrade.

# Log traces:

```prolog
DesktopCentral Server Name                -> VPSVR.exedy-id.local
DesktopCentral Server IPAddress           -> 192.168.57.3
DesktopCentral Agent Version              -> 11.5.2605.11.W 
DesktopCentral Product Code               -> DCEE 
Local Computer Name                       -> VPSVR 
Local Computer IP Address                 -> 192.168.57.3 
The remote office name is                 -> Local Office
```



```prolog
[ 2026-04-13 09:41:30:332 ] [ 16872 ] [INFO] PostDownloadHandling : Successfully downloaded the file /store/357851-googlechromestandaloneenterprise64.msi?agentResourceIdentifier=308&ResourceID=308&uniqueValue=8AAA0A4900 from the server 192.168.57.3 to the destination file C:\Program Files (x86)\ManageEngine\UEMS_Agent\patches\357851-googlechromestandaloneenterprise64.msi 
[ 2026-04-13 09:41:30:332 ] [ 16872 ] [INFO] Successfully updated ecdatatransfer_access.log
[ 2026-04-13 09:41:30:332 ] [ 16872 ] [INFO] InternetGetDownloader : ResumeGetRequestEx errorCode = 0 
[ 2026-04-13 09:41:30:332 ] [ 16872 ] [ERROR] deleteValue:  Software\AdventNet\DesktopCentral\DCAgent\FileMetaData\17760480851539216872.download Key not found!: 2  
[ 2026-04-13 09:41:30:332 ] [ 16872 ] [ERROR]  Error Message: Cannot create a file when that file already exists.


[ 2026-04-13 09:41:30:332 ] [ 16872 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-13 09:41:30:347 ] [ 16872 ] [INFO] AgentSendRequest : Updating key inside main send request
[ 2026-04-13 09:41:30:347 ] [ 16872 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-13 09:41:32:004 ] [ 16872 ] [INFO] Checksum from file : c837983efa128539cb4476503e9501b1
[ 2026-04-13 09:41:32:004 ] [ 16872 ] [INFO] Checksum to compare : 18e3e0bb47b434ce21513bded672ba5ca83b521a8e42d73b24fc7acf4889d4ab
[ 2026-04-13 09:41:32:004 ] [ 16872 ] [INFO] Download succeeded but checksum failed.
```



```prolog
[ 2026-04-13 15:40:59:547 ] [ 12420 ] [INFO] Destination Path : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\357851-googlechromestandaloneenterprise64.msi
[ 2026-04-13 15:40:59:547 ] [ 12420 ] [INFO] RegChecksumFromDB : 18e3e0bb47b434ce21513bded672ba5ca83b521a8e42d73b24fc7acf4889d4ab ChecksumFromDB : 18e3e0bb47b434ce21513bded672ba5ca83b521a8e42d73b24fc7acf4889d4ab are same and retry expired. Not proceeding to download.
[ 2026-04-13 15:40:59:547 ] [ 12420 ] [ERROR] Error occurred while downloading the patch : 357851-googlechromestandaloneenterprise64.msi
```

