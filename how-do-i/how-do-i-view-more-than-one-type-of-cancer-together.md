---
description: For users who wish to compare data across different types of cancer
---

# How do I view multiple types of cancer together?

To view multiple types of cancer patients side-by-side, such as ovarian cancer patients and breast cancer patients, you will need to start with a Pan-Cancer dataset and then filter down to just the cancer types you want to see.&#x20;

There are 2 main Pan-Cancer studies:

* [TCGA PanCan Study](https://xenabrowser.net/datapages/?cohort=TCGA%20Pan-Cancer%20\(PANCAN\)) This contains the latest data from the PanCan Atlas project, including many hand curated datasets. It also contains some legacy TCGA data across all cancer types, including GISTIC 2 CNV estimates and miRNAseq estimates.
* [GDC TCGA PanCan (PANCAN) Study](https://xenabrowser.net/datapages/?cohort=GDC%20Pan-Cancer%20\(PANCAN\)) This contains the latest data from the GDC across all cancer types, mapped to hg38.

If you do not know which one you wish to use, we recommend starting with the TCGA PanCan Study.

## Generalized Steps

1\. Add the phenotype column that details the cancer type

{% hint style="info" %}
The phenotype column will vary depending on which study you choose. See below for specific column names
{% endhint %}

2\. Search for the cancer type you are interested in, making sure that it is listed in the phenotype column. **Separate each cancer type by 'OR'. Example: 'lgg OR gbm'.** Click the Filter + subgroup menu next to the search bar and select 'Keep Samples'.

![](<../.gitbook/assets/highlightlocation (2) (2) (2) (2) (2) (2) (2) (2) (2).png>)

![](../.gitbook/assets/highlightmenulocation.png)

{% hint style="info" %}
[More information on filtering](../overview-of-features/filter-and-subgrouping/)
{% endhint %}

## For TCGA Pan-Cancer (PANCAN) ...&#x20;

For the TCGA PanCan (PANCAN), you will want to add the phenotype column:

> cancer type abbreviation

{% hint style="info" %}
[Here is a bookmark ](https://xenabrowser.net/heatmap/?bookmark=d34a38000eca5f2bfcf936d5e06066dc)that will take you to the TCGA PanCan (PANCAN) Study with that phenotype column already selected.
{% endhint %}

## For GDC TCGA PanCan (PANCAN) ...

For the GDC TCGA PanCan (PANCAN), you will want to add the phenotype column:

> disease\_type

{% hint style="info" %}
[Here is a bookmark ](https://xenabrowser.net/heatmap/?bookmark=647fda97e21e3626d17788770855bd3c)that will take you to the GDC TCGA PanCan (PANCAN) Study with that phenotype column already selected.
{% endhint %}

## Example

Below is an example for viewing breast and ovarian cancer together for the TCGA PanCan Atlas

[**Beginning screenshot**](https://xenabrowser.net/heatmap/?bookmark=94d91442ccbf3ad7302857db86e8a3cf)****

****[**Ending screenshot**](https://xenabrowser.net/heatmap/?bookmark=beeee48590a9183ac2944063ba4c1774)

![](../.gitbook/assets/filterdown.gif)
