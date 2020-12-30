---
description: Under construction
---

# Basic Tutorial: Section 2

## Description

This tutorial is intended for those who have never used Xena before but who have completed Section 1 of the Basic Tutorial. We will cover how to filter to just the samples you are interested in, how to create subgroups, and how to run a Kaplan-Meier survival analysis.

## Prerequisites

This tutorial assumes completion of the [Basic Tutorial: Section 1](basic-tutorial-section-1.md).

## Estimated time needed

**Part A**: 15 min

**Part B**: 15 min

**Part C:** 5 min

## Learning goals

### Part A

* Search for samples of interest
* Filter to keep or remove those samples of interest

### Part B

* Make subgroups
* Renaming subgroups

### Part C

* Running a Kaplan-Meier survival analysis
* Using a custom time endpoint

## Tutorial

In section 1 we found that we found that samples that have aberrations in EGFR \(mutations or amplifications\) have higher expression.

Now we are going to investigate whether those samples with aberrations have a worse survival prognosis.

### Part A

Our goal is to build a Visual Spreadsheet and understand the relationship between the columns

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=6b1057b1103e9995069e3dbdd7da83ba)

![https://xenabrowser.net/?bookmark=6b1057b1103e9995069e3dbdd7da83ba](../.gitbook/assets/screen-shot-2020-12-29-at-1.08.37-pm.png)

#### Steps

1. Start at our home page [http://xena.ucsc.edu/](http://xena.ucsc.edu/) and click on 'Launch Xena'. You are now in our Visual Spreadsheet Wizard.
2. Type 'GDC TCGA Lung Adenocarcinoma', select this study from the drop down menu, and click 'Done'
3. Type 'EGFR', select the checkboxes for Gene Expression, Copy Number, and Somatic Mutation, and click 'Done'

#### Video of steps

![](../.gitbook/assets/basictutorialpart1a.gif)

#### How to read a Visual Spreadsheet

Samples are on the y-axis and your columns of data are on the x-axis. We line up all columns so that each row is the same sample, allowing you to easily see trends in the data. Data is always sorted left to right and sub-sorted on columns thereafter.

#### Biological interpretation

We can see that samples that have high expression of _EGFR_ \(red, column B\) tend to either have amplifications of _EGFR_ \(red,  column C\) or mutations in _EGFR_ \(blue tick marks, column D\)

{% hint style="success" %}
More information:

* [Visual Spreadsheet](../overview-of-features/visual-spreadsheet/#after-you-made-a-visual-spreadsheet)
* [Colors and values in columns](../overview-of-features/visual-spreadsheet/#data-values)
* [Sample sorting](../overview-of-features/visual-spreadsheet/#sample-sorting)
{% endhint %}

### Part B

To further explore the relationship between the gene expression, mutation, and copy number variation data for _EGFR_, we will move columns to change the sort order, resize columns, and zoom in both for the entire Visual Spreadsheet and within a column.

#### Steps

1. **Move columns.** Click on column C, copy number variation, and drag it to the left so that it becomes the first column after the samples column \(i.e. column B\). Note that the samples are now sorted by the values in this column.
2. **Resize columns.** Click on the handle in the lower right corner of column D, mutation. Move it to the right to make the column bigger. 
3. **Zoom in on a column.** Click and drag within column D. Release to zoom.
4. **Zoom out on a column.** Click the red zoom out text at the top of column D.
5. **Zoom in on samples.** Click and drag vertically in any column in the Visual Spreadsheet to zoom in on these samples.
6. **Zoom out on samples.** To zoom out click either 'Zoom out' or 'Clear zoom' at the top of the Visual Spreadsheet.

#### Video of step 1

#### Video of step 2

#### Video of steps 3-6

## Test your knowledge

