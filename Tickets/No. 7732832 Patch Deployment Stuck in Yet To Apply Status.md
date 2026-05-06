---
notion_id: "33743c23-a5e2-806c-9c18-ed9175c34a31"
notion_last_edited: "2026-04-05T07:30:00.000Z"
tags:
resolved: "False"
problem tags:
  - "collection struck at ready to execute"
Solved by: "Others"
Date: "2026-04-03"
---

# Issue:



# Analysis:

APD was created at Apr 2, 2026 03:35 PM 

# Log traces:

```sql
DesktopCentral Server Name                -> SPWG-DTCTPRD.spwg.local
DesktopCentral Agent Version              -> 11.4.2500.11.W 
	DesktopCentral Server IPAddress           -> 10.10.1.217
Local Computer Name                       -> ImageWins2019 
Local Computer IP Address                 -> 10.10.21.162 
DC Distribution Server Enabled            -> no 
```

```sql
26-04-02	          Logon	  16:10:58	       16:11:29
26-04-02	        Refresh	  16:17:05	       16:17:32
```

```sql
[ 2026-04-02 16:11:00:856 ] [ 7508 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by client-data/1/domains/workgroup/meta-data.xml 
[ 2026-04-02 16:11:00:856 ] [ 7508 ] [INFO] AgentSendRequest: EnablePocoCommunication is [0] 
[ 2026-04-02 16:11:00:856 ] [ 7508 ] [INFO] InternetGetRequestEx : DesktopCentral Server & Port -> 10.10.1.217 : 8383 
[ 2026-04-02 16:11:00:856 ] [ 7508 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2026-04-02 16:11:00:859 ] [ 7508 ] [INFO] GetInternetRequestHandle :  GET Request 
[ 2026-04-02 16:11:00:859 ] [ 7508 ] [INFO] Inside SetAuthentication 
[ 2026-04-02 16:11:00:871 ] [ 7508 ] [INFO] SetAuthentication: Authenticated successfully 
[ 2026-04-02 16:11:00:871 ] [ 7508 ] [INFO] End of SetAuthentication 
[ 2026-04-02 16:11:00:871 ] [ 7508 ] [INFO] Get request to reporting server
[ 2026-04-02 16:11:00:871 ] [ 7508 ] [INFO] GetSecFlags: Ignoring Certificate check flags added for communication 
[ 2026-04-02 16:11:00:900 ] [ 7508 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2026-04-02 16:11:00:900 ] [ 7508 ] [INFO] GetInternetRequestHandle: Client Certificate set successfullly 
[ 2026-04-02 16:11:15:958 ] [ 7508 ] [INFO] writeValue : Valuename or Valuedata is Empty 
[ 2026-04-02 16:11:15:958 ] [ 7508 ] [INFO] GetInternetRequestHandle : WinHttpQueryHeaders http status code 200 
[ 2026-04-02 16:11:15:958 ] [ 7508 ] [INFO] DeletePrivateKeys: Deleted using a21ad1a1dccf3ea1224e3a0f07160f29f6334b56e6cb08dc7fd3dc85af2e37856fe55e149f0067d517760af9f7c8e114 KeyContainer from Microsoft Software Key Storage Provider
[ 2026-04-02 16:11:15:958 ] [ 7508 ] [ERROR] Response Header doesn't contain Content-Encoding. 
[ 2026-04-02 16:11:15:958 ] [ 7508 ] [INFO] InternetGetRequestEx : Content Length of the request file: 12000 Bytes
[ 2026-04-02 16:11:15:958 ] [ 7508 ] [INFO] CreateFolder : The Directory to create is C:\Program Files (x86)\ManageEngine\UEMS_Agent\data\ 
[ 2026-04-02 16:11:15:958 ] [ 7508 ] [INFO] Bytes read reached the contenlength
[ 2026-04-02 16:11:15:958 ] [ 7508 ] [INFO] InternetGetRequestEx : Total Time Taken for download : 0.000 seconds
[ 2026-04-02 16:11:15:974 ] [ 7508 ] [INFO] InternetGetRequestEx : Total bytes read = 12000
[ 2026-04-02 16:11:15:974 ] [ 7508 ] [INFO] InternetGetRequestEx : GetFileSize returns :  12000
[ 2026-04-02 16:11:15:974 ] [ 7508 ] [INFO] InternetGetRequestEx : File completely downloaded..!
[ 2026-04-02 16:11:15:974 ] [ 7508 ] [INFO] InternetGetRequestEx : Successfully downloaded the file client-data/1/domains/workgroup/meta-data.xml?agentResourceIdentifier=58228&ResourceID=58228&uniqueValue=VMware-42%2002%207e%20cd%205c%204a%204d%2011-a0%2063%20ca%20eb%209b%20f1%20fd%2096 from the server 10.10.1.217 to the destination file C:\Program Files (x86)\ManageEngine\UEMS_Agent\data\meta-data.xml 
[ 2026-04-02 16:11:15:974 ] [ 7508 ] [INFO] Successfully updated ecdatatransfer_access.log
[ 2026-04-02 16:11:15:974 ] [ 7508 ] [INFO] Message : The operation completed successfully.  
```

```sql
[ 2026-04-02 16:17:05:931 ] [ 6608 ] [INFO] AgentSendRequest : The url to get / send in UTF8 format is given by client-data/1/domains/workgroup/meta-data.xml 
[ 2026-04-02 16:17:05:931 ] [ 6608 ] [INFO] AgentSendRequest: EnablePocoCommunication is [0] 
[ 2026-04-02 16:17:05:931 ] [ 6608 ] [INFO] InternetGetRequestEx : DesktopCentral Server & Port -> 10.10.1.217 : 8383 
[ 2026-04-02 16:17:05:931 ] [ 6608 ] [INFO] @@@@@@@@ Inside GetInternetRequestHandle Method @@@@@@@@ 
[ 2026-04-02 16:17:05:934 ] [ 6608 ] [INFO] GetInternetRequestHandle :  GET Request 
[ 2026-04-02 16:17:05:934 ] [ 6608 ] [INFO] Inside SetAuthentication 
[ 2026-04-02 16:17:05:946 ] [ 6608 ] [INFO] SetAuthentication: Authenticated successfully 
[ 2026-04-02 16:17:05:946 ] [ 6608 ] [INFO] End of SetAuthentication 
[ 2026-04-02 16:17:05:946 ] [ 6608 ] [INFO] Get request to reporting server
[ 2026-04-02 16:17:05:946 ] [ 6608 ] [INFO] GetSecFlags: Ignoring Certificate check flags added for communication 
[ 2026-04-02 16:17:05:971 ] [ 6608 ] [INFO] SetClientCertificateEx: Client Certificate set successfully 
[ 2026-04-02 16:17:05:971 ] [ 6608 ] [INFO] GetInternetRequestHandle: Client Certificate set successfullly 
[ 2026-04-02 16:17:06:060 ] [ 6608 ] [INFO] writeValue : Valuename or Valuedata is Empty 
[ 2026-04-02 16:17:06:060 ] [ 6608 ] [INFO] GetInternetRequestHandle : WinHttpQueryHeaders http status code 304 
[ 2026-04-02 16:17:06:070 ] [ 6608 ] [INFO] DeletePrivateKeys: Deleted using ac6a1deb2bfa5c661cd7536f165216c0b63ba7af70ff4fc52422ae22d865c4b07ef702a9f89c24052b25dd603055ba1e KeyContainer from Microsoft Software Key Storage Provider
[ 2026-04-02 16:17:06:070 ] [ 6608 ] [ERROR] Response Header doesn't contain Content-Encoding. 
[ 2026-04-02 16:17:06:070 ] [ 6608 ] [INFO] InternetGetRequestEx :File not modified since the time: Thu, 02 Apr 2026 08:56:19 GMT
[ 2026-04-02 16:17:06:070 ] [ 6608 ] [INFO] Successfully updated ecdatatransfer_access.log
[ 2026-04-02 16:17:06:071 ] [ 6608 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-02 16:17:06:071 ] [ 6608 ] [INFO] AgentSendRequest : Last Access Address is 10.10.1.217 
[ 2026-04-02 16:17:06:071 ] [ 6608 ] [INFO] Message : The operation completed successfully.  
[ 2026-04-02 16:17:06:071 ] [ 6608 ] [INFO]  @@@@@@@@@@@@ End of InternetDownloadFileIfmodifiedSince method @@@@@@@@@@@@@
[ 2026-04-02 16:17:06:071 ] [ 6608 ] [ERROR] DownLoadMetaData : Failed to download the metadata.xml error code 90001 
[ 2026-04-02 16:17:06:071 ] [ 6608 ] [INFO] DownLoadMetaData: meta-data downloaded successfully.
```

```sql
26/04/02:16:17:22,dcconfig.exe,6608,Refresh,GET,10.10.1.217,8383,58228,client-data/1/customer-meta-data.json?agentResourceIdentifier=58228&ResourceID=58228&uniqueValue=VMware-42%2002%207e%20cd%205c%204a%204d%2011-a0%2063%20ca%20eb%209b%20f1%20fd%2096,6383,6383,0,C:\Program Files (x86)\ManageEngine\UEMS_Agent\\data\customer-meta-data.json
```

