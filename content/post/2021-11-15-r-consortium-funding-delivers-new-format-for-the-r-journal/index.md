---
title: R Consortium Funding Delivers New Format for the R Journal
author: Di Cook, Mitch O'Hara-Wild, H. Sherry Zhang, Stephanie Kobakian
date: '2021-11-15'
slug: r-consortium-funding-delivers-new-format-for-the-r-journal
categories: ["R", "R Journal"]
tags: ["R Markdown"]
---

The [R Journal](https://journal.r-project.org/) is a primary outlet for publishing research of interest to the R community. It publishes articles related to R packages (detailing the the broader context, implementation details and examples of use), applications, comparisons and benchmarking and reviews. The journal was born in 2009, superseding a long-running newsletter, to provide an outlet documenting advances in statistical computing, discuss issues and research opportunities at the intersection of statistical analysis and software, and to encourage awareness of these advances and opportunites within the community.

Articles have traditionally been written using latex, and outputted to `pdf`, with code and data to reproduce results provided separately. `Sweave` emerged later as a commonly used dynamic document system and allowed R code to be embedded directly into document whose output was `tex` document that included output (including tables and graphs) generated from embedded R code. This was essentially an accepted pre-processing step resulting in a `tex` conforming to the structure required by the R Journal.

The operations of the R Journal are entirely run using R itself and, to our knowledge, it is the only journal of this kind. Common operations performed by editors including acknowledging submissions, sending review requests, organising reviews, emailing authors about their paper's status, compiling articles into an issue, and populating the web site are all contained within the `rj` package, which is available on Github. It's lovely to contemplate; R is the editorial workflow system for the R Journal. 

The journal is produced entirely by volunteers, like much of the R community. It is an ever-changing group of people who get involved because they care about the community and the availability and survival of a publishing outlet for research related to R. Some members are lucky to have the support of their workplace, usually academic, and juggle the responsibilities with teaching, their own research or consulting. The editorial responsibilities include updating editorial management software (with the `rj` package) as well as managing article submissions. 

Inspired by a [talk by Yihui Xie in 2018 "Towards An Open-access, Fast, and Reproducible Journal"](https://slides.yihui.org/2017-DSM-Journal-Yihui-Xie.html#1),and knowing that she would be committing to be an editor of the R Journal from 2019, Di submitted a grant to the R Consortium requesting funds to experiment with changing the format and operations. It was successfully funded at $50,000USD to support the "hiring of an editorial assistant, and to experiment with alternative operations to streamline checking compliance of submitted papers, soliciting, constructing and returning reviews, copy-editing, construction and web delivery of new issues". 

Central to the new format was utilizing [Rmarkdown](https://rmarkdown.rstudio.com) for document writing. Just reviewing Yihui's slides I now see the wonderful gif describing a latex foundation (slide 16/30) document, and I can confirm that the first year as Editor-in-Chief (this year) that working with the the `rj` functions on the latex files to build an issue was very much like this, one little bump brings the whole system down. `Rmarkdown` is a much friendlier version of dynamic document building than `Sweave`, and writes to various outputs, including `html`, thanks to pandoc. It is much more elegant for graphics - which is dear to my heart. With `html` format there is also the prospect of including interactive graphics. 

We are now happy to announce that there is a new way to write R Journal articles, that deliver them in `html`. The [new web site can be viewed in development version](https://journal.r-project.org/dev/), with a goal to rolling it out as the main site with the December issue this year. 

The new web site has these features:

- revised overview of the journal
- updated instructions for authors
- `html` formatted articles submitted as `Rmd`, in addition to the `pdf` format. 

There are numerous benefits of the new `html` formatted articles, which include the **ability to include interactive graphics**, and that it is a **more accessible format** for the blind members of the R community.  ([Jonathan Godfrey is suitably excited!](https://www.massey.ac.nz/massey/expertise/profile.cfm?stref=416430)) To get a glimpse of what is possible with interactive graphics, take a look at the article [Conversations in Time](https://journal.r-project.org/dev/articles/RJ-2021-050/) where you can find embedded, a plot with linked brushing between multiple plots, and a movie. 

The way to get started yourself is to use the [rjtools](https://rjournal.github.io/rjtools/index.html). The function `create_article()` creates a template in your project, containing a variety of key points, and an interactive plot made with [ggplot2](https://ggplot2.tidyverse.org) and [plotly](https://plotly-r.com). This package also allows you to check your article, prior to submission, a little like the way the `devtools` package helps to check your R package prior to submitting to [CRAN](https://cran.r-project.org). 
    
In the interim, the funding has supported numerous developments to the main workhorse package for operations, `rj`. This include:

- A new submission system: amazingly the previous system was running on submission to a [wufoo form](https://www.wufoo.com) hosted by the 2013 editor, Hadley Wickham. The new system uses a Google form, and populating into a Google spreadsheet, owned by current editors, with ownership migrating to new editors as needed. 
- A [pkgdown](https://pkgdown.r-lib.org) web site that includes better documentation on operations. 
- New functions like `match_keywords()` which allows finding reviewers whose expertise matches the the keywords for the article. 
- New functions for paper management such as tracking articles, and finding articles that are slow-moving in the repository.  
- A new issue building system. This is such a wonderful change, and a relief to the huge time commitment previously needed. With the new system it should be possible to bring out more than two issues per year to handle the larger number of articles. 
- A host of new functions to check articles, that have been migrated now to the `rjtools` package.  
- New functions to manage Associate Editor and reviewer load. 
- A system to manage the new process including Associate Editors in the review workflow. 

The funding has also provided intermittent editorial assistance. Initially, editorial assistant converted the long, long author guidelines into a check-list, multiple check-lists. An initial check-list was used for identifying articles that were not conforming to the guidelines when they were submitted. The second check-list is targeted to the article proofing prior to publication. Authors are provided with this list when their paper is accepted and asked to check their paper carefully, which has helped reduce the load from the editors. The first issue of 2021 was also copy-edited by the editorial assistant, quite painstakingly detailed suggested edits as red-inked pdfs sent to the authors to correct. We hope that you can see the language improvement in these articles. 

In the near future we hope to develop the journal operations in two directions: a system for authors to track the progress of their paper through the review system, and a web-based system to help editors manage reviews. 

To summarise, the funds from the R Consortium have provided the freedom for the R Journal editors to experiment, and dramatically improve the operations. 

