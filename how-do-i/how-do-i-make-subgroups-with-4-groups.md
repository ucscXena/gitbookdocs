---
description: >-
  Instead of making just subgroups with geneA high vs low, this page will show
  you how to make subgroups with geneA high & geneB high
---

# How do I make subgroups with geneA high and geneB high?

{% hint style="warning" %}
This page assumes you are familiar with making 2 subgroups. If you are not, please see the ['How do I make subgroups'](how-do-i-make-subgroups.md) help page.
{% endhint %}

This page details how to create subgroups based on the expression of 2 genes so that you create the following 4 subgroups:

* geneA expression is high AND geneB expression is high
* geneA expression is high AND geneB expression is low
* geneA expression is low AND geneB expression is low
* geneA expression is low AND geneB expression is high

To do this enter a search terms for each gene, such as 'C:>15' or 'D:<0.6' into the search box and separate each search term with a ';'.

[Here is an example](https://xenabrowser.net/?bookmark=5a20f78764f8cf07ac93ae4a998913e1). You can see in the search bar the expression used to make column A using the example genes of CD44 and CD24.&#x20;

Also note that you can use this feature on columns besides gene expression, such as copy number variation, etc. You can also use it on categorical features, for instance to compare expression of a gene and the patient's gender (male or female). Simply add the gender column to the Visual Spreadsheet and enter 'female' for one of the search terms above.&#x20;

{% hint style="info" %}
[See our help on renaming the subgroup labels](https://ucsc-xena.gitbook.io/project/overview-of-features/filter-and-subgrouping#changing-subgroup-labels) from 'true' and 'false' to something more biologically meaningful.
{% endhint %}
