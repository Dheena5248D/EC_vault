---
notion_id: "33543c23-a5e2-801a-ab12-e3f5c801cd29"
notion_last_edited: "2026-04-05T07:05:00.000Z"
tags:
  - "checksum failure"
resolved: "False"
Difficulty: "1"
problem tags:
  - "checksum mismatch"
  - "patch scan failure"
Solved by: "ME"
Date: "2026-04-01"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003535110998"
---

**Related back to Tickets:** [[No. 7792112  Download Success but checksum failed Error  60000.]]

# Issue:

Download Success but checksum failed Error : 60000, agent communication seems fine, have requested logs from cx

# Analysis:

There is a known issue in the Cx build where the checksumType is being missed so the agent generate the hash wrongly so the checksum mismatch occurs,

Issue fixed on 2605.13 and above

# Log traces:

```sql
Local Computer Name                       -> veeam
 Local Computer IP Address                 -> 172.18.43.126
 DC Distribution Server  Name      			-> HPHWINPMP01V 
 DC Distribution Server  IPAddress 			-> 172.18.45.79 
 DesktopCentral Agent Version              -> 11.5.2605.09.W 
```

```sql
[ 2026-03-31 09:02:40:479 ] [ 17124 ] [INFO] Inside SaveToDestFile from C:\Program Files (x86)\ManageEngine\UEMS_Agent\DownloadRepository\17749189511701217124.download to C:\Program Files (x86)\ManageEngine\UEMS_Agent\patches\357326-googlechromestandaloneenterprise64.msi
[ 2026-03-31 09:02:40:479 ] [ 17124 ] [INFO] CreateFolder : The Directory to create is C:\Program Files (x86)\ManageEngine\UEMS_Agent\patches\ 
[ 2026-03-31 09:02:41:604 ] [ 17124 ] [INFO] Inside CleanFileAndRegistry
[ 2026-03-31 09:02:41:667 ] [ 17124 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-03-31 09:02:41:667 ] [ 17124 ] [INFO] deleteValue:  Delete value / success! 
[ 2026-03-31 09:02:41:667 ] [ 17124 ] [INFO] deleteValue:  Key found ...!: 0
[ 2026-03-31 09:02:41:667 ] [ 17124 ] [ERROR] deleteValue:  Delete value / failure! 
[ 2026-03-31 09:02:41:667 ] [ 17124 ] [ERROR]  Error Message: The operation completed successfully.


[ 2026-03-31 09:02:41:667 ] [ 17124 ] [INFO] PostDownloadHandling : Successfully downloaded the file /store/357326-googlechromestandaloneenterprise64.msi?agentResourceIdentifier=22829&ResourceID=22829&uniqueValue=9999-1356-6537-1092-3286-3597-11 from the server 172.18.45.79 to the destination file C:\Program Files (x86)\ManageEngine\UEMS_Agent\patches\357326-googlechromestandaloneenterprise64.msi 
[ 2026-03-31 09:02:41:667 ] [ 17124 ] [INFO] Successfully updated ecdatatransfer_access.log
[ 2026-03-31 09:02:41:667 ] [ 17124 ] [INFO] InternetGetDownloader : ResumeGetRequestEx errorCode = 0 
[ 2026-03-31 09:02:41:667 ] [ 17124 ] [ERROR] deleteValue:  Software\AdventNet\DesktopCentral\DCAgent\FileMetaData\17749189511701217124.download Key not found!: 2  
[ 2026-03-31 09:02:41:667 ] [ 17124 ] [ERROR]  Error Message: Cannot create a file when that file already exists.


[ 2026-03-31 09:02:41:667 ] [ 17124 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-31 09:02:41:667 ] [ 17124 ] [INFO] AgentSendRequest : Updating key inside main send request
[ 2026-03-31 09:02:41:667 ] [ 17124 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-31 09:02:45:026 ] [ 17124 ] [INFO] Checksum from file : 9b82f47ebbc6e5f737f15fd98baa350a
[ 2026-03-31 09:02:45:026 ] [ 17124 ] [INFO] Checksum to compare : dec9f617363e8a3fd888996ffea9a1806cc20fa23c4967a6bd691960cba29139
[ 2026-03-31 09:02:45:026 ] [ 17124 ] [INFO] Download succeeded but checksum failed.
```



