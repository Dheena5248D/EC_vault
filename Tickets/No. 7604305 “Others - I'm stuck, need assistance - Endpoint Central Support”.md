---
notion_id: "32243c23-a5e2-80e8-8ee7-ef9f8ba875c4"
notion_last_edited: "2026-04-22T12:45:00.000Z"
tags:
  - "server-upgrade"
resolved: "False"
problem tags:
  - "post server-upgrade"
Solved by: "Others"
Date: "2026-03-13"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003455521391"
---

# Problem:

as the user reported that after performing the server upgrade earlier, all patches disappeared from the console. The customer attempted to revert the environment using a snapshot and then performed the upgrade again, but the same behavior occurred. 



# analysis:

After the server upgrade, the server attempted to synchronize patch metadata and download required CRS definition files are not available so trying to get from the internet. Since the environment appears to be configured as a closed network, the server was unable to reach the external source to download the required metadata files. As a result, the DB sync process failed.

To resolve this, kindly ask the customer to initiate the DB Sync process for a closed network environment and verify whether the patch data gets populated successfully after the sync.

If the issue persists even after perf

# Log traces:

```prolog
[13:04:04:922]|[03-12-2026]|[CRSLogger]|[INFO]|[300]|[SERVER-e90b1fa0-7136-438e-b066-a85c59df3bc9]: Going to updateCRSVersionForModules|
[13:04:04:926]|[03-12-2026]|[CRSLogger]|[INFO]|[300]|[SERVER-e90b1fa0-7136-438e-b066-a85c59df3bc9]: XML File download failed for the path : ..\conf\CRSData\updatedb\dc-crs\definitiondata\1.11\\windows-details.xml and Download status : 10,008|
[13:04:04:926]|[03-12-2026]|[CRSLogger]|[SEVERE]|[300]|[SERVER-e90b1fa0-7136-438e-b066-a85c59df3bc9]: Error while downloading files| 
java.lang.Exception: XML file failed to download: ..\conf\CRSData\updatedb\dc-crs\definitiondata\1.11\\windows-details.xml, and download status : 10008
	at com.me.uems.patch_mgmt.sync.crs.DBSyncDownloadUtil.downloadAllRequiredFiles(DBSyncDownloadUtil.java:301)
	at com.me.uems.patch_mgmt.sync.crs.DBSyncDownloadUtil.downloadAllRequiredFiles(DBSyncDownloadUtil.java:122)
	at com.me.uems.patch_mgmt.sync.task.StaticDBSyncTask.performStaticSync(StaticDBSyncTask.java:336)
	at com.me.uems.patch_mgmt.sync.task.PatchDBSyncTaskImpl.syncPatchDB(PatchDBSyncTaskImpl.java:41)
	at com.me.uems.patch_mgmt.sync.task.UpdateDBTask.executeTask(UpdateDBTask.java:26)
	at com.me.devicemanagement.onpremise.server.scheduler.SchedulerExecutionTask.invokeMethodInClass(SchedulerExecutionTask.java:91)
	at com.me.devicemanagement.onpremise.server.scheduler.SchedulerExecutionTask.executeTask(SchedulerExecutionTask.java:77)
	at com.adventnet.taskengine.internal.SchedulerBean.executeTask(SchedulerBean.java:698)
	at jdk.internal.reflect.GeneratedMethodAccessor17.invoke(Unknown Source)
	at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.base/java.lang.reflect.Method.invoke(Method.java:566)
	at com.adventnet.mfw.bean.BeanProxy.lambda$invoke$0(BeanProxy.java:51)
	at com.zoho.mickey.api.DefaultCodeBlock.execute(CodeBlock.java:453)
	at com.adventnet.mfw.bean.BeanProxy.invoke(BeanProxy.java:48)
	at com.sun.proxy.$Proxy8.executeTask(Unknown Source)
	at com.adventnet.taskengine.internal.ScheduleExecutor.executeNextTask(ScheduleExecutor.java:334)
	at com.adventnet.taskengine.internal.ScheduleExecutor.run(ScheduleExecutor.java:225)
	at java.base/java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:515)
	at java.base/java.util.concurrent.FutureTask.run(FutureTask.java:264)
	at java.base/java.util.concurrent.ScheduledThreadPoolExecutor$ScheduledFutureTask.run(ScheduledThreadPoolExecutor.java:304)
	at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)
	at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)
	at java.base/java.lang.Thread.run(Thread.java:829)

[13:04:04:929]|[03-12-2026]|[CRSLogger]|[INFO]|[300]|[SERVER-e90b1fa0-7136-438e-b066-a85c59df3bc9]: Download Failed, Retry count exceeds, stopping the db sync process|
```

