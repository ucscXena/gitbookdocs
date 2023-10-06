---
description: Run a genome-wide differential GSEA analysis to compare groups of samples
---

# GSEA

To run a GSEA analysis, click on the 3 dot column menu at the top of a categorical column (not a numerical column) and choose 'GSEA'.

This will take you to new page where you will define the sample subgroups you would like to compare (note that you can select multiple categories for a single subgroup).

After you have your subgroups, choose a gene set library, scroll to the bottom and click 'submit'.

{% hint style="warning" %}
Due to compute limitations you can only run a total of 2000 samples through the analysis pipeline.
{% endhint %}

This will start the analysis, which make take a while to run depending on the size of the dataset. As the results are completed, the web page will update. Scroll to see more results. Once the analysis is finished it will say 'Done' at the top of the page.

## More details

The gene expression dataset chosen for a specific study/cohort is the same gene expression dataset as the one in the [Basic Datasets menu](visual-spreadsheet/#selecting-a-dataset).&#x20;

The Advanced Visualization parameters apply to the PCA or t-SNE plot, as well as the blitzGSEA analysis itself.&#x20;

Note that the GSEA analysis runs [blitzGSEA](https://academic.oup.com/bioinformatics/article/38/8/2356/6526383), a faster implementation of a traditional GSEA analysis.

## Running it on your own data

We disable running our GSEA analysis on your own data since we send the data in the analysis to various websites, which may not be secure. Currently we only offer a [docker image](https://gallery.ecr.aws/f8e3p8q3/xenablitzgsea) as a method for running this pipeline on your own data. Please contact us if you need help setting this up.&#x20;
