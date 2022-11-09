# How do I compare gene expression between subgroups?

{% hint style="warning" %}
This page assumes you have a column on screen that has the groups you would like to compare (such as 'sample type' for comparing tumor vs normal') or have already made subgroups (such as 'has mutations in _EGFR_' vs 'does not have mutations in _EGFR_'). If you need help making subgroups, please see the ['How do I make subgroups'](how-do-i-make-subgroups.md) help page.
{% endhint %}

1. First, make sure that the gene or genes that you want to compare across your groups are on screen.&#x20;
2. Click on the charts icon in the top right and choose 'Compare subgroups'.&#x20;
3. Click the dropdown for 'Show data from' and choose your gene expression column.&#x20;
4. Click the dropdown for 'Subgroup samples by' and choose your subgroup column.&#x20;
5. Choose if you would like a box plot or violin plot and click 'Done'.&#x20;

## Example

Below we look at patient's samples that have aberrations in _EGFR_  in the TCGA Lung Adenocarcinoma study. We will investigate if patient's samples that have aberrations in _EGFR_ (mutations or copy number amplifications) have higher expression.

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=dc05bbdcf590f7df4506fbcd721f60b5)

![https://xenabrowser.net/?bookmark=d31da9334a490d3cc5b5b75446e679a1](../.gitbook/assets/screen-shot-2021-01-13-at-11.43.35-am.png)

#### Steps

1. Click the graph icon in the upper right corner to enter Chart View.
2. Click 'Compare subgroups', since we want to compare the group of samples who have aberrations in _EGFR_ to the group of samples that do not.
3. Click the dropdown for 'Show data from' and choose 'column C: EGFR - gene expression RNAseq - HTSeq - FPKM-UQ'.
4. Click the dropdown for 'Subgroup samples by' and choose 'column B: (mis OR infra) OR C:>0.5 - Subgroup'.
5. Click 'Done'.&#x20;

#### Video of steps

![](../.gitbook/assets/makeboxplot.gif)

{% hint style="info" %}
For more information see our [Basic Tutorial: Section 3](../tutorials/basic-tutorial-section-3.md).
{% endhint %}
