# How do I compare tumor vs normal expression?

## TCGA matched normal vs. GTEx normal

While TCGA is a good resource for tumor data, finding normal tissue expression data for comparison can be challenging. There are two main sources of normal expression data in Xena. The first is normal samples from TCGA itself. These samples are called "solid tissue normals" and are taken from normal tissues near the tumor. Solid tissue normal samples from TCGA are typically limited in number but some cancer types may have enough for a robust statistical comparison. Their proximity to tumor may introduce signals of tumor microenvironment in its transcriptome profile. The second way is to compare to [GTEx](https://gtexportal.org/home/) samples, which has expression data from normal tissue of individuals who do not have cancer. There are typically many more samples in GTEx then TCGA solid tissue normals, however, experimental sample processing are different from TCGA, which may lead to batch effects.

## Using the  TCGA TARGET GTEx study

You can use the  [TCGA TARGET GTEx study](https://xenabrowser.net/?bookmark=057c5fe67d5d79488b843d7a6e1a9840) for both types of 'normal' samples. Data from the study is from the UCSC RNA-seq Compendium, where TCGA, TARGET, and GTEx samples are re-analyzed \(re-aligned to hg38 genome and expressions are called using RSEM and Kallisto methods\) by the same RNA-seq pipeline. Because all samples are processed using a uniform bioinformatic pipeline, batch effect due to different computational processing is eliminated.

To compare tumor vs normal, you will need to filter down to just the samples you want to compare and then compare gene expression between your groups of samples.

{% hint style="info" %}
More information:

* [Filtering and subgrouping](../overview-of-features/filter-and-subgrouping/)
* [Compare gene expression between subgroups](how-do-i-compare-gene-expression-between-subgroups.md)
{% endhint %}

There are four gene expression datasets in this study. Two are normalized using with-in sample methods. The 'RSEM norm\_\_count' dataset is normalized by the upper quartile method, the 'RSEM expected\_\_count \(DESeq2 standardized\)' dataset is by DESeq2 normalization. Therefore, these two gene expression datasets should be used.

## Running a Differential Gene Expression Analysis

If you are looking to compare just a few genes, you can use our [chart view](../overview-of-features/chart-view.md) to run your analysis. If you are looking to run a genome-wide differential gene expression analysis, you can use our [DEA feature](../overview-of-features/differential-gene-expression.md). Note that we only allow users to run our Differential Gene Expression Analysis on less than 2,000 samples total. Thus, you will need to filter to run this analysis on this dataset.

{% hint style="info" %}
More information:

* [Filtering and subgrouping](../overview-of-features/filter-and-subgrouping/)
* [Running a Differential Gene Expression Analysis](../overview-of-features/differential-gene-expression.md)
{% endhint %}

## Walk-through example

In this example we will be looking to compare _MYC_ gene expression between normal colon tissue from GTEx to TCGA colon adenocarcinoma.

### 1. Filter

Start with the [TCGA TARGET GTEx study](https://xenabrowser.net/?bookmark=057c5fe67d5d79488b843d7a6e1a9840), first, we filter the cohort and only keep the colon samples. The search term that was used to filter is: **colon**.

![](../.gitbook/assets/colonfilter.gif)

cheat link: [https://xenabrowser.net/?bookmark=9c75da8586d85ac10f1a6aa26059ba14](https://xenabrowser.net/?bookmark=9c75da8586d85ac10f1a6aa26059ba14)

### 2. Add gene

Click 'Click to Add Column',  add a gene \(e.g. _MYC_\), click 'gene expression' and click 'Done'.

![](../.gitbook/assets/addgene.gif)

Link to ending screen: [https://xenabrowser.net/?bookmark=25d653e7869a0a3e65f56b202aad30f6](https://xenabrowser.net/?bookmark=25d653e7869a0a3e65f56b202aad30f6)

### 3. Chart

1. Click the graph icon in the upper right corner to enter Chart View.
2. Click 'Compare subgroups', since we want to compare tumor vs normal samples
3. Click the dropdown for 'Show data from' and choose 'column F: MYC - gene expression RNAseq - RSEM norm\_count'.
4. Click the dropdown for 'Subgroup samples by' and choose 'column C: Sample Type'.
5. Click 'Done'. 

Link to ending screen: [https://xenabrowser.net/?bookmark=c64978e15bfa3ac0d49d0fc84f74506c](https://xenabrowser.net/?bookmark=c64978e15bfa3ac0d49d0fc84f74506c)

