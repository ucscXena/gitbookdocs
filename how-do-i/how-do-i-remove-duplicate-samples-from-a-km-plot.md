# How do I remove duplicate samples from a KM plot?

If your plot has an '!' icon next to the p-value this means that some samples are in your plot twice. This can happen when A\) a patient has both a tumor and normal sample or when a patient has a metastasis that is part of the dataset and/or B\) a tumor sample was split into multiple aliquots and then run through the same analysis twice.

This page will guide you on how to remove duplicates due to A. If there are duplicates due to B you will need to [download the data](../overview-of-features/download-data.md), decide how to resolve any inconsistencies between the multiple aliquots and [load it up as your own data](../local-xena-hub/).

![](../.gitbook/assets/idh1km.png)

[https://xenabrowser.net/heatmap/?bookmark=93a89b4749b93a0288d9c2ea23045fae](https://xenabrowser.net/heatmap/?bookmark=93a89b4749b93a0288d9c2ea23045fae)

## Removing duplicates

1. Add the data column of 'sample type' from the Phenotype data

{% hint style="info" %}
Note that different datasets may call this phenotype data something slightly different. We are just trying to add a column of data that indicates the sample type such as 'Primary Tumor', 'Normal', etc.
{% endhint %}

Bookmark: [https://xenabrowser.net/heatmap/?bookmark=12583e1bb07f2ae755a503fc55313862](https://xenabrowser.net/heatmap/?bookmark=d51db865d437e3f760bad2b14373bfa0)

We can see here that some patients have both Primary and Recurrent Tumors. 

2. Filter to only samples that are 'Primary tumor' by typing 'primary' into the filter search box. [More help on filtering](../overview-of-features/filter-and-subgrouping.md). Next, click the filter icon next to the filter search box and chose 'Filter'. This will filter out all samples that are not primary tumor.

![](../.gitbook/assets/filtertoprimary.gif)

To filter out the samples that are 'Recurrent Tumor', type 'primary' into the filter search box

3. Run your KM analysis by clicking the caret menu at the top of the column and choosing 'Kaplan-Meier plot' It will now only have primary tumor samples in it!

![](../.gitbook/assets/idh1kmgood.png)

[![](/content/images/2017/09/Untitled-6.png) https://xenabrowser.net/heatmap/?bookmark=a56b47aefabb74042622547395a6b0a0](https://xenabrowser.net/heatmap/?bookmark=e69084a4619bf669320d81ce2b160f5b)

