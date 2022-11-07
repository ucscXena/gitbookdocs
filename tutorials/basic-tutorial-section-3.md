---
description: Learn how to use Chart View and add new columns of data to a view
---

# Basic Tutorial: Section 3

## Description

This tutorial is made for those who have never used Xena but who have completed Section 1 of the Basic Tutorial. We will cover how to make box plots and bar charts using our Charts and Statistics View and how to add another column of data, in particular phenotype data, to the view.

## Prerequisites

This tutorial assumes you have done [Basic Tutorial: Section 1](basic-tutorial-section-1.md). [Basic Tutorial: Section 2](basic-tutorial-section-2.md) is recommended but not required. This tutorial begins where the Basic Tutorial: Section 2 ends. A live link to the end of Basic Tutorial: Section 2 is at the beginning of this tutorial.

## Estimated time needed

**Part A**: 5 min

**Part B**: 15 min

## Learning goals

**Part A**

* Create a box plot using the Charts and Statistics View

**Part B**

* Add another column of data to the view
* Add phenotype data to the view
* Create a bar chart using the Charts and Statistics View

## Tutorial

In the [Basic Tutorial: Section 1](basic-tutorial-section-1.md) we found that patient's samples that have aberrations in EGFR have higher expression. These aberrations could be mutations or copy number amplifications.&#x20;

In the [Basic Tutorial: Section 2](basic-tutorial-section-2.md) we created two subgroups: patient's samples that have aberrations in _EGFR_ and those without. We ran a Kaplan Meier survival analysis and found that there was no difference in survival between these two groups.&#x20;

Now we are going to use the subgroups created in the [Basic Tutorial: Section 2](basic-tutorial-section-2.md) to see if there is a statistical difference in gene expression between the two subgroups. We will also look at whether samples from male or female patients have more aberrations.

{% hint style="warning" %}
To ensure your columns are sorted the same as those in this tutorial, please start at this link: [https://xenabrowser.net/?bookmark=2862e84d66d5c2e1a99a44fd4e2c4045](https://xenabrowser.net/?bookmark=2862e84d66d5c2e1a99a44fd4e2c4045)
{% endhint %}

### Part A

We found that patient's samples that have aberrations in _EGFR_ have higher gene expression. Now we are going to investigate if this difference in gene expression statistically significant.

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=dc05bbdcf590f7df4506fbcd721f60b5)

![](../.gitbook/assets/screen-shot-2021-01-13-at-11.43.35-am.png)

We can now see that patient's samples with _EGFR_ aberrations have statistically higher gene expression.

#### Steps

1. Click the graph icon in the upper right corner to enter Chart View.
2. Click 'Compare subgroups', since we want to compare the group of samples who have aberrations in _EGFR_ to the group of samples that do not.
3. Click the dropdown for 'Show data from' and choose 'column C: EGFR - gene expression RNAseq - HTSeq - FPKM-UQ'.
4. Click the dropdown for 'Subgroup samples by' and choose 'column B: (mis OR infra) OR C:>0.5 - Subgroup'.
5. Click 'Done'.&#x20;

#### Video of steps

![](../.gitbook/assets/makeboxplot.gif)

{% hint style="success" %}
More information

* [Chart and Statistics View](../overview-of-features/chart-view.md)
{% endhint %}

### Part B

We will now investigate how _EGFR_ aberrations compare between samples from men and women.

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=8ac908b928e0332e8dfa3e306488d543)

![](../.gitbook/assets/screen-shot-2021-01-13-at-12.01.47-pm.png)

We can now see that _EGFR_ aberrations are more common in samples from females.

**Steps**

1. Click the 'x' in the upper right corner to exit Chart View.
2. Hover between columns B and C until 'Click to insert a column' becomes visible. Click on it.
3. Choose 'Phenotypic', type 'gender' into the search bar, select 'gender.demographic' from the dropdown menu, and click 'Done'.
4. Click the column menu at the top of column C and choose 'Chart & Statistics'. Note that this is just another way to enter Chart View.
5. Click 'Compare subgroups', since we want to compare the group of samples who have aberrations in _EGFR_ to the group of samples that do not.
6. 'column C: gender.demographic' should already be selected for  'Show data from'. If not, select it.
7. 'column B: (mis OR infra) OR C:>0.5 - Subgroup' should already be selected for 'Subgroup samples by'. If not, select it.
8. Click 'Done'.&#x20;

#### Video of steps 1-3

![](../.gitbook/assets/addgender.gif)

#### Video of steps 4-8

![](../.gitbook/assets/barchart.gif)

{% hint style="success" %}
More information

* [Chart and Statistics View](../overview-of-features/chart-view.md)
{% endhint %}

## Test your knowledge

{% tabs %}
{% tab title="Question 1" %}
Starting at the end of Part A, create a violin plot that compares copy number variation between patient's samples that have _EGFR_ aberrations and those that do not.
{% endtab %}

{% tab title="Answer 1" %}
\*\*\*\*[**Ending Screenshot**](https://xenabrowser.net/?bookmark=07b189f18423721b05c23fe4a1f0b0aa)\*\*\*\*

![](../.gitbook/assets/screen-shot-2021-01-13-at-2.20.27-pm.png)
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Question 2" %}
Starting at the end of Part B, add the phenotype data 'age\_at\_initial\_pathologic\_diagnosis' to the plot.
{% endtab %}

{% tab title="Answer 2" %}
\*\*\*\*[**Ending Screenshot**](https://xenabrowser.net/?bookmark=e3a364e74e74a9dbeb7f23b8c286456e)\*\*\*\*

![](../.gitbook/assets/screen-shot-2021-01-13-at-2.17.07-pm.png)

{% hint style="info" %}
Note that your column order may be different.
{% endhint %}
{% endtab %}
{% endtabs %}
