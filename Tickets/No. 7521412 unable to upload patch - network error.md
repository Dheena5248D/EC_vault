---
notion_id: "32043c23-a5e2-8068-9941-d461eba75788"
notion_last_edited: "2026-03-19T10:05:00.000Z"
tags:
  - "patch-deployment"
  - "upload patch"
resolved: "False"
problem tags:
  - "network error while uploading a patch"
Date: "2026-03-12"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003383218380"
---

**Related back to Tickets:** [[No. 7701991 112733 dependency patch ID upload error - Network Error]]

# Problem:

Cx is trying to upload a iso for manual upload patch required patch but it results in network error



# Analysis



The dev confirms that it is a known issue

build: 115260019

<u>***Analysis: ***</u>The issue the cx is facing is a known issue where uploading a patch greater than 3GB might cause Network Error displayed

<u>***Workaround:***</u> Please ask the cx to access the server using port 8443, while uploading such patches.

## Server

In server the patch is uploaded and also a antivirus scan is skipped due its exceeding file size

```javascript
[18:17:50:958]|[02-12-2026]|[emsRestAPILogger]|[INFO]|[371]|[35da989c-e649-47b7-a695-fd4d3651a3a6]: 200 | POST | http://172.18.0.80/emsapi/files|
```

```javascript
[18:00:55:327]|[02-12-2026]|[com.adventnet.iam.security.SecurityRequestWrapper]|[WARNING]|[371]|[SERVER-4fd82f5d-7572-41d2-b467-4b146b47f97e]: anti-virus check has been skipped due to the file size exceeded the configured av-threshold value 300 MB and the file [26200.6584.250915-1905.25h2_ge_release_svc_refresh_CLIENT_BUSINESS_VOL_x64FRE_pt-br.iso] size is 7011 MB|
```





In har log:



The har log sends the file in post to the server but there is no response from the server 



