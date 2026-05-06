---
notion_id: "33b43c23-a5e2-80b9-bba6-ccf30047a6b7"
notion_last_edited: "2026-04-07T05:57:00.000Z"
tags:
  - "checksum failure"
resolved: "False"
problem tags:
commented time: "2026-04-07T11:25:00.000+05:30"
Solved by: "ME"
Date: "2026-04-07"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003543729103"
---

# Issue:

There is a known issue on the cx build where checksum fails but the customer has upgraded the server to the latest version, still he is facing the same issue download success but checksum failed : 60000

# Analysis:

On analyzing the log the retry for deploying the patch has exhausted as the deployment failed caused by the known issue on Cx previous build resulting in the agent not retrying to deploy the patch on the machine.



Kindly ask the cx to modify the APD and save which resets the retry count of the APD task or deploy the failed patches manually 

# Log traces:

```sql
DesktopCentral Agent Version              -> 11.5.2605.13.W 
Local Computer Name                       -> A317-6200
Local Computer IP Address                 -> 192.168.213.22
Local Computer IP Address                 -> 192.168.213.22
DC Distribution Server Enabled            -> no
```



```sql
[ 2026-04-06 08:32:59:010 ] [ 10248 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by /store/357643-googlechromestandaloneenterprise64.msi  
[ 2026-04-06 08:32:59:010 ] [ 10248 ] [INFO] InternetGetRequestEx : DesktopCentral Server & Port -> 192.168.223.141 : 8383 
[ 2026-04-06 08:32:59:121 ] [ 10248 ] [INFO] LogHttpResponseHeaders: {Status:HTTP/1.1 200 OK, Content-Type:application/x-msdownload, Content-Length:150958080, Last-Modified:Thu, 02 Apr 2026 12:40:20 GMT}

[ 2026-04-06 08:32:59:185 ] [ 10248 ] [INFO] PatchStoreLocation criteria : patchid=357643 and (languageid=0 or languageid=1)
[ 2026-04-06 08:32:59:185 ] [ 10248 ] [INFO] Destination Path : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\357643-googlechromestandaloneenterprise64.msi
[ 2026-04-06 08:32:59:185 ] [ 10248 ] [INFO] RegChecksumFromDB : 203fb7bc6cf44140e193a97193f90a78d150009728fa654dde629838b5b1f4b3 ChecksumFromDB : 203fb7bc6cf44140e193a97193f90a78d150009728fa654dde629838b5b1f4b3 are same and retry expired. Not proceeding to download.
[ 2026-04-06 08:32:59:185 ] [ 10248 ] [ERROR] Error occurred while downloading the patch : 357643-googlechromestandaloneenterprise64.msi
```

[https://www.notion.so/7733556-Latest-Chrome-patch-failing-to-deploy-with-error-Download-Success-but-checksum-failed-Error-33b43c23a5e280b9bba6ccf30047a6b7?v=33543c23a5e280578168000c4f61fd3c&source=copy_link](https://www.notion.so/7733556-Latest-Chrome-patch-failing-to-deploy-with-error-Download-Success-but-checksum-failed-Error-33b43c23a5e280b9bba6ccf30047a6b7?v=33543c23a5e280578168000c4f61fd3c)

