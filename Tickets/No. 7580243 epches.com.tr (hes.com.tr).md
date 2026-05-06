---
notion_id: "32443c23-a5e2-8026-b636-ecda63b494ba"
notion_last_edited: "2026-03-16T12:40:00.000Z"
tags:
  - "patch clean up"
  - "patch-deployment"
resolved: "False"
problem tags:
  - "patch not deleted from the agent after deployment"
Date: "2026-03-16"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003432135637"
---

# Problem:

After successful deployment the agent didn’t deleted the  patch 43387  binary from the agent



# Analysis:

The patch was first installed on 26/02/24  09:41:28 and in status of reboot pending and deleted on 09:52:41 but the pc dosn’t restarted after and the patch is still missing and after the collection is processed again and the patch is downloaded again on 02/03/2026 14:17:42 



# Log analysis:

```javascript
Local Computer Name                       -> hes-tiger 
Local Computer IP Address                 -> 10.1.200.11 
DC Distribution Server Enabled            -> no 
```



```javascript
[ 2026-02-24 09:52:41:936 ] [ 29020 ] [INFO] Successfully deleted file : C:\Program Files (x86)\ManageEngine\UEMS_Agent\\patches\43387-windows10.0-kb5075906-x64-2022.msu
```



```javascript
[ 2026-03-02 14:17:42:010 ] [ 35484 ] [INFO] Successfully downloaded the patch 43387-windows10.0-kb5075906-x64-2022.msu.
```

