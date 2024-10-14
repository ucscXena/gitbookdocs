---
description: For users who wish to compare data across different types of cancer
---

# How do I view multiple types of cancer together?

To view multiple types of cancer patients side-by-side you will need to start with a Pan-Cancer dataset and then filter down to just the cancer types you want to see.&#x20;

The [TCGA PanCan Study](https://xenabrowser.net/datapages/?cohort=TCGA%20Pan-Cancer%20\(PANCAN\)) contains the latest data from the PanCan Atlas project, including many hand curated datasets. It also contains some legacy TCGA data across all cancer types, including GISTIC 2 CNV estimates and miRNAseq estimates.

## Generalized Steps

1\. Add the phenotype column `cancer type abbreviation` that details the cancer type.

{% hint style="info" %}
[Here is a bookmark ](https://xenabrowser.net/heatmap/?bookmark=d34a38000eca5f2bfcf936d5e06066dc)that will take you to the TCGA PanCan (PANCAN) Study with that phenotype column already selected.
{% endhint %}

2\. Search for the cancer type you are interested in, making sure that it is listed in the phenotype column. **Separate each cancer type by 'OR'. Example: 'lgg OR gbm'.** Click the Filter + subgroup menu next to the search bar and select 'Keep Samples'.

![](<../.gitbook/assets/highlightlocation (2) (2) (2) (2) (2) (2) (2) (2) (2).png>)

![](../.gitbook/assets/highlightmenulocation.png)

{% hint style="info" %}
[More information on filtering](../overview-of-features/filter-and-subgrouping/)
{% endhint %}

## Example

Below is an example for viewing breast and ovarian cancer together for the TCGA PanCan Atlas

[**Beginning screenshot**](https://xenabrowser.net/heatmap/?bookmark=94d91442ccbf3ad7302857db86e8a3cf)

[**Ending screenshot**](https://xenabrowser.net/heatmap/?bookmark=beeee48590a9183ac2944063ba4c1774)

![](../.gitbook/assets/filterdown.gif)
