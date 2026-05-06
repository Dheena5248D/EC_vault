---
ticket_id: "#7803598"
status: "Done"
date: "2026-04-13"
url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003576089978"
solved_by: "ME"
---

# Issue:
Manual Deployment task is in Draft Download in progress even though patches are downloaded

# Analysis:
The patches are downloaded but still the collection in draft- download in progress

On analysing the log and the pdf the collection "SIEMSRV" was created at april 11 but the server logs only extend until **April 9**

Kindly collect latest server logs to analyse further:

# Log traces:
```prolog
build.number=114252821

[15:03:57:053]|[04-09-2026]|[PatchDownloadManagerLogger]|[INFO]|[768]|[c69532a5-953f-43a5-989a-12061e52f625]: Deployment initiated for collection id : 29,451|
[15:03:57:053]|[04-09-2026]|[PatchDownloadManagerLogger]|[INFO]|[768]|[c69532a5-953f-43a5-989a-12061e52f625]: Processing Completed for : 43574.txt|
```
