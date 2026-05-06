---
notion_id: "34443c23-a5e2-80a5-a236-fede002c239c"
notion_last_edited: "2026-04-16T14:29:00.000Z"
tags:
resolved: "False"
problem tags:
Date: "2026-04-16"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003515801929"
---

# Issue:

**Test & Approve** feature, where CX reported that a specific patch is not getting approved and is not deploying to the production servers/endpoints.

# Analysis:



# Log traces:

```prolog
26-04-11      DBSYNC        11:38:10      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             12:09:42      31.54         DiffScan      Successfully posted the patch scan data to the server
26-04-11      AvOnlyAPD     20:38:03      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             20:40:04      2.01          DiffScan      Successfully posted the patch scan data to the server
26-04-11      AvOnlyAPD     22:08:02      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             22:09:55      1.87          DiffScan      Successfully posted the patch scan data to the server
26-04-11      AvOnlyAPD     23:37:59      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             23:39:37      1.64          DiffScan      Successfully posted the patch scan data to the server
26-04-12      AvOnlyAPD     05:37:58      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             05:39:47      1.82          DiffScan      Successfully posted the patch scan data to the server
26-04-12      AvOnlyAPD     10:07:58      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             10:09:46      1.81          DiffScan      Successfully posted the patch scan data to the server
26-04-12      AvOnlyAPD     11:37:58      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             11:39:36      1.63          DiffScan      Successfully posted the patch scan data to the server
26-04-13      TestGroup     11:38:15      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             12:09:35      31.32         DiffScan      Successfully posted the patch scan data to the server
26-04-13      AvOnlyAPD     14:37:56      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             14:39:47      1.85          DiffScan      Successfully posted the patch scan data to the server
26-04-13      AvOnlyAPD     17:38:01      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             17:39:57      1.94          DiffScan      Successfully posted the patch scan data to the server
26-04-13      AvOnlyAPD     19:07:56      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             19:09:46      1.83          DiffScan      Successfully posted the patch scan data to the server
26-04-13      AvOnlyAPD     23:37:55      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             23:39:47      1.86          DiffScan      Successfully posted the patch scan data to the server
26-04-14      AvOnlyAPD     01:08:34      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             01:10:33      1.98          DiffScan      Successfully posted the patch scan data to the server
26-04-14      AvOnlyAPD     05:37:55      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             05:39:46      1.85          DiffScan      Successfully posted the patch scan data to the server
26-04-14      AvOnlyAPD     10:07:54      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             10:09:45      1.85          DiffScan      Successfully posted the patch scan data to the server
26-04-14      DBSYNC        11:38:05      11.3.2416.20.W    NO            YES           11716         Endpoint Central / ONPREM     Local Office / no                        0             0             YES/2/22             12:08:53      30.79         DiffScan      Successfully posted the patch scan data to the server
```



