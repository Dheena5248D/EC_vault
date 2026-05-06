---
Status: "Done"
tags:
problem tags:
Solved by: "ME"
Date: "2026-04-14"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003574416384"
---

# Issue:

Query regarding all the windows 11 machines patch scan failed with remarks: Scanning Failed (drvforceupdate.exe.gz download failed due to checksum mismatch error. Contact support)

# Analysis:

On analysisng the log the drvforceupdate.exe.gz checksum mismatch happens after the server upgrade

but the server log dosn't have latest logs like crslog0, serverout0, seems like the customer uploaded the logs directly from the logs folder. so the logs that are being written is not uploaded

kindly ask the the customer to copy and past logs at another folder and ask them to upload the server logs for furthur analysis

# Log traces:

```prolog
26-04-02      APD           18:53:10      11.4.2522.03.W    YES           YES           4201          Vulnerability Manager Plus / ONPREMLocal Office / no                        0             0             YES/8/18             18:57:12      4.04          DiffScan      Successfully posted the patch scan data to the server
26-04-07      DBSYNC        07:46:28      11.5.2605.13.W    YES           YES           4201          Vulnerability Manager Plus / ONPREMLocal Office / no                        0             0             YES/8/18             07:46:30      0.04          FullScan      Problem while loading Patch Resource XML. 

26-04-07	07:45:56	4201	UPGRADE	11.5.2605.13.W	SUCCESS
26-04-07	07:46:23	4201	INSTALL_POST	11.5.2605.13.W	SUCCESS
26-04-09	16:37:02	4201	INSTALL_POST	11.5.2605.13.W	SUCCESS

26/04/07:07:46:30,dcpatchscan.exe,2196,-,POST,192.168.255.232,8383,4201,/patchscan?actionToCall=error&computerName=DELTA-NB005&domainName=DELTADOMAIN&domainType=2&scanMode=1&scanType=DBSYNC&remarks=[i18n]dc.patch.configremarks.xml.checksummismatch@@@drvforceupdate.exe.gz[/i18n]&errorCode=5107&agentResourceIdentifier=4201&osPlatform=1&ResourceID=4201&uniqueValue=5CG60802BF,0,80,0.000,0,-
```



