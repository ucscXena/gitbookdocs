---
description: Under construction
---

# Tutorial: Tumor vs Normal

## Description

We will cover how to view tumor and normal samples side by side and how to compare gene expression for one or more genes between tumor and normal samples. 

We will be using both GTEx samples as our normal samples as well as TCGA matched normal samples. More information on GTEx normal samples can be found here:

{% page-ref page="../how-do-i/tumor-vs-normal.md" %}

## Prerequisites

This tutorial assumes completion of the Basic Tutorials, especially the [Basic Tutorial: Section 3](basic-tutorial-section-3.md).

## Estimated time needed

**Part A**: 10 min

**Part B**: 5 min

## Learning goals

**Part A**

* Build a visual spreadsheet with the columns primary site, sample type, study, and gene expression the TCGA TARGET GTEx study.
* Filter to just colon samples.

**Part B**

* Create a box plot using the Charts and Statistics View

## Tutorial

We will compare _MYC_ gene expression between GTEx normal colon samples and TCGA colon adenocarcinoma primary tumor samples.

### Part A

Our goal is to build a visual spreadsheet with the columns 'primary site', 'sample site', 'study', and gene expression for _MYC_ for the TCGA TARGET GTEx study. We will then filter to just samples in the colon.

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=1bd621010a99958b139840a83a49562d)

![](../.gitbook/assets/screen-shot-2021-06-08-at-1.59.21-pm.png)

#### Steps

1. Start at our home page [http://xena.ucsc.edu/](http://xena.ucsc.edu/) and click on 'Launch Xena'. You are now in our Visual Spreadsheet Wizard.
2. Type 'TCGA TARGET GTEx', select this study from the drop down menu, and click 'Done'.
3. Type '_MYC_', select the checkbox for Gene Expression and click 'Done'.
4. Choose 'Phenotypic' and select the checkboxes for 'sample type', 'study' and 'Primary site', and click 'Done'.
5. Type 'colon' in the Find, Filter, and Subgroup search bar and choose 'Keep samples'.

#### Video of steps 1-4

#### Video of step 5

### Part B

Our goal is now see if the difference in gene expression, where normal samples tend to have lower _MYC_ expression, is statistically significant.

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=5037e150565a8331ca94d869dfb0a209)

![](../.gitbook/assets/screen-shot-2021-06-08-at-2.02.19-pm.png)

#### Steps

1. Click the column menu for column B \(MYC gene expression\) and choose 'Charts & Stats'
2. Click 'Compare subgroups', click the dropdown for 'Show data from' and choose 'column B: MYC - gene expression RNAseq - RSEM norm\_count' if it is not already selected
3. Click the dropdown for 'Subgroup samples by' and choose 'column C: Sample Type'.
4. Leave the chart type as 'box plot', and click 'Done'. 

#### Video of steps 1-4

## Test your knowledge
