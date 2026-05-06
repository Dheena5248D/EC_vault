---
notion_id: "33543c23-a5e2-80a3-98ff-ec9fc202d232"
notion_last_edited: "2026-04-02T07:45:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "Others"
Date: "2026-04-01"
---

# Issue:

Patch deployment failure with: Communication error

Verified in logs, it seems application.xml failed to load. Need to check the following

1. Why are the troubleshooter and console showing different versions

2. need to check why troubleshooter in deployment shows communciation issue

3. need to check actual issue

# Analysis:



# Log traces:

```sql
DesktopCentral Agent Version              -> 11.4.2522.10.W
Local Computer Name                       -> HLP2 
Local Computer IP Address                 -> 192.168.1.149
 DC Distribution Server Enabled            -> no 
```

```sql
26-03-31	08:57:36		OndemandAgentUpgrad	
```

```sql
[ 2026-03-31 08:57:47:927 ] [ 10140 ] [INFO] isAgentUpgradeRequired: Agentupgader commandline arguments: AgentUpgrader.exe 11.5.2605.11.W 2e17f1a9c2f8de25892c887822b1227329db1bc998042839ff10b15e71793a2b
[ 2026-03-31 08:57:47:927 ] [ 10140 ] [INFO] executeFileEx : Current Working Directory : C:\Program Files (x86)\ManageEngine\UEMS_Agent 
[ 2026-03-31 08:57:47:927 ] [ 10140 ] [INFO] executeFileEx : Executing Application Source : AgentUpgrader.exe 11.5.2605.11.W 2e17f1a9c2f8de25892c887822b1227329db1bc998042839ff10b15e71793a2b 
[ 2026-03-31 08:57:47:927 ] [ 10140 ] [INFO] executeFileEx : Set Working Directory : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\Updates\ 
[ 2026-03-31 08:57:47:943 ] [ 10140 ] [INFO] execute : Process successfully created for application AgentUpgrader.exe 11.5.2605.11.W 2e17f1a9c2f8de25892c887822b1227329db1bc998042839ff10b15e71793a2b 
[ 2026-03-31 08:57:47:943 ] [ 10140 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-31 08:57:47:943 ] [ 10140 ] [INFO] executeFileEx : Remarks from the CreateProcess is The operation completed successfully.  for the executable AgentUpgrader.exe 11.5.2605.11.W 2e17f1a9c2f8de25892c887822b1227329db1bc998042839ff10b15e71793a2b 
[ 2026-03-31 08:57:47:943 ] [ 10140 ] [ERROR] main : MDM Profile Enrollment skipped due to DCP or Server OS is detected.
```

```sql
[ 2026-03-31 08:57:56:836 ] [ 10140 ] [INFO] executeFileEx : Remarks from the CreateProcess is The operation completed successfully.  for the executable "C:\Program Files (x86)\ManageEngine\UEMS_Agent\\bin\7za.exe" x -y "C:\Program Files (x86)\ManageEngine\UEMS_Agent\\client-data\patch-resources\applications.xml.gz" * 
[ 2026-03-31 08:57:56:836 ] [ 10140 ] [INFO] [ExtractFiles] => Successfully extracted the file: * from the zip C:\Program Files (x86)\ManageEngine\UEMS_Agent\\client-data\patch-resources\applications.xml.gz
[ 2026-03-31 08:57:56:836 ] [ 10140 ] [INFO] operation : extract; file : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\client-data\patch-resources\applications.xml.gz; dest_path : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\client-data\patch-resources; status : success;
[ 2026-03-31 08:57:56:836 ] [ 10140 ] [INFO] downloadXMLGZ : extractXML is returning with status: 0
[ 2026-03-31 08:57:56:836 ] [ 10140 ] [INFO] ValidateAndGetFileChecksum : Checksum value to compare : 73eef20dc1556db5d52418323f46cc9627eda7c0a405743958d1c3cf7c783de4
[ 2026-03-31 08:57:56:836 ] [ 10140 ] [INFO] ValidateAndGetFileChecksum : Checksum value from file : 73eef20dc1556db5d52418323f46cc9627eda7c0a405743958d1c3cf7c783de4
[ 2026-03-31 08:57:56:836 ] [ 10140 ] [INFO] Message : The operation completed successfully.  
[ 2026-03-31 08:58:05:284 ] [ 10140 ] [ERROR] Cannot create and add a new row while constructing tabledata from XML file.
[ 2026-03-31 08:58:05:284 ] [ 10140 ] [ERROR] Cannot construct table data from XML file.
[ 2026-03-31 08:58:05:481 ] [ 10140 ] [ERROR] [WriteToFileA] => Wrote 8779537 bytes to C:\Program Files (x86)\ManageEngine\UEMS_Agent\\logs\dcParseFailure.log successfully.
[ 2026-03-31 08:58:05:481 ] [ 10140 ] [ERROR] loadXML : Failed to load the data resources from xml buffer C:\Program Files (x86)\ManageEngine\UEMS_Agent\\client-data\patch-resources\applications.xml
[ 2026-03-31 08:58:05:481 ] [ 10140 ] [ERROR] Failed to load applications.xml
```

```sql
26-03-31	08:58:05	6002	1774943885	7	[i18n]dc.patch.configremarks.xml.loadfailure@@@applications.xml[/i18n]	Failed to load applications.xml
```



