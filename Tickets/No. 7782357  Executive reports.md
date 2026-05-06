---
notion_id: "33d43c23-a5e2-8005-b3dc-fd4672242712"
notion_last_edited: "2026-04-09T07:14:00.000Z"
tags:
resolved: "False"
problem tags:
commented time: "2026-04-09T12:00:00.000+05:30"
Solved by: "ME"
Date: "2026-04-09"
ticket_url: "https://medcsupport.zohodesk.com/agent/medcsupport/all/tickets/details/220709003562814012"
---

**similar Tickets:** [[No. 7730920]]

# Issue:

generate Executive Threat Summary reports fails and shown an error " An internal error occurred while processing the request, Please Try again later”

# Analysis:

There is a Known issue that throws internal server error while report generation.



There is a Known issue that throws internal server error while report generation.

The issue is fixed in latest builds, kindly ask the customer to upgrade to 11.5.2600.34

[https://www.manageengine.com/products/desktop-central/service-packs.html](https://www.manageengine.com/products/desktop-central/service-packs.html)

# Log traces:

Build: 11.5.2600.26



```prolog
[09:09:23:913]|[04-07-2026]|[dcRestAPILogger]|[INFO]|[350]|[bc47ef75-3f9e-4a84-8474-90bd327a30cf]: 500 | POST | https://spos1105.cetelembr.cnet.intra:8383/dcapi/report/pdf/generate | 1.003 | An internal error occurred while processing the request. Please try again later.|
[09:09:23:913]|[04-07-2026]|[dcRestAPILogger]|[INFO]|[350]|[bc47ef75-3f9e-4a84-8474-90bd327a30cf]: 500 | POST | https://spos1105.cetelembr.cnet.intra:8383/dcapi/report/pdf/generate|
```



```prolog
[16:15:39:377]|[03-08-2026]|[ReportEngineLogger]|[INFO]|[531]|[SERVER-8b7a31cf-7f54-4694-b603-89897865e2a6]: Starting task. TaskCount:1|
[16:15:39:378]|[03-08-2026]|[ReportEngineLogger]|[INFO]|[531]|[SERVER-8b7a31cf-7f54-4694-b603-89897865e2a6]: Directory already present or error in creating directoryD:\Program Files\UEMS_CentralServer\server_process\common_files\temp_files\Chart\ChartOut\|
[16:15:43:133]|[03-08-2026]|[ReportEngineLogger]|[INFO]|[531]|[SERVER-8b7a31cf-7f54-4694-b603-89897865e2a6]: Task failed while generating images using javaFx. Refer JavaFx_error.log for more details|
[16:15:43:378]|[03-08-2026]|[ReportEngineLogger]|[INFO]|[352]|[e6b7a3b6-7228-4d67-b074-7e57392dd8d5]: Directory already present or error in creating directoryD:\Program Files\UEMS_CentralServer\server_process\common_files\temp_files\Chart\ChartOut\|
[16:15:43:378]|[03-08-2026]|[ReportEngineLogger]|[INFO]|[352]|[e6b7a3b6-7228-4d67-b074-7e57392dd8d5]: Screenshots generated at location: D:\Program Files\UEMS_CentralServer\server_process\common_files\temp_files\Chart\ChartOut\|
[16:15:43:590]|[03-08-2026]|[ReportEngineLogger]|[INFO]|[352]|[e6b7a3b6-7228-4d67-b074-7e57392dd8d5]: Fetch the chart data for the graphName:patch_status_summary|
[16:15:43:600]|[03-08-2026]|[ReportEngineLogger]|[SEVERE]|[352]|[e6b7a3b6-7228-4d67-b074-7e57392dd8d5]: Exception while getting image instance for chart| 
java.io.FileNotFoundException: D:\Program Files\UEMS_CentralServer\server_process\common_files\temp_files\Chart\ChartOut\opwlZ8FALhjEOQb2NBKC_Chart_1.png (The system cannot find the file specified)
	at java.base/java.io.FileInputStream.open0(Native Method)
	at java.base/java.io.FileInputStream.open(Unknown Source)
	at java.base/java.io.FileInputStream.<init>(Unknown Source)
	at java.base/java.io.FileInputStream.<init>(Unknown Source)
	at java.base/sun.net.www.protocol.file.FileURLConnection.connect(Unknown Source)
	at java.base/sun.net.www.protocol.file.FileURLConnection.getInputStream(Unknown Source)
	at java.base/java.net.URL.openStream(Unknown Source)
	at com.lowagie.text.Image.getInstance(Image.java:252)
	at com.lowagie.text.Image.getInstance(Image.java:328)
	at com.me.ems.report.pdf.itext.template.renderer.ChartRenderer.renderTemplate(ChartRenderer.java:33)
	at com.me.ems.report.pdf.itext.template.renderer.TemplateRendererItext.renderTemplate(TemplateRendererItext.java:19)
	at com.me.ems.report.pdf.itext.template.PDFiTextTemplate.render(PDFiTextTemplate.java:93)
	at com.me.ems.report.pdf.template.PDFTemplate.writeToDocument(PDFTemplate.java:80)
	at com.me.ems.report.pdf.itext.template.renderer.SectionTemplateRenderer.renderTemplate(SectionTemplateRenderer.java:22)
	at com.me.ems.report.pdf.itext.template.renderer.TemplateRendererItext.renderTemplate(TemplateRendererItext.java:19)
	at com.me.ems.report.pdf.itext.template.PDFiTextTemplate.render(PDFiTextTemplate.java:93)
	at com.me.ems.report.pdf.itext.template.SectionTemplate.render(SectionTemplate.java:38)
	at com.me.ems.report.pdf.template.PDFTemplate.writeToDocument(PDFTemplate.java:80)
	at com.me.ems.report.pdf.itext.template.renderer.ChapterTemplateRenderer.renderTemplate(ChapterTemplateRenderer.java:23)
	at com.me.ems.report.pdf.itext.template.renderer.TemplateRendererItext.renderTemplate(TemplateRendererItext.java:19)
	at com.me.ems.report.pdf.itext.template.PDFiTextTemplate.render(PDFiTextTemplate.java:93)
	at com.me.ems.report.pdf.template.PDFTemplate.writeToDocument(PDFTemplate.java:80)
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
```



