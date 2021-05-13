# Xena Gene Set Viewer

The Xena Gene Sets Viewer [https://xenagoweb.xenahubs.net/xena](https://xenagoweb.xenahubs.net/xena) compares gene expression, somatic mutation, and copy number variation profile of cancer related gene sets across cancer cohorts.  It queries genomics data hosted on public Xena Hubs, in a similar way as other tools in the Xena Visualization suite. And then it generates gene set visualizations of those data.

Source code:

* [Xena Gene Set Viewer](https://github.com/ucscXena/XenaGoWidget)
* [Xena Analysis Server](https://github.com/ucscXena/xena-analysis-grails)

## Overview

The Gene Set Viewer allows comparison of individual gene sets or pathways and their genes across two cancer tumor sample cohorts as well as comparison within the same sub cohorts.

![](../.gitbook/assets/overview.png)

As an overview, Figure 1 shows two cohorts, the left \(olive background, TCGA Ovarian Cancer\)  and the right \(tan background , TCGA Prostate Cancer\).    Figure 1A shows the selection for the analysis, Gene Set, view limit, and filter \(differential versus similar\).  Figure 1B shows the view comparing the Mean Gene Set Score in the center and individual samples on the right.   1C shows the individual samples, with the hover result showing the sample and score in 1E.  1D provides a link directly into Xena for the given gene set.  1F provides a sharable URL link.   1G provides a login for use in uploading.

![Figure 2.  Xena view of Gene Expression gene sets realized by clicking on Figure 1D shows](../.gitbook/assets/image%20%288%29.png)



![Figure 3. Opening a gene set figure Figure 1 to show individual gene expression by sample.](../.gitbook/assets/image%20%287%29.png)

![Figure 4. Clicking on an open gene target from 3 shows the gene set and the individual genes. ](../.gitbook/assets/image%20%2811%29.png)

![Figure 5. Clicking Edit in Figure 1 or  3 allows changing cohort, as well as individual sub cohorts.](../.gitbook/assets/image%20%289%29.png)

![Figure 6 Analysis can be changed from Figure 1A.  Here we see CNV and Mutation together.](../.gitbook/assets/image%20%286%29.png)

![Figure 7 Hovering over CNV + Mutation view shows types of mutation and CNV.](../.gitbook/assets/image%20%2814%29.png)

![Figure 8 A user that is logged in may upload a tab delimited GMT file which is analyzed and available.](../.gitbook/assets/image%20%2810%29.png)

Figure 8 shows analysis of a GMT file using the BPA method \[[citation](https://www.nature.com/articles/s41467-019-12924-w): thanks to Verena Friedl\].   This is only available to logged in users and they may only see their own analysis and are limited to 100 pathways.  Logins are any valid google login.    Several public pathway sets are available including those curated from the Gene Ontology Consortium \(thanks to Laurent-Philippe Albou\) as well as those from the Hallmark \[cite\] and Pancan \[cite\] analyses.

![figure 9 &apos;+&apos; symbol in Figure 1A allows editing of gene sets from pre-analyzed set.](../.gitbook/assets/image%20%2812%29.png)





## Analysis

### Gene Expression

* BPA GENE EXPRESSION
* PARADIGM IPL
* REGULON ACTIVITY \(only avaiable for the LUAD Cohort\)

### Mutation / CNV

* CNV ∩ MUTATION
* COPY NUMBER
* MUTATION

## Sources for the somatic mutation and copy number variation data

* [https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)
* [https://xenabrowser.net/datapages/?cohort=Cancer Cell Line Encyclopedia \(Breast](https://xenabrowser.net/datapages/?cohort=Cancer%20Cell%20Line%20Encyclopedia%20%28Breast)\)

