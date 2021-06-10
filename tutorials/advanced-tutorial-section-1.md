---
description: Under construction
---

# Advanced Tutorial: Section 1

## Description <a id="description"></a>

This tutorial is intended for those who have a basic understanding of how to use Xena. We will cover how to view whole chromosome and how to use the advanced dataset menu to access datasets such as exon expression.

## Prerequisites <a id="prerequisites"></a>

This tutorial assumes completion of the [Basic Tutorial: Section 1](https://app.gitbook.com/@ucsc-xena/s/project/tutorials/basic-tutorial-section-1). Completion of [Basic Tutorial: Section 2](https://app.gitbook.com/@ucsc-xena/s/project/tutorials/basic-tutorial-section-2) and [Basic Tutorial: Section 3](basic-tutorial-section-3.md) is recommended but not required. 

## Estimated time needed <a id="estimated-time-needed"></a>

10 min‌

## Learning goals <a id="learning-goals"></a>

Create a visual spreadsheet that include a chromosome-wide column and data from the advanced dataset menu

## Tutorial <a id="tutorial"></a>

We investigate the _ERG-TMPRSS2_ gene fusion and _TMPRSS2_ promoter hijacking in TCGA Prostate Cancer.

_ERG_ is an oncogene that expressed at low levels in normal prostate tissue. Some prostate cancer samples have higher expression of _ERG_. These samples tend to have an intra-chromosomal deletion that fuses _ERG_ to _TMPRSS2_. As _TMPRSS2_ is expressed at high levels in normal prostate tissue, this allows _ERG_ to hijack the _TMPRSS2_ promoter which leads to increased _ERG_ expression.

{% embed url="https://docs.google.com/presentation/d/1kiGz-L6Z2Qm4PwMs3Sbtvtr1tF-xd3PXOUAetamt\_6k/edit?usp=sharing" %}

#### [​Ending Screenshot​](https://xenabrowser.net/?bookmark=6ea137951fb4ddad4c8a6baaac3914f4) <a id="ending-screenshot"></a>

{% hint style="info" %}
Note that column D may look slight different for you, depending on how large you make the column and where exactly you zoom to.‌
{% endhint %}

![](../.gitbook/assets/screen-shot-2021-06-10-at-12.46.32-pm.png)

#### Steps <a id="steps"></a>

1. Start at our home page [http://xena.ucsc.edu/](http://xena.ucsc.edu/) and click on 'Launch Xena'. You are now in our Visual Spreadsheet Wizard.
2. Type 'TCGA Prostate Cancer \(PRAD\)', select this study from the drop down menu, and click 'Done'.
3. Type '_ERG_', select the checkbox for Gene Expression and click 'Done'.
4. Type '_ERG_', click 'Show Advanced', select the checkbox for 'IlluminaHiSeq' under 'exon expression RNAseq', and click 'Done'.
5. Click the text 'Click to insert a column' after column C. Type 'chr21', select the checkbox for Copy Number and click 'Done'.
6. Click on the filter menu and select 'Remove samples with nulls'
7. Click on the  handle in the lower right corner of column E, copy number for chromosome 21. Move it to the right to make the column bigger. 
8. Click and drag within column E, copy number for chromosome 21 to zoom into the intra-chromosomal deletion.

#### Video of steps <a id="video-of-steps"></a>

‌

## Test your knowledge <a id="test-your-knowledge"></a>

{% tabs %}
{% tab title="Question" %}
Add copy number data for_TMPRSS2_ and _ERG_ to more closely examine the breakpoints within each gene.
{% endtab %}

{% tab title="Answer" %}
\*\*\*\*[**Ending Screenshot**](https://xenabrowser.net/?bookmark=a8efad0aae4e396aa2aa1ae06a7ddf12)\*\*\*\*

![](../.gitbook/assets/screen-shot-2021-06-10-at-12.49.41-pm.png)
{% endtab %}
{% endtabs %}

