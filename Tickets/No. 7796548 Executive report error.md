---
notion_id: "34543c23-a5e2-8044-8dfb-ec149e8d4f6d"
notion_last_edited: "2026-04-17T10:18:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "ME"
Date: "2026-04-17"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003571952722"
---

# Issue:

Report generation failure

# Analysis:

There is a Known issue that throws an execption in image generation

Kindly suggest 2613.05 build upgrade,

[https://www.manageengine.com/patch-management/service-packs1.html](https://www.manageengine.com/patch-management/service-packs1.html)

# Log traces:



`build.number=115260601`

[19:12:43:148]|[04-14-2026]|[dcRestAPILogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: 500 | POST | [http://10.10.1.34:8020/dcapi/report/pdf/generate](http://10.10.1.34:8020/dcapi/report/pdf/generate)| 1,003 | An internal error occurred while processing the request. Please try again later.|



```prolog
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Directory already present or error in creating directory|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Generated file in path E:\UEMS_CentralServer\server_process\common_files\files\1\templatereport\ondemand\14-04-2026\ExecutivePatchSummary1776190361044.pdf|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: ---------------------------------------Report generation start---------------------------------------|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Loading PDF class: com.me.ems.report.pdf.itext.PDFiText|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Loading PDFRenderer class: com.me.ems.report.pdf.itext.PDFiTextRenderer|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Configuring PDF Object|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : HeaderTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : FooterTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : NullTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : MasterTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : ReportInfoTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : TableOfContents|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : ChapterTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : ParagraphTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : ChapterTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : SectionTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : ChartTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : SectionTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : ChartTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : ChapterTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : SectionTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : MickeyTableTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : SectionTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : MickeyTableTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : SectionTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : MickeyTableTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : SectionTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: creating template object : MickeyTableTemplate|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Directory already present or error in creating directoryE:\UEMS_CentralServer\server_process\common_files\temp_files\Chart\ChartOut\|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Output file Location : E:\UEMS_CentralServer\server_process\common_files\temp_files\Chart\ChartOut\|
[19:12:41:044]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Fetch the chart data for the graphName:patch_status_summary|
[19:12:41:075]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Entered into the method:getJsScript|
[19:12:41:075]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Fetch the chart data for the graphName:severity_counts|
[19:12:41:106]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Entered into the method:getJsScript|
[19:12:41:106]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Total thread pool size: 10|
[19:12:41:106]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Start of getImagesMethod|
[19:12:41:106]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Directory already present or error in creating directoryE:\UEMS_CentralServer\server_process\common_files\temp_files\Chart\ChartOut\|
[19:12:41:106]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[12984]|[SERVER-dfc227b1-e69d-4649-a9bc-c4bb7fd487cc]: Starting task. TaskCount:1|
[19:12:41:106]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Assigning worker. Active thread poolcount:2 Queue size:0 Task counter:5|
[19:12:41:106]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[12984]|[SERVER-dfc227b1-e69d-4649-a9bc-c4bb7fd487cc]: Directory already present or error in creating directoryE:\UEMS_CentralServer\server_process\common_files\temp_files\Chart\ChartOut\|
[19:12:41:411]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[12984]|[SERVER-dfc227b1-e69d-4649-a9bc-c4bb7fd487cc]: Task failed while generating images using javaFx. Refer JavaFx_error.log for more details|
[19:12:43:117]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Directory already present or error in creating directoryE:\UEMS_CentralServer\server_process\common_files\temp_files\Chart\ChartOut\|
[19:12:43:117]|[04-14-2026]|[ReportEngineLogger]|[INFO]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Screenshots generated at location: E:\UEMS_CentralServer\server_process\common_files\temp_files\Chart\ChartOut\|
[19:12:43:133]|[04-14-2026]|[ReportEngineLogger]|[SEVERE]|[341]|[0939637d-1192-4ae1-9194-e77663ba3494]: Exception in rendering template. On error hook invoked| 
com.me.ems.report.pdf.PDFException: IOException in Header Template
	at com.me.ems.report.pdf.itext.template.renderer.HeaderTemplateRenderer.renderTemplate(HeaderTemplateRenderer.java:34)
	at com.me.ems.report.pdf.itext.template.renderer.TemplateRendererItext.renderTemplate(TemplateRendererItext.java:19)
	at com.me.ems.report.pdf.itext.template.PDFiTextTemplate.render(PDFiTextTemplate.java:93)
	at com.me.ems.report.pdf.itext.template.HeaderTemplate.render(HeaderTemplate.java:9)
	at com.me.ems.report.pdf.template.PDFTemplate.writeToDocument(PDFTemplate.java:80)
	at com.me.ems.report.pdf.itext.event.PDFEvent.onEndPage(PDFEvent.java:51)
	at com.lowagie.text.pdf.PdfDocument.newPage(PdfDocument.java:943)
	at com.lowagie.text.pdf.PdfDocument.add(PdfDocument.java:596)
	at com.lowagie.text.Document.add(Document.java:303)
	at com.me.ems.report.pdf.itext.template.ChapterTemplate.willRender(ChapterTemplate.java:28)
	at com.me.ems.report.pdf.template.PDFTemplate.writeToDocument(PDFTemplate.java:79)
	at com.me.ems.report.pdf.itext.template.renderer.MasterTemplateRenderer.renderTemplate(MasterTemplateRenderer.java:30)
	at com.me.ems.report.pdf.itext.template.renderer.TemplateRendererItext.renderTemplate(TemplateRendererItext.java:19)
	at com.me.ems.report.pdf.itext.template.PDFiTextTemplate.render(PDFiTextTemplate.java:93)
	at com.me.ems.report.pdf.template.PDFTemplate.writeToDocument(PDFTemplate.java:80)
	at com.me.ems.report.pdf.helper.PDFRendererHelper.renderTemplateWithinTransaction(PDFRendererHelper.java:113)
	at com.me.ems.report.pdf.helper.PDFRendererHelper.renderPDF(PDFRendererHelper.java:84)
	at com.me.ems.report.pdf.itext.PDFiTextRenderer.renderPDF(PDFiTextRenderer.java:40)
	at com.me.ems.report.ReportGenerator.writePdfToStream(ReportGenerator.java:146)
	at com.me.ems.report.ReportGenerator.writePdfToFile(ReportGenerator.java:95)
	at com.me.dc.vulnerability.core.utils.ReportsUtil.initiatePDFGeneration(ReportsUtil.java:412)
	at com.me.dc.vulnerability.api.v1.controller.ReportsController.exportPDF(ReportsController.java:237)
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(Unknown Source)
	at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(Unknown Source)
	at java.base/java.lang.reflect.Method.invoke(Unknown Source)
	at org.glassfish.jersey.server.model.internal.ResourceMethodInvocationHandlerFactory.lambda$static$0(ResourceMethodInvocationHandlerFactory.java:52)
	at org.glassfish.jersey.server.model.internal.AbstractJavaResourceMethodDispatcher$1.run(AbstractJavaResourceMethodDispatcher.java:146)
	at org.glassfish.jersey.server.model.internal.AbstractJavaResourceMethodDispatcher.invoke(AbstractJavaResourceMethodDispatcher.java:189)
	at org.glassfish.jersey.server.model.internal.JavaResourceMethodDispatcherProvider$TypeOutInvoker.doDispatch(JavaResourceMethodDispatcherProvider.java:219)
	at org.glassfish.jersey.server.model.internal.AbstractJavaResourceMethodDispatcher.dispatch(AbstractJavaResourceMethodDispatcher.java:93)
	at org.glassfish.jersey.server.model.ResourceMethodInvoker.invoke(ResourceMethodInvoker.java:478)
	at org.glassfish.jersey.server.model.ResourceMethodInvoker.apply(ResourceMethodInvoker.java:400)
	at org.glassfish.jersey.server.model.ResourceMethodInvoker.apply(ResourceMethodInvoker.java:81)
	at org.glassfish.jersey.server.ServerRuntime$1.run(ServerRuntime.java:256)
	at org.glassfish.jersey.internal.Errors$1.call(Errors.java:248)
	at org.glassfish.jersey.internal.Errors$1.call(Errors.java:244)
	at org.glassfish.jersey.internal.Errors.process(Errors.java:292)
	at org.glassfish.jersey.internal.Errors.process(Errors.java:274)
	at org.glassfish.jersey.internal.Errors.process(Errors.java:244)
	at org.glassfish.jersey.process.internal.RequestScope.runInScope(RequestScope.java:265)
	at org.glassfish.jersey.server.ServerRuntime.process(ServerRuntime.java:235)
	at org.glassfish.jersey.server.ApplicationHandler.handle(ApplicationHandler.java:684)
	at org.glassfish.jersey.servlet.WebComponent.serviceImpl(WebComponent.java:394)
	at org.glassfish.jersey.servlet.WebComponent.service(WebComponent.java:346)
	at org.glassfish.jersey.servlet.ServletContainer.service(ServletContainer.java:359)
	at org.glassfish.jersey.servlet.ServletContainer.service(ServletContainer.java:312)
	at org.glassfish.jersey.servlet.ServletContainer.service(ServletContainer.java:205)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:197)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at org.apache.tomcat.websocket.server.WsFilter.doFilter(WsFilter.java:51)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at com.adventnet.cp.ClientFilter.doFilter(ClientFilter.java:32)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at com.adventnet.authentication.filter.RememberMeFilter.doFilter(RememberMeFilter.java:52)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142) 
	at com.me.devicemanagement.onpremise.webclient.filter.CommonFilter.doFilter(CommonFilter.java:78)
```

