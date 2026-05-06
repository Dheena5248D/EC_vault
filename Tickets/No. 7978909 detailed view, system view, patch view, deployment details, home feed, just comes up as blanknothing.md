---
notion_id: "35743c23-a5e2-80b9-86c0-f179a07e44bf"
notion_last_edited: "2026-05-05T12:04:00.000Z"
tags:
resolved: "False"
problem tags:
Date: "2026-05-05"
Learning priority: "medium"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003655662320"
---

# Issue:

After updating to Build : 11.5.2613.09 - cannot view detailed view, system view, patch view, deployment details, home feed, just comes up as blank/nothing.

# Analysis:

The customer is facing an issue while accessing the views after upgrading the server.



[zz Arul Pandian](https://medcsupport.zohodesk.com/agent/medcsupport/all/setup#setup/users-control/agents/220709003339524701) and [Rathinavel Pandian Ravi](https://medcsupport.zohodesk.com/agent/medcsupport/all/setup#setup/users-control/agents/220709001214677943), kindly check this ticket.

# Log traces:

```sql
api-audit-log0.txt
[16:38:59:509]|[05-04-2026]|[dcRestAPILogger]|[INFO]|[49968]|[
ac332eda-6c1a-4f51-a6e9-2fe2eaea1cc8
]: 500 | GET | https://srv-pm01.ad.lgfa.com.au:8383/dcapi/summary_2_0/cards | 1,003 | Exception while forming response getDashboardCards[Ljava.lang.StackTraceElement;@20351ca|
securityfilter0.log:
[16:38:59:494]|[05-04-2026]|[com.adventnet.iam.security.SecurityUtil]|[WARNING]|[49968]|[
ac332eda-6c1a-4f51-a6e9-2fe2eaea1cc8
]: null|
java.lang.IllegalStateException: java.io.IOException: java.lang.reflect.InvocationTargetException
at org.apache.catalina.webresources.AbstractSingleArchiveResourceSet.getArchiveEntry(AbstractSingleArchiveResourceSet.java:100)
at org.apache.catalina.webresources.AbstractArchiveResourceSet.getResource(AbstractArchiveResourceSet.java:255)
at org.apache.catalina.webresources.StandardRoot.getResourcesInternal(StandardRoot.java:317)
at org.apache.catalina.webresources.CachedResource.validateResources(CachedResource.java:159)
 serverout0.txt:
[16:38:59:384]|[05-04-2026]|[com.me.dc.common.api.utils.AuthorizationUtil]|[INFO]|[49968]|[
ac332eda-6c1a-4f51-a6e9-2fe2eaea1cc8
]: Inside the getParameters method of AuthorizationUtil|
12599
[16:38:59:494]|[05-04-2026]|[com.me.uems.dashboard.core.handler.UEMSDashboardHandler]|[INFO]|[49968]|[
ac332eda-6c1a-4f51-a6e9-2fe2eaea1cc8
]: Fetch the zoho chart graph data for the card: windows10_systems_by_version |
12600
[16:38:59:494]|[05-04-2026]|[com.me.uems.dashboard.core.handler.UEMSDashboardHandler]|[INFO]|[49968]|[
ac332eda-6c1a-4f51-a6e9-2fe2eaea1cc8
]: windows10_systems_by_version properties:: {viewName=windows10_systems_by_version, dashboardId=1, showFilter=false, cardId=8, selectedViewName=windows10_systems_by_version, isResourceDashboard=false, isCardFilterApplied=false}|
12605
12706
[16:38:59:494]|[05-04-2026]|[com.me.devicemanagement.framework.webclient.zohoCharts.ZohoChartJSONGeneratorImpl]|[SEVERE]|[49968]|[
ac332eda-6c1a-4f51-a6e9-2fe2eaea1cc8
]: Exception in ZohoChartJSONGeneratorImpl-constructChartData|
java.lang.NullPointerException
 at org.apache.catalina.webresources.Cache.getResources(Cache.java:160)
at org.apache.catalina.webresources.StandardRoot.getResources(StandardRoot.java:306)
```

