---
notion_id: "32d43c23-a5e2-8047-a92f-dc16f965d1ae"
notion_last_edited: "2026-03-24T16:07:00.000Z"
tags:
  - "file download failed"
resolved: "False"
problem tags:
Date: "2026-03-24"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003489266508"
---

# Issue:

 Downloading ud-supported-patch-details.json.gz failed with error code: 1

# Analysis:

On analysing the logs the file is successfully downloaded on the system but when the agent tries to unzip the file using 7za it returned  The system cannot find the file specified. 
we may need the client-data folder for further analyis

it is suspected that the av is deleting the file right after download

# Log traces:

```prolog

[ 2026-03-16 15:06:49:088 ] [ 11428 ] [ERROR] Error Code : 2 , Error Message : The system cannot find the file specified.  
[ 2026-03-16 15:06:48:753 ] [ 11428 ] [INFO] protocol is https	Path is /dc-crs/definitiondata/1.11/patchscan/1.254/ud-supported-patch-details.json.gz
[ 2026-03-16 15:06:49:009 ] [ 11428 ] [INFO] End of ExternalDCDownloadHanlder::DownloadFile method[ 2026-03-16 15:06:49:009 ] [ 11428 ] [INFO] downloadXMLGZ : Download of Gzip file https://patchdb.manageengine.com/dc-crs/definitiondata/1.11/patchscan/1.254/ud-supported-patch-details.json.gz success
[ 2026-03-16 15:06:49:025 ] [ 11428 ] [INFO] execute : Process successfully created for application "C:\Program Files (x86)\ManageEngine\UEMS_Agent\\bin\7za.exe" x -y "C:\Program Files (x86)\ManageEngine\UEMS_Agent\\\client-data\patch-resources\ud-supported-patch-details.json.gz" * 
```



