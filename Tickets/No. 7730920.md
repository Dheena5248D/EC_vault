---
notion_id: "33d43c23-a5e2-800c-8cb4-cfe64943b851"
notion_last_edited: "2026-04-09T06:28:00.000Z"
tags:
resolved: "False"
problem tags:
Solved by: "Others"
Date: "2026-04-06"
---

**Related back to Tickets:** [[No. 7782357  Executive reports]]

# Issue:

    Unable to run Executive reports

# Analysis:



# Log traces:

build.number=115260029

```prolog
[15:20:10:953]|[04-01-2026]|[ReportEngineLogger]|[SEVERE]|[359]|[d968a04e-5f79-45e0-a8e6-d08dfbc8f773]: Exception in rendering template. On error hook invoked| 
com.me.ems.report.pdf.PDFException: Exception in writing template to document : ChapterTemplate
	at com.me.ems.report.pdf.template.PDFTemplate.writeToDocument(PDFTemplate.java:87)
	at com.me.ems.report.pdf.itext.template.renderer.MasterTemplateRenderer.renderTemplate(MasterTemplateRenderer.java:30)
	at com.me.ems.report.pdf.itext.template.renderer.TemplateRendererItext.renderTemplate(TemplateRendererItext.java:19)
	at com.me.ems.report.pdf.itext.template.PDFiTextTemplate.render(PDFiTextTemplate.java:93)
	at com.me.ems.report.pdf.template.PDFTemplate.writeToDocument(PDFTemplate.java:80)
	at com.me.ems.report.pdf.helper.PDFRendererHelper.renderTemplateWithinTransaction(PDFRendererHelper.java:113)
	at com.me.ems.report.pdf.helper.PDFRendererHelper.renderPDF(PDFRendererHelper.java:84)
```

