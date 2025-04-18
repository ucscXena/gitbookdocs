---
description: >-
  Learn how to remove samples with no data, subgroup samples, and make Kaplan
  Meier plots
---

# Basic Tutorial: Section 2

## Description

This tutorial is made for those who have never used Xena but who have completed Section 1 of the Basic Tutorial. We will cover how to filter to just the samples you are interested in, how to create subgroups, and how to run a Kaplan Meier survival analysis.

## Prerequisites

This tutorial assumes completion of the [Basic Tutorial: Section 1](basic-tutorial-section-1.md). This tutorial begins where the Basic Tutorial: Section 1 ends.

## Estimated time needed

**Part A**: 7 min

**Part B**: 15 min

**Part C:** 5 min

## Learning goals

**Part A**

* Search for samples of interest
* Remove samples with no data

**Part B**

* Make subgroups
* Rename subgroups

**Part C**

* Run a Kaplan Meier survival analysis
* Use a custom time endpoint

## Tutorial

In the Basic Tutorial Section 1 we found that we found that samples from patients that have aberrations in _EGFR_ have relatively higher expression. These aberrations could be mutations or copy number amplifications.&#x20;

Now we are going to look at whether those patient with aberrations in their samples also have a worse survival prognosis.

{% hint style="warning" %}
To ensure your columns are sorted the same as those in this tutorial, [please start at this link](https://xenabrowser.net/?bookmark=373e6aac9ce49ce3420c95e81d1eb686)
{% endhint %}

### Part A

Our goal is to remove patient's samples with no data (i.e. null) from the view. This will make the view look cleaner and remove irrelevant samples from our Kaplan Meier survival analysis.

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=c892731ed5eb7dfe875146d0aca87bc3)

<figure><img src="../.gitbook/assets/Screenshot 2024-10-14 at 5.05.09 PM.png" alt=""><figcaption></figcaption></figure>

#### Steps

1. Type 'null' into the samples search bar. This will highlight samples that have 'null' values in any column on the screen. Null means that there is no data for that sample for that column.
2. Click the filter menu and select 'Remove samples'.
3. Delete the search term.

#### Video of steps

<figure><img src="../.gitbook/assets/tutorial2.1.gif" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
More information

* [Filtering and subgrouping samples](../overview-of-features/filter-and-subgrouping/)
* [Supported search terms](../overview-of-features/filter-and-subgrouping/supported-search-terms-for-finding-samples.md)
{% endhint %}

#### Shortcut for Part A

Instead of typing 'null' and removing those samples from the view, you can also use the 'Remove samples with nulls' shortcut in the filter menu.

<figure><img src="../.gitbook/assets/tutorial2.2.gif" alt=""><figcaption></figcaption></figure>

### Part B

Our goal is to create two subgroups, those patient's with samples with aberrations in _EGFR_ and those patient's samples without aberrations in _EGFR_. We will then name the subgroups.

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=d29d9b70671ac2af3dda01a7448be38f)

<figure><img src="../.gitbook/assets/Screenshot 2024-10-14 at 5.19.03 PM.png" alt=""><figcaption></figcaption></figure>

#### Steps

1. Type **'**(mis OR inframe) OR B:>0.5'  into the samples search bar. This will select samples that either have a missense or inframe deletion '(mis OR inframe)', or where copy number variation (column B) is greater than 0.5. Note that I arbitrarily choose a cutoff of 0.5.

{% hint style="danger" %}
You must have the **copy number variation column as column B** for the search term  **'**(mis OR inframe) OR B:>0.5' to work. The 'B' in 'B:>0.5' is instructing Xena to search in column B for values that are greater than 0.5.
{% endhint %}

1. Click the filter menu and select 'New subgroup column'. This will create a new column that has samples that met our search term marked as 'true' (ie. those that have an _EGFR_ aberration) and those that did not meet our search term as 'false' (ie. those that do not have an _EGFR_ aberration).
2. Click the column menu for the column we just created (column B) and chose 'Display'.
3. Rename the display so that samples that are 'true' are instead labeled as 'EGFR Aberrations' and the samples that are 'false' are instead labeled as 'No EGFR Aberrations'. Click 'Done'
4. Delete the search term. This will remove the black tick marks for matching samples.

#### Video of steps 1

<figure><img src="../.gitbook/assets/tutorial2.3.gif" alt=""><figcaption></figcaption></figure>

#### Video of steps 2-4

<figure><img src="../.gitbook/assets/tutorial2.4.gif" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
More information

* [Filtering and subgrouping samples](../overview-of-features/filter-and-subgrouping/)
* [Supported search terms](../overview-of-features/filter-and-subgrouping/supported-search-terms-for-finding-samples.md)
{% endhint %}

### Part C

Now that we have our subgroups we will run a Kaplan Meier survival analysis. Note that TCGA survival data is in days, hence the x-axis will be in days.

#### [Ending Screenshot](https://xenabrowser.net/?bookmark=6787986724f81fd87d64980ff8ef85e9)

<figure><img src="../.gitbook/assets/Screenshot 2024-10-14 at 5.22.24 PM.png" alt=""><figcaption></figcaption></figure>

We can now see that there is no difference in survival between patients with _EGFR_ aberrations and those without.

#### Steps

1. Click the column menu at the top of column B.
2. Choose 'Kaplan Meier Plot'.
3. Click 'Custom survival time cutoff' at the bottom of the Kaplan Meier plot.
4. Enter 3650, as this is 10 years.

#### Video of steps

<figure><img src="../.gitbook/assets/tutorial2.5.gif" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
More information

* [Kaplan Meier survival analysis](../overview-of-features/kaplan-meier-plots.md)
{% endhint %}

## Test your knowledge

{% tabs %}
{% tab title="Question 1" %}
Starting at the end of Part A, filter down to only those patient's samples that have a missense mutation.
{% endtab %}

{% tab title="Answer 1" %}
Search term: "missense"

[**Ending screenshot**](https://xenabrowser.net/?bookmark=14d3d143685004f3c61e40c3cdaa4855)

<figure><img src="../.gitbook/assets/Screenshot 2024-10-14 at 5.25.12 PM.png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Question 2" %}
Starting at the end of Part A, create two subgroups: those patient's samples with _EGFR_ expression greater than 4 and those with _EGFR_ expression less than 4.
{% endtab %}

{% tab title="Answer 2" %}
Search term: "C:>4"

[**Ending screenshot**](https://xenabrowser.net/?bookmark=5bc9a8c614a34134a56b51df73c9aaa2)

<figure><img src="../.gitbook/assets/Screenshot 2024-10-14 at 5.27.19 PM.png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Question 3" %}
Starting at the end of Part A, run a Kaplan Meier analysis on the _EGFR_ expression column.
{% endtab %}

{% tab title="Answer 3" %}
[**Ending screenshot**](https://xenabrowser.net/?bookmark=8c5344fd189aa168bd4e8495e2c42963)

<figure><img src="../.gitbook/assets/Screenshot 2024-10-14 at 5.28.48 PM.png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}
