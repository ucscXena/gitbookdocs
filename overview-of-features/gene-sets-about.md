# Gene Sets Tool

GeneSet view \([Source](https://github.com/ucscXena/XenaGoWidget)\) cohort comparison tool:

[https://xenageneset.berkeleybop.io/xena/](https://xenageneset.berkeleybop.io/xena/)

is part of the [Xena Visual Spreadsheet suite](https://xenabrowser.net/heatmap/).

## About

Allows comparison individual gene sets and genes across two cancer cohorts.

![Xena GeneSet Tool Screen Shot](../.gitbook/assets/screenshot1.png)

## Overview

![Overview](../geneset/images/Overview1.png)

GeneSets are list along the left-hand-side.  Relevant scores from Cohort A on the left and Cohort B are on the right.  Darker red indicates that expression of selected events are over-represented and darker blue is under-represented.  A white color indicates that the expression is average for the expected samples.

Cohorts may be selected from the dialog next to the gene view.   

![Cohort Selection](../geneset/images/CohortSelection.png)

A selected Gene Set is highlighted in blue (A).  The selected genes are on the right (D) with Cohort A along the top and Cohort B along the bottom.  Highlighting the genes (D) or the the gene set (C) results in a green hover.  If a gene is highlighted, all of the gene sets that include that gene are hovered in green.  If a gene set is highlighted, all genes from the current selection are highlighted. 

If "Reciprocal Gene Set" is selected, then gene sets that contain any of the hovered gene set are also highlighted.

<img src="../geneset/images/Options1.png" data-canonical-src="../geneset/images/Options1.png" width="200" height="200" />

Colors and scale may be altered from the dialogs in the option.  Data may be downloaded as JSON from the current view.

Additional Gene Sets may be added or edited by selecting "Edit Pathways".

## Gene Search

In both the Gene Set View Pathway Editing screen, genes can be searched for.  Once highlighted, the genes and gene sets containing those genes will be highlighted in pink. 

