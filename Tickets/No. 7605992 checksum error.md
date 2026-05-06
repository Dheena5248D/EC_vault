---
notion_id: "32743c23-a5e2-803a-91ea-dd553ca8c45f"
notion_last_edited: "2026-03-26T13:42:00.000Z"
tags:
  - "patch-deployment"
  - "checksum failure"
resolved: "False"
problem tags:
Date: "2026-03-18"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003461338342"
---

**Related back to Tickets:** [[No. 7792112  Download Success but checksum failed Error  60000.]]





# Analysis

 Due to the missing checksum type in the XML, the agent is unable to properly validate the downloaded file, leading to the checksum failure.



# Log trace

```javascript
[ 2026-03-17 07:24:12:082 ] [ 17640 ] [INFO] Checksum from file : 837b16d0821951d5c0348e2a5385eea0
[ 2026-03-17 07:24:12:082 ] [ 17640 ] [INFO] Checksum to compare : 0b1f7a379720bd7415e281ba112b584413f6de34033fc25347dc22f27b1f8ac8
[ 2026-03-17 07:24:12:082 ] [ 17640 ] [INFO] Download succeeded but checksum failed.
[ 2026-03-17 11:46:32:953 ] [ 7456 ] [INFO] RegChecksumFromDB : 0b1f7a379720bd7415e281ba112b584413f6de34033fc25347dc22f27b1f8ac8 ChecksumFromDB : 0b1f7a379720bd7415e281ba112b584413f6de34033fc25347dc22f27b1f8ac8 are same and retry expired. Not proceeding to download.
```



```javascript
26-03-17	902	APD Daily 10pm	357039	11:46:32	11:46:32	60000	Download Success but checksum failed Error : 60000.
```



```javascript
26-03-17	Refresh	  Computer	    SYSTEM	          APD Deploy	                APD Daily 10pm	902	      SCHEDULED_SKIP	  11:46:07	    2	  11:46:36DC_FORCE_REBOOT_IMMEDIATE(skppd)     CONFIGURATION_STAGED	   --
```

