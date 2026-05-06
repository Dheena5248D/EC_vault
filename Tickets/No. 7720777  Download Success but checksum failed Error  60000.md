---
notion_id: "33443c23-a5e2-80b4-ab82-c2335bee721e"
notion_last_edited: "2026-03-31T12:27:00.000Z"
tags:
  - "checksum failure"
resolved: "False"
problem tags:
  - "checksum mismatch"
Date: "2026-03-31"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003534432624"
---

**similar Tickets:** [[No. 7699852 Google chrome checksum mismatch]]
**Related back to Tickets:** [[No. 7792112  Download Success but checksum failed Error  60000.]]

# Issue:

"Download Success but checksum failed Error : 60000" when patching multiple applications - Google Chrome, Microsoft Edge, Amazon SSM agent, Amazon EC2 Launch.

Cx already tried to delete the patches from the downloaded patches view and redownload it but still getting the error.

# Analysis:

Simliar ticket: [[No. 7699852 Google chrome checksum mismatch]] 



There is a known issue where checksum type field is empty in the agent so agent hashes the patch binary in md5 and compare it with SHA256 resulting in checksum mismatch

The fix is in development

Workaround for that is :

After deployment is created ask the cx to perform Download Again using the button present in Downloaded Patches view for that patch


# Log traces:

```javascript
Local Computer Name                       -> WSAMZN-OIPTBTG1 
Local Computer IP Address                 -> 192.168.111.218,172.16.10.156 
```



```javascript
[06:08:18:362]|[03-31-2026]|[PatchManagementLogger]|[INFO]|[449]|[166b15e1-9310-469e-8ecc-daaa4ed57331]: updated install patch status with props ::{COMPUTER_NAME=WSAMZN-JKU2I5F7, NEXT_APPLY_TYPE=Refresh/Startup, MSP_NAME=DC_MSP, TOTAL_RETRY_COUNT=2, RESOURCE_ID=39006, OS_PLATFORM=1, UNIQUE_VALUE=EC24404A-3784-A622-024E-78B4D625BB0C, REMARKS_EN=Download Success but checksum failed Error : 60000., COMPUTER_DOMAIN_NAME=innovationspace, CUSTOMER_ID=1, REMARKS=Download Success but checksum failed Error : 60000., APPLY_TYPE=Refresh, DOMAIN_NETBIOS_NAME=innovationspace, PATCH_ID=357434, NAME=WSAMZN-JKU2I5F7, RESOURCE_TYPE=1, ERROR_CODE=-1, STATUS=7, LAST_RETRY_ATTEMPT=0, COLLECTION_ID=6001, AGENT_TIME=1774897697000, IP_ADDRESS=192.168.119.89,172.16.10.23, DOMAIN_TYPE=2}|
```



```javascript
[ 2026-03-31 07:52:31:851 ] [ 9356 ] [INFO] Checksum from file : 088ab4bc8df4e5a5ebf7f8117aaf62ff
[ 2026-03-31 07:52:31:851 ] [ 9356 ] [INFO] Checksum to compare : 34ade9450e8f644959a0f2181793e11137ea601eb3866d2f1893a1c1597c44ee
[ 2026-03-31 07:52:31:851 ] [ 9356 ] [INFO] Checksum does not match.
```

