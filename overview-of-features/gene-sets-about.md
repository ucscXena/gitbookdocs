# Gene Sets Tool

The Gene Sets Tool [https://xenageneset.berkeleybop.io/xena/](https://xenageneset.berkeleybop.io/xena/) allows comparison of cancer tissue cohorts.  
It is part of the [Xena Visual Spreadsheet suite](https://xenabrowser.net/heatmap/).

Source can be found on GitHub <https://github.com/ucscXena/XenaGoWidget>.

## Overview

The Gene Set Tool allows direct comparison of individual gene sets and genes across two cancer tissue sample cohorts (Cohorts A and B).

![Overview](../geneset/images/Overview1.png)

Gene sets are list along the left-hand-side (A), with Cohort A presented on the LHS and Cohort B on the RHS. 
Darker red indicates that expression of selected events have over-represented expression and darker blue is under-represented expression of variants.
A white color indicates that the expression is average for the expected samples.

TODO: need a better explanation here

As a user hovers over gene sets the highlighted gene set is indicated in green (C), while the selected gene set (by clicking on itt) is indicated in blue. 
Genes for the selected gene set are shown in (D).  
Statistics for the hovered gene sets are shown in (B).   
Genes included in the hovered gene set are highlighted in green (D).

TODO: show hovered gene and samples


### Expanded Gene Set View

TODO: image of expanded gene set view

TODO: hovering of gene sets versus genes
 
 
### Cohort selection

![Cohort Selection](../geneset/images/CohortSelection.png)

A selected Gene set is highlighted in blue (A).  The selected genes are on the right (D) with Cohort A along the top and Cohort B along the bottom.  Highlighting the genes (D) or the the gene set (C) results in a green hover.  If a gene is highlighted, all of the gene sets that include that gene are hovered in green.  If a gene set is highlighted, all genes from the current selection are highlighted. 

If "Reciprocal Gene Set" is selected, then gene sets that contain any of the hovered gene set are also highlighted.

![Options](../geneset/images/Options1.png)

Colors and scale may be altered from the dialogs in the option.  Data may be downloaded as JSON from the current view.

Additional Gene Sets may be added or edited by selecting "Edit Pathways".

## Gene Search

In both the Gene Set View Pathway Editing screen, genes can be searched for.  
Once highlighted, the genes and gene sets containing those genes will be highlighted in pink. 

[!Gene Search Result](../geneset/images/GeneSearch)


## Editing Pathways


[!Editing Pathways](../geneset/images/Editing Pathways)
