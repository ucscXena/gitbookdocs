---
description: >-
  How to find samples that you want to remove or keep in the view. How to make
  subgroups.
---

# Finding samples for filtering and subgrouping

## General Functionality

Use the search box at the top of the screen to first select/highlight your samples of interest and then either zoom, filter to just these samples, or create a new subgroup column.

![](../../.gitbook/assets/screen-shot-2021-01-19-at-3.36.32-pm.png)

This bar allows you to search all data on the screen for your search term of interest \(ie. 'female' or 'missense'\). You can also enter your sample ID to see where your sample of interest falls in the plot. Samples that match your criteria are highlighted and then marked with a black bar.

Once you have your sample\(s\) of interest, click on the filter button to choose from the options in the caret menu next to it to:

**Keep Samples:** Keep only the samples which match your criteria.

**Removes Samples:** Remove the samples which match your criteria.

**Clear Sample Filter:** Remove ALL filters currently applied.

**Zoom:** Zoom to the samples that meet your criteria. Shift-click to zoom out.

**New subgroup column:** Create a new column where samples that meet your criteria are annotated as 'true' and samples that don't meet your criteria are annotated as 'false'. This new columns can then be used for [Kaplan Meier Analysis](../kaplan-meier-plots.md) or in the [Chart View](../chart-view.md).

## Video Tutorial

Note that a new option in the filter and subgroup menu allows users to remove samples that match their search term. Video is otherwise relevant.

{% embed url="https://www.youtube.com/watch?v=P-MGKGuXZPo" caption="" %}

Here are the steps taken in the above walk-through:

1. Select the TCGA BRCA cohort
2. Select TP53 expression and mutation
3. Find samples where column B \(expression\) is less than 10 \(i.e. have relatively low expression\)
4. Find samples that have a nonsense or frame\_shift mutation for TP53
5. Filter down to just these samples
6. Clear this filter
7. Subgroup. Make a new column where the highlighted samples are marked as 'true' and those that are not are marked as 'false'.
8. Examine new subgroups in Chart mode

## Advanced Options once subgroups are created

Once the subgroup column is created, users can further customize group labels from "true" or "false" to for exmaple "wild type" or "EGFR mutant" by adjusting the column display settings. To access these select the three dot menu at the top of the column and choose 'Display'

There is also an advanced option to create multiple subgroups \(such as three, four, etc\). Please contact us for instructions on this beta feature!

