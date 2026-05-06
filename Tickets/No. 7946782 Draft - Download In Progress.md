---
notion_id: "35243c23-a5e2-8099-8a02-ce393231eb04"
notion_last_edited: "2026-04-30T13:38:00.000Z"
tags:
resolved: "False"
problem tags:
  - "aaapatchdownloadfix silentfix not removed issue"
Solved by: "ME"
Date: "2026-04-30"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003642575813"
---

# Issue:

User reports that patch task Is stuck In yet to apply and draft download status

Patch Is available In the downloaded patches view

# Analysis:

From the log trace we have found out that during upgrade to later builds an unwanted jar AAAPatchDownloadFix.jar was not removed during upgrade.

Please ask the cx to remove the AAAPatchDownloadFix.jar carefully from the <server-home>/lib folder and restart the server to resolve the issue.

Kindly ask the Cx to make sure :

1. the jar AAAPatchDownloadFix.jar is deleted.

2. The server is restarted properly

3. Attempt download for the patches

4. If the patch is shown as Yet to Download in UI ask to check in Downloaded Patches view.

If the patch download is not success (or) The UI always showing Yet to Download ask the cx to share the latest server logs

# Log traces:



