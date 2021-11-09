# Kaplan Meier Plots

Kaplan Meier Survival Analyses are a way of comparing the survival of groups of patients. More information on what a Kaplan Meier analysis is can be found in [this article](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3932959/)

## Generating a plot

To generate a KM plot, click on the column menu at the top of a column and choose 'Kaplan Meier Plot'.&#x20;

![](<../.gitbook/assets/kmplot (2) (1).gif>)

## Features

### Sample groups

For numerical or continuous features, you will have the option of having 2 groups of samples, 3 groups of samples, or viewing the upper vs lower quartile. For 2 groups, we divide the samples on the median. For 3 groups, we divide samples into the upper third, middle third, and lower third. When viewing the upper vs lower quartile, note that we only include samples that are greater than (not greater than or equal to) the upper quartile, and the same for the lower quartile.

If more than one sample has the same value, we put the samples in a group together, even if this means the groups end up being unequal in size.

For categorical features, we only show the first 10 categories.

For mutation features, we divide samples into those with any mutation and those without. To make more refined groups (e.g. samples with nonsense mutations vs those without), [create your own subgroups ](filter-and-subgrouping/)and run a KM plot on the new column

We remove samples with 'null' data for all plots.

### Type of survival

We default to Overall Survival. Users can select different end points if they are available. An example of this is in the [TCGA PanCancer Study](https://xenabrowser.net/heatmap/?bookmark=bdfafba0e4256523a202948e8fa5d26c).

### Survival time cutoff

We default to the last time any individual in the plot was known to be alive. You can change this to be 1-year or 5-year survival by changing the time cutoff at the bottom of the screen. The statistics will automatically recalculate. TCGA data uses days as their measurement of time.

### PDF

You can generate a high quality PDF by clicking the PDF icon.

### Download

You can download the data used to generate the KM plot using the download icon. It will download the [Event and Time to Event columns](../local-xena-hub/km-plots-using-data-from-a-local-xena-hub.md#time-to-event-and-event), in addition to the sample ID, patient ID, groups, and underlying data.

## Statistics used

When there are multiple curves or lines in a KM plot, Xena Browser compares the different Kaplan–Meier curves using the log-rank test. The Browser reports the test statistics (𝜒 2) and p-value (𝜒 2 distribution). Data is retrieved in real-time from Xena Hub(s) to a user's web browser and the test is performed in the browser to maintain your data privacy.

The statistics the Xena Browser reports are equivalent to R's survival package, [survdiff](https://stat.ethz.ch/R-manual/R-devel/library/survival/html/survdiff.html), with rho=0 (default in R).

### **Exceptions**

If all patients in a particular group (i.e. line) are censored before any event happens for the whole population (including all the groups), we exclude this group from the statistical analysis and perform the log-rank test on the remaining groups. We do this because we have no way to know the number of people at risk for this particular group at any of event times, and therefore can not compute any statistics for this group. R handles this exception in the same way. Although this group is removed from the statistical analysis, we still display the group in the KM plot.

## Duplicate samples

Note that we do not automatically remove duplicate patients (for instance if there is a tumor and a normal sample from the same patient). You can determine if there are duplicate patients by looking for the "!" icon next to the p value. [Learn how to remove duplicate samples](../how-do-i/how-do-i-remove-duplicate-samples-from-a-km-plot.md).

## More information on how to load your own survival data into Xena

{% content-ref url="../local-xena-hub/km-plots-using-data-from-a-local-xena-hub.md" %}
[km-plots-using-data-from-a-local-xena-hub.md](../local-xena-hub/km-plots-using-data-from-a-local-xena-hub.md)
{% endcontent-ref %}
