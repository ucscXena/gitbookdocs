# Basic data and datasets

## What does the value of 0.5 mean for this dataset \(expression, CNV, methylation\)?

Individual values for each dataset mean different things. There is some information in the legend at the bottom of the dataset. If this does not answer your question we recommend going to the dataset details page to learn more about the dataset. To get there, click on the column menu and choose 'About'.

![How to access the About menu](../.gitbook/assets/aboutmenu%20%281%29.gif)

You may also need to read the paper or otherwise search the internet for more information on a particular method or units \(e.g. such as GISTIC 2\).

## How can find out more about data behind a column?

We recommend going to the dataset details page to learn more about a dataset. To get there, click on the column menu and choose 'About'.

![](../.gitbook/assets/aboutmenu%20%282%29.gif)

## What normalization was performed on this dataset?

We list the units and normalization at the bottom of the column. You can also go to the dataset details page to learn more about a dataset. To get there, click on the column menu and choose 'About'.

![](../.gitbook/assets/aboutmenu.gif)

## How do I calculate fold change \(FC\)?

The following instructions assume that your data has been log transformed. All the RNAseq data in Xena public data hubs have already been log transformed, either by us or by the data providers. You can always confirm this by viewing the dataset details page \(start at our [Explore Data pages](https://xenabrowser.net/datapages/) and drill down until you get to the details page for the dataset\).

Log transformed means that the output values from the gene expression caller/program have been put through the following transformation:

> log2\(x+theta\) = y

Where x is the TPM, RSEM, etc value, "theta" is a very small value \(1, 0.01, etc\) added to x since you can not take the log of zero, "log2" is log base 2, and y is the transformed value.

When comparing these log transformed values, we use the [quotient rule of logarithms](https://en.wikipedia.org/wiki/List_of_logarithmic_identities#Using_simpler_operations):

> log\(A/B\) = log\(A\) - log\(B\)

So, within our downloads \(either from our bulk downloads or just a slice of the data that has not been mean normalized\), say you have 2 samples with expression for a gene. In our downloads, one sample is 4 and one sample is 1. This means, because our values are log transformed,

> log\(A\) = 4
>
> log\(B\) = 1

Therefore:

> log\(A/B\) = 4 - 1
>
> log\(A/B\) = 3

This gives you a 3-fold change.

Please note that in this case we are reporting the log\(fold change\). Biologists often use the log\(fold change\) because without taking the log, down regulated genes would have values between 0 and 1, whereas up regulated genes would have any value between 1 and infinity. This distribution makes graphing and further statistical analysis difficult. Taking the log typically makes the resulting values more normally distributed, which is better for further analysis.



