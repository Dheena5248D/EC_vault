---
notion_id: "33743c23-a5e2-8034-bdff-ccb2af60f7e9"
notion_last_edited: "2026-04-05T07:05:00.000Z"
tags:
  - "ui"
  - "report"
resolved: "False"
Difficulty: "2"
problem tags:
  - "post server-upgrade"
  - "ui rendering"
  - "collection not processed"
Solved by: "ME"
Date: "2026-04-03"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003518103302"
---

# Issue:

generate Executive Threat Summary reports fails and shown an error " An internal error occurred while processing the request, Please Try again later”

# Analysis:

There is a Known issue that throws an execption in image generation

The fix has been relased in 11.5.2605.08 and above, kindly suggest server upgrade

[https://www.manageengine.com/products/desktop-central/service-packs1.html](https://www.manageengine.com/products/desktop-central/service-packs1.html)

# Log traces:

```sql
[12:06:33:874]|[03-25-2026]|[dcRestAPILogger]|[INFO]|[515]|[6b1ed66b-c841-4adf-829e-9c24982c5979]: 500 | POST | https://patch2-srvr.domain2000.local:8383/dcapi/report/pdf/generate | 1,003 | An internal error occurred while processing the request. Please try again later.|
[12:06:33:874]|[03-25-2026]|[dcRestAPILogger]|[INFO]|[515]|[6b1ed66b-c841-4adf-829e-9c24982c5979]: 500 | POST | https://patch2-srvr.domain2000.local:8383/dcapi/report/pdf/generate|
```

```sql
[12:06:32:234]|[03-25-2026]|[ReportEngineLogger]|[INFO]|[535]|[SERVER-44311088-1f00-4127-8fa7-7c5d533abeca]: Task failed while generating images using javaFx. Refer JavaFx_error.log for more details|
[12:06:32:266]|[03-25-2026]|[ReportEngineLogger]|[INFO]|[543]|[SERVER-6359ea12-ffb9-4d3e-80de-06e076a85bd6]: Task failed while generating images using javaFx. Refer JavaFx_error.log for more details|
[12:06:32:267]|[03-25-2026]|[ReportEngineLogger]|[INFO]|[527]|[SERVER-b7d2386d-37ba-448c-b28f-b7c1302398b8]: Task failed while generating images using javaFx. Refer JavaFx_error.log for more details|
[12:06:32:275]|[03-25-2026]|[ReportEngineLogger]|[INFO]|[455]|[SERVER-7ecce305-8e97-4176-9a9e-6fecd3cc5c3e]: Task failed while generating images using javaFx. Refer JavaFx_error.log for more details|
[12:06:32:278]|[03-25-2026]|[ReportEngineLogger]|[INFO]|[520]|[SERVER-1aa346ed-4ef1-400d-abbb-b80e854b7fa1]: Task failed while generating images using javaFx. Refer JavaFx_error.log for more details|
[12:06:33:837]|[03-25-2026]|[ReportEngineLogger]|[INFO]|[515]|[6b1ed66b-c841-4adf-829e-9c24982c5979]: Directory already present or error in creating directoryC:\Program Files\DesktopCentral_Server\server_process\common_files\temp_files\Chart\ChartOut\|
[12:06:33:838]|[03-25-2026]|[ReportEngineLogger]|[INFO]|[515]|[6b1ed66b-c841-4adf-829e-9c24982c5979]: Screenshots generated at location: C:\Program Files\DesktopCentral_Server\server_process\common_files\temp_files\Chart\ChartOut\|
[12:06:33:852]|[03-25-2026]|[ReportEngineLogger]|[SEVERE]|[515]|[6b1ed66b-c841-4adf-829e-9c24982c5979]: Exception in rendering template. On error hook invoked| 
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
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at com.me.devicemanagement.framework.webclient.filter.LicenseFilter.doFilter(LicenseFilter.java:84)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at com.me.devicemanagement.onpremise.webclient.filter.AuthorizationFilter.doFilter(AuthorizationFilter.java:102)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at com.me.devicemanagement.onpremise.webclient.filter.CommonActionsFilter.doFilter(CommonActionsFilter.java:181)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at com.me.devicemanagement.onpremise.webclient.filter.UIRestrictionFilter.doFilter(UIRestrictionFilter.java:110)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at com.me.devicemanagement.onpremise.webclient.filter.UMFilter.doFilter(UMFilter.java:164)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at com.me.devicemanagement.framework.webclient.filter.EncodingFilter.doFilter(EncodingFilter.java:50)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at com.adventnet.filters.ParamWrapperFilter.doFilter(ParamWrapperFilter.java:80)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at com.me.devicemanagement.framework.webclient.filter.FunctionalityRestrictionFilter.doFilter(FunctionalityRestrictionFilter.java:47)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at com.adventnet.iam.security.SecurityFilter.doNextFilter(SecurityFilter.java:965)
	at com.adventnet.iam.security.SecurityFilter.doFilter(SecurityFilter.java:615)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at com.adventnet.authentication.filter.AssociateCredential.doFilter(AssociateCredential.java:122)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:166)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:142)
	at org.apache.catalina.core.StandardWrapperValve.invoke(StandardWrapperValve.java:166)
	at org.apache.catalina.core.StandardContextValve.invoke(StandardContextValve.java:88)
	at org.apache.catalina.authenticator.AuthenticatorBase.invoke(AuthenticatorBase.java:481)
	at org.apache.catalina.core.StandardHostValve.invoke(StandardHostValve.java:127)
	at org.apache.catalina.valves.AbstractAccessLogValve.invoke(AbstractAccessLogValve.java:643)
	at com.me.integration.onpremise.common.iframe.DCAuthenticateRemote.handleRequest(DCAuthenticateRemote.java:204)
	at com.me.integration.onpremise.common.iframe.DCAuthenticateRemote.invoke(DCAuthenticateRemote.java:155)
	at org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:83)
	at org.apache.catalina.authenticator.SingleSignOn.invoke(SingleSignOn.java:315)
	at org.apache.catalina.core.StandardEngineValve.invoke(StandardEngineValve.java:72)
	at org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:344)
	at org.apache.coyote.ajp.AjpProcessor.service(AjpProcessor.java:429)
	at org.apache.coyote.AbstractProcessorLight.process(AbstractProcessorLight.java:63)
	at org.apache.coyote.AbstractProtocol$ConnectionHandler.process(AbstractProtocol.java:939)
	at org.apache.tomcat.util.net.NioEndpoint$SocketProcessor.doRun(NioEndpoint.java:1831)
	at org.apache.tomcat.util.net.SocketProcessorBase.run(SocketProcessorBase.java:52)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:973)
	at org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:491)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:63)
	at java.base/java.lang.Thread.run(Unknown Source)
Caused by: java.io.FileNotFoundException: C:\Program Files\DesktopCentral_Server\bin\..\webapps\DesktopCentral\client-data\1\customer-data\logo\customer-logo.png (The system cannot find the path specified)
	at java.base/java.io.FileInputStream.open0(Native Method)
	at java.base/java.io.FileInputStream.open(Unknown Source)
	at java.base/java.io.FileInputStream.<init>(Unknown Source)
	at java.base/java.io.FileInputStream.<init>(Unknown Source)
	at java.base/sun.net.www.protocol.file.FileURLConnection.connect(Unknown Source)
	at java.base/sun.net.www.protocol.file.FileURLConnection.getInputStream(Unknown Source)
	at java.base/java.net.URL.openStream(Unknown Source)
	at com.lowagie.text.Image.getInstance(Image.java:252)
	at com.lowagie.text.Image.getInstance(Image.java:328)
	at com.me.ems.report.pdf.itext.template.renderer.HeaderTemplateRenderer.renderTemplate(HeaderTemplateRenderer.java:25)
	... 112 more
```

