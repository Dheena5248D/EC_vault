---
notion_id: "33443c23-a5e2-80a6-81a5-fcb98000d41e"
notion_last_edited: "2026-03-31T12:30:00.000Z"
tags:
  - "checksum failure"
resolved: "False"
problem tags:
  - "checksum mismatch"
Date: "2026-03-31"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003453762437"
---

**Related back to Tickets:** [[No. 7792112  Download Success but checksum failed Error  60000.]]

# Issue:

While downloading the patch in server checksum mismatch occurred 

# Analysis:

Need server logs to analyze further 

# Log traces:

```javascript
[ 2026-03-30 10:22:52:479 ] [ 13480 ] [INFO] Destination Path : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\40378-windows11.0-kb5043080-x64_953449672073f8fb99badb4cc6d5d7849b9c83e8.msu
[ 2026-03-30 10:22:52:481 ] [ 13480 ] [INFO] RegChecksumFromDB : 819632610A101AF11C72907FB13FF05B5FB4222C0E263EE9A03BCC1D1D5F26A4 ChecksumFromDB : 819632610A101AF11C72907FB13FF05B5FB4222C0E263EE9A03BCC1D1D5F26A4 are same and retry expired. Not proceeding to download.
```

