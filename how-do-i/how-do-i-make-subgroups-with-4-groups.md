---
description: >-
  Instead of making just subgroups with geneA high vs low, this page will show
  you how to make subgroups with geneA high & geneB high
---

# How do I make subgroups with geneA high and geneB high?

You may want to create subgroups based on the expression of 2 genes so that you create the following 4 subgroups:

* geneA expression is high AND geneB expression is high
* geneA expression is high AND geneB expression is low
* geneA expression is low AND geneB expression is low
* geneA expression is low AND geneB expression is high

Our beta feature will allow you to do this. First, be familiar with the [basics of creating 2 subgroups](how-do-i-make-subgroups.md). Then, using this, create two search terms, one for each column. Finally, enter them in the search bar and separate them with a ";". [Here is an example](https://xenabrowser.net/?bookmark=5a20f78764f8cf07ac93ae4a998913e1). You can see in the search bar the expression used to make column A using the example genes of CD44 and CD24. 

This new column can then be used to run a [KM plot ](../overview-of-features/kaplan-meier-plots.md)or [compare the subgroups](how-do-i-compare-gene-expression-between-subgroups.md). 

Note that you can also change the values in the Visual Spreadsheet for column A from 'true;true' to something that makes more sense for you such as 'CD44 high and CD24 high', etc. by clicking on the 3 dot menu at the top of the column and choosing 'display'. 

Also note that you can use this feature on columns besides gene expression, such as copy number variation, etc. You can also use it on categorical features, for instance to compare expression of a gene and the patient's gender \(male or female\). Simply add the gender column to the Visual Spreadsheet and enter 'female' for one of the search terms above. 

