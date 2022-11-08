# How do I compare tumor vs normal expression?

## TCGA matched normal vs. GTEx normal

There are two main sources of normal expression data in Xena. The first is matched normal tissue samples from TCGA patients. These patient's samples are called "solid tissue normals" and are taken from tissue near the tumor. Normal samples from TCGA patients are typically limited in number but some cancer types may have enough for a robust statistical comparison. It is important to note that their proximity to tumor means it may have tumor microenvironment signal. The second source of normal expression is [GTEx](https://gtexportal.org/home/). GTEx has expression data from normal tissue of individuals who do not have cancer. There are typically many more samples in GTEx then in TCGA solid tissue normals. However, experimental sample processing are different from TCGA, which may lead to batch effects.

## Using the  TCGA TARGET GTEx study

You can use the  [TCGA TARGET GTEx study](https://xenabrowser.net/?bookmark=057c5fe67d5d79488b843d7a6e1a9840) for both types of 'normal' samples. Data from the study is from the UCSC RNA-seq Compendium, where TCGA, TARGET, and GTEx samples are re-analyzed by the same RNA-seq pipeline. This pipeline involved re-aligning the reads to hg38 genome and calling gene expression using RSEM and Kallisto methods. Because all samples are processed using a uniform bioinformatic pipeline, batch effects due to different computational processing is eliminated. Note that the samples from this study have only undergone per-sample normalization.

To compare tumor vs normal, you will need to filter down to just the samples you want to compare and then compare gene expression between your groups of samples.

{% hint style="info" %}
More information:

* [Filtering and subgrouping](../overview-of-features/filter-and-subgrouping/)
* [Compare gene expression between subgroups](how-do-i-compare-gene-expression-between-subgroups.md)
{% endhint %}

There are four gene expression datasets in this study. Two are normalized using with-in sample methods. The 'RSEM norm\_\_count' dataset is normalized by the upper quartile method, the 'RSEM expected\_\_count (DESeq2 standardized)' dataset is by DESeq2 normalization. Therefore, these two gene expression datasets should be used.

## Running a Differential Gene Expression Analysis

If you are looking to compare just a few genes, you can use our [chart view](../overview-of-features/chart-view.md) to run your analysis. If you are looking to run a genome-wide differential gene expression analysis, you can use our [DEA feature](../overview-of-features/differential-gene-expression.md). Note that we only allow users to run our Differential Gene Expression Analysis on less than 2,000 samples total. Thus, you will need to filter to run this analysis on this dataset.

{% hint style="info" %}
More information:

* [Filtering and subgrouping](../overview-of-features/filter-and-subgrouping/)
* [Running a Differential Gene Expression Analysis](../overview-of-features/differential-gene-expression.md)
{% endhint %}

## Tutorial

{% content-ref url="../tutorials/tutorial-tumor-vs-normal.md" %}
[tutorial-tumor-vs-normal.md](../tutorials/tutorial-tumor-vs-normal.md)
{% endcontent-ref %}
