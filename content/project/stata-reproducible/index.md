---
title: "Reproducible Deliverables from Stata"
subtitle: "Stata for Reproducible Results"
excerpt: "Stata enables us to create complete Word, Excel, PDF and HTML documents that not only include formatted text but also summary statistics, regression results, and graphs."
date: 2022-09-25
author: "Wenjia Zhu"
featured: true
draft: false
tags:
- Stata
categories:
- Reproducible Deliverables
- Stata
# layout options: single or single-sidebar
layout: single-sidebar

---

One of my work duties is preparing project reports and all the relevant workbooks. Though most of the projects are unique and one-time activities, in some cases, we would repeat the work and present the same kind of analysis results for the clients in consecutive years. For instance, we're always asked by our clients to provide program evaluation every year. To fulfill the requirements of these projects, we normally rely on Stata to manipulate the data and run statistical regressions to evaluate the program impacts. After getting the analyses completed in the stata, we would then start drafting the report and embed with summary statistics, regression results and graphs from various code files. You can imagine how labor intensive it could be to scrutinize hundreds of code lines and seek the correct pieces of information required in the report!

With the help of Stata's commands for report generation, we can easily insert results from Stata commands into formatted text and directly place tables and figures into our report document[^stata]. I'll give some simplified report examples in word and excel generated from stata `.do` files. 

---
## Generate Word Report

The `put*` commands, which are the **putdocx**, **putpdf**, and **putexcel**,  are used to create customized reports in Word, PDF, and Excel. To create a Word report, we begin the creation of the document, add in titles and other text, include estimation results and add graphs. We can also customize the report by applying some additional **putdocx** commands to add headers, footers, page numbers, titles, subtitles, and sections with different formatting. Attached is a simplified version of the [Word report](/project/stata-reproducible/report1.docx) example for download.

---
## Create Excel Report

We use **putexcel** command to export Stata results and graphs to Excel files. We can also format the file by some additional commands so as to modify the column labels, change the font type and size, and change the alignment of the font, and more. I include a simplified version of the [Excel report](/project/stata-reproducible/report2.xlsx) example for download.


[^stata]: Reproducible and automated reporting. [STATA](https://www.stata.com/features/overview/truly-reproducible-reporting/)







