---
description: Under construction
---

# Basic Tutorial: Section 2

## Description

This tutorial is intended for those who have never used Xena before but who have completed Section 1 of the Basic Tutorial. We will cover how to filter to just the samples you are interested in, how to create subgroups, and how to run a Kaplan Meier survival analysis.

## Prerequisites

This tutorial assumes completion of the [Basic Tutorial: Section 1](basic-tutorial-section-1.md). This tutorial begins where the Basic Tutorial: Section 1 ends.

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

* Running a Kaplan Meier survival analysis
* Using a custom time endpoint

## Tutorial

In the Basic Tutorial Section 1 we found that we found that samples that have aberrations in _EGFR_ \(mutations or amplifications\) have higher expression.

Now we are going to investigate whether those samples with aberrations have a worse survival prognosis.

{% hint style="warning" %}
To ensure your columns are sorted the same as those in this tutorial, please start at this link: [https://xenabrowser.net/?bookmark=6b1057b1103e9995069e3dbdd7da83ba](https://xenabrowser.net/?bookmark=6b1057b1103e9995069e3dbdd7da83ba)
{% endhint %}

### Part A

Our goal is to remove samples with no data \(i.e. null\) from the view. This will make the view look cleaner and remove irrelevant samples from our Kaplan Meier survival analysis.

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=1420a515a2cd26f4bf12d267a857e5f8)

![https://xenabrowser.net/?bookmark=1420a515a2cd26f4bf12d267a857e5f8](../.gitbook/assets/screen-shot-2020-12-30-at-1.22.29-pm.png)

#### Steps

1. ... 
2. Delete the search term. This will remove the black tick marks for matching samples.

#### Video of steps

{% hint style="success" %}
**More information**

* [Searching for and filtering samples](../overview-of-features/filter-and-subgrouping.md)
{% endhint %}

### Part B

Our goal is to create two subgroups, those samples with aberrations in _EGFR_ and those samples without aberrations in _EGFR_. We will then name the subgroups.

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=2862e84d66d5c2e1a99a44fd4e2c4045)

![https://xenabrowser.net/?bookmark=2862e84d66d5c2e1a99a44fd4e2c4045](../.gitbook/assets/screen-shot-2020-12-30-at-1.28.28-pm.png)

#### Steps

1. **...**
2. Delete the search term. This will remove the black tick marks for matching samples.

#### Video of steps

### Part C

Now that we have our subgroups of those with and without aberrations in _EGFR_, we will run a Kaplan Meier survival analysis. Note that TCGA survival data is in days, hence the x-axis will be in days.

{% hint style="success" %}
**More information**

* [Kaplan Meier survival analysis](../overview-of-features/kaplan-meier-plots.md)
{% endhint %}

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=9e55264b9bd8b70efea1fc680a3bbf39)

![https://xenabrowser.net/?bookmark=9e55264b9bd8b70efea1fc680a3bbf39](../.gitbook/assets/screen-shot-2020-12-30-at-1.30.31-pm.png)

#### Steps

1. Click on the column menu at the top of column B
2. Choose 'Kaplan Meier Plot'
3. Click at the bottom of the Kaplan Meier plot on 'Custom survival time cutoff'
4. Enter 3650, as this is 10 years

#### Video of steps

## Test your knowledge

{% tabs %}
{% tab title="Question 1" %}
Starting at the end of Part A, filter down to only those samples that have a missense mutation.
{% endtab %}

{% tab title="Answer 1" %}

{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Question 2" %}
Starting at the end of Part A, create two subgroups: those with _EGFR_ expression greater than 17 and those with _EGFR_ expression less than 17.
{% endtab %}

{% tab title="Answer 2" %}

{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Question 3" %}
Starting at the end of Part A, run a Kaplan Meier analysis on _EGFR_ expression column.
{% endtab %}

{% tab title="Answer 3" %}

{% endtab %}
{% endtabs %}

