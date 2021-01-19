# How do I compare gene expression between subgroups?

{% hint style="warning" %}
This page assumes you have already made subgroups. If you need help making subgroups, please go to the ['How do I make subgroups'](how-do-i-make-subgroups.md) help page.
{% endhint %}

Next, make sure that the gene or genes that you want to use in the comparison are on screen. Click on the charts icon in the top right  and choose 'Compare subgroups'. Click the dropdown for 'Show data from' and choose you gene expression column. Click the dropdown for 'Subgroup samples by' and choose your subgroup column. Choose if you would like a box plot or violin plot and click 'Done'. 

## Example

Below we examine aberrations in _EGFR_  in TCGA Lung Adenocarcinoma. We will investigate if samples that have aberrations in _EGFR_ \(mutations or copy number amplifications\) have higher expression.

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=dc05bbdcf590f7df4506fbcd721f60b5)

![https://xenabrowser.net/?bookmark=d31da9334a490d3cc5b5b75446e679a1](../.gitbook/assets/screen-shot-2021-01-13-at-11.43.35-am.png)

#### Steps

1. Click the graph icon in the upper right corner to enter Chart View.
2. Click 'Compare subgroups', since we want to compare the group of samples who have aberrations in _EGFR_ to the group of samples that do not.
3. Click the dropdown for 'Show data from' and choose 'column C: EGFR - gene expression RNAseq - HTSeq - FPKM-UQ'.
4. Click the dropdown for 'Subgroup samples by' and choose 'column B: \(mis OR infra\) OR C:&gt;0.5 - Subgroup'.
5. Click 'Done'. 

#### Video of steps

![](../.gitbook/assets/makeboxplot.gif)

{% hint style="info" %}
For more information see our [Basic Tutorial: Section 3](../tutorials/basic-tutorial-section-3.md), where this example was pulled from.
{% endhint %}

