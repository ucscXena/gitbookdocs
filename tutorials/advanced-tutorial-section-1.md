---
description: >-
  Learn how to view whole chromosomes and view advanced datasets such as exon
  expression
---

# Advanced Tutorial: Section 1

## Description <a id="description"></a>

This tutorial is intended for those who have a basic understanding of how to use Xena. We will cover how to view whole chromosome and how to use the advanced dataset menu to access datasets such as exon expression.

## Prerequisites <a id="prerequisites"></a>

This tutorial assumes a basic understanding of how to build and read a [Visual Spreadsheet](../overview-of-features/visual-spreadsheet/). This can be achieved through completion of the Basic Tutorials, especially the [Basic Tutorial: Section 1](basic-tutorial-section-1.md).

## Estimated time needed <a id="estimated-time-needed"></a>

10 min‌

## Learning goals <a id="learning-goals"></a>

Create a visual spreadsheet that include a chromosome-wide column and data from the advanced dataset menu

## Tutorial <a id="tutorial"></a>

We will investigate the _ERG-TMPRSS2_ gene fusion and _TMPRSS2_ promoter hijacking in patients from the TCGA Prostate Cancer study.

_ERG_ is an oncogene that expressed at low levels in normal prostate tissue. Some patient's prostate cancer samples have higher expression of _ERG_. These samples tend to have an intra-chromosomal deletion that fuses _ERG_ to _TMPRSS2_. As _TMPRSS2_ is expressed at high levels in normal prostate tissue, this allows _ERG_ to hijack the _TMPRSS2_ promoter which leads to increased _ERG_ expression.

{% embed url="https://docs.google.com/presentation/d/1kiGz-L6Z2Qm4PwMs3Sbtvtr1tF-xd3PXOUAetamt\_6k/edit?usp=sharing" %}

#### [​Ending Screenshot​](https://xenabrowser.net/?bookmark=6ea137951fb4ddad4c8a6baaac3914f4) <a id="ending-screenshot"></a>

{% hint style="info" %}
Note that column D may look slight different, depending on how resize and zoom the column.
{% endhint %}

![](../.gitbook/assets/screen-shot-2021-06-10-at-12.46.32-pm.png)

We can now see that there are many patient's samples with relatively high expression of _ERG_ \(column B\), and that if we look more closely that this relatively high expression is not uniform across the exons of _ERG_, but instead is in the exons closer to the 3' end of the gene \(column C\). Looking at column D, we can see that these samples that have relatively high expression also have an interchromosomal deletion of part of chromosome 21. If we hover over the genes at either end of the deletion, we can see that the end points fall within _ERG_ and _TMPRSS2_. 

#### Steps <a id="steps"></a>

1. Start at [https://xenabrowser.net/](https://xenabrowser.net/)
2. Type 'TCGA Prostate Cancer \(PRAD\)', select this study from the drop down menu, and click 'Done'.
3. Type '_ERG_', select the checkbox for Gene Expression and click 'Done'.
4. Type '_ERG_', click 'Show Advanced', select the checkbox for 'IlluminaHiSeq' under 'exon expression RNAseq', and click 'Done'.
5. Click the text 'Click to insert a column' after column C. Type 'chr21', select the checkbox for Copy Number and click 'Done'.
6. Click on the filter menu and select 'Remove samples with nulls'
7. Click on the  handle in the lower right corner of column E, copy number for chromosome 21. Move it to the right to make the column bigger. 
8. Click and drag within column E, copy number for chromosome 21 to zoom into the intra-chromosomal deletion.

#### Video of steps 1-4 <a id="video-of-steps"></a>

![](../.gitbook/assets/advanced_1.gif)

#### ‌**Video of steps 5-8**

![](../.gitbook/assets/advanced_2.gif)

{% hint style="info" %}
More information:

* [Advanced dataset menu](../overview-of-features/visual-spreadsheet/#advanced-datasets)
* [Visual Spreadsheet](../overview-of-features/visual-spreadsheet/)
{% endhint %}

## Test your knowledge <a id="test-your-knowledge"></a>

{% tabs %}
{% tab title="Question 1" %}
Add copy number data for chromosome 1.
{% endtab %}

{% tab title="Answer 1" %}
\*\*\*\*[**Ending Screenshot**](https://xenabrowser.net/?bookmark=95d77b2d3107653fa2a7be51424f0a04)\*\*\*\*

![](../.gitbook/assets/screen-shot-2021-06-10-at-3.49.57-pm.png)
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Question 2" %}
Add DNA Methylation data for _ERG_.
{% endtab %}

{% tab title="Answer 2" %}
\*\*\*\*[**Ending Screenshot**](https://xenabrowser.net/?bookmark=3b8cf8fa103e5fe2d718337551af34a4)\*\*\*\*

![](../.gitbook/assets/screen-shot-2021-06-10-at-3.48.18-pm.png)
{% endtab %}
{% endtabs %}

