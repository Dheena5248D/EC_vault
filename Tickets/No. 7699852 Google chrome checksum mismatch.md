---
notion_id: "32f43c23-a5e2-802a-b9f4-ec292e66150f"
notion_last_edited: "2026-03-31T05:58:00.000Z"
tags:
  - "checksum failure"
  - "patch download"
resolved: "False"
problem tags:
  - "checksum mismatch"
Date: "2026-03-26"
---

**Related back to Tickets:** [[No. 7720777  Download Success but checksum failed Error  60000]], [[No. 7792112  Download Success but checksum failed Error  60000.]]

# Issue:

Cx reported that download of Google chrome checksum mismatch 60000

# Analysis:

There is similar ticket: #7700177



There is a known issue in the Cx build where it dosn’t consider checksum type and generates the checksum in md5 and compare the hash with sha256 so this checksum mismatch error occurs.

The fix is being under development

# Log traces:

```javascript
Local Computer Name                       -> DE470580C00037
DesktopCentral Agent Version              -> 11.5.2605.09.W 
```

```javascript
[ 2026-03-24 11:26:34:258 ] [ 18028 ] [INFO] PostDownloadHandling : Successfully downloaded the file /store/357325-googlechromestandaloneenterprise.msi?agentResourceIdentifier=639&ResourceID=639&uniqueValue=YMJR008906 from the server 10.59.148.32 to the destination file C:\Program Files (x86)\ManageEngine\UEMS_Agent\patches\357325-googlechromestandaloneenterprise.msi 
[ 2026-03-24 11:26:34:258 ] [ 18028 ] [INFO] Successfully updated ecdatatransfer_access.log
[ 2026-03-24 11:26:34:258 ] [ 18028 ] [INFO] InternetGetDownloader : ResumeGetRequestEx errorCode = 0 
[ 2026-03-24 11:26:34:258 ] [ 18028 ] [ERROR] deleteValue:  Software\AdventNet\DesktopCentral\DCAgent\FileMetaData\17743479911769618028.download Key not found!: 2  
[ 2026-03-24 11:26:34:258 ] [ 18028 ] [ERROR]  Error Message: Eine Datei kann nicht erstellt werden, wenn sie bereits vorhanden ist.


[ 2026-03-24 11:26:34:258 ] [ 18028 ] [INFO] Message : Der Vorgang wurde erfolgreich beendet.  
[ 2026-03-24 11:26:34:258 ] [ 18028 ] [INFO] AgentSendRequest : Updating key inside main send request
[ 2026-03-24 11:26:34:258 ] [ 18028 ] [INFO] Message : Der Vorgang wurde erfolgreich beendet.  
[ 2026-03-24 11:26:34:960 ] [ 18028 ] [INFO] Checksum from file : b9418db9e63401f13a956ef5ff4fa8ca
[ 2026-03-24 11:26:34:960 ] [ 18028 ] [INFO] Checksum to compare : 5f44625f8202a668efdddd00a25e8303d100883f8428fb52c5dc35baab7d8616
```

```javascript
Algorithm Hash
--------- ----
MD5       B9418DB9E63401F13A956EF5FF4FA8CA
SHA1      C6D40EB4784750A9352FAB84160E01714F736B9E
SHA256    5F44625F8202A668EFDDDD00A25E8303D1008...
SHA384    2607C24DE10D91E638A7302660FF42AFD1964...
SHA512    A7CA6CA78FABF236B379506E0898797CC2B5F..
```



