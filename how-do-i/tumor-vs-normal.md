# How do I compare tumor vs normal expression?

While TCGA is a good resource for tumor data, finding normal tissue expression data for comparision can be challenging. There are two main sources of normal expression data in Xena. The first is normal samples from TCGA itself. These samples are called "solid tissue normals" and are taken from normal tissues near the tumor. Solid tissue normal samples from TCGA are typically limited in number but some cancer types may have enough for a robust statistical comparison. Their proximity to tumor may introduce signals of tumor microenvironment in its transcriptome profile. The second way is to compare to [GTEx](https://gtexportal.org/home/) samples, which has expression data from normal tissue of individuals who do not have cancer. There are typically many more samples in GTEx then TCGA solid tissue normals, however, experimental sample processing are different from TCGA, which may lead to batch effects.

You can use the study below for both of these ways. Data from the study is from the UCSC RNA-seq Compendium, where TCGA and GTEx samples are re-analyzed \(re-aligned to hg38 genome and expressions are called using RSEM and Kallisto methods\) by the same RNA-seq pipeline. Because all samples are processed using an uniform bioinformatic pipeline, batch effect due to different computational processing is eliminated.

To compare tumor vs normal, you will need to use the [TCGA TARGET GTEx study](https://xenabrowser.net/?bookmark=057c5fe67d5d79488b843d7a6e1a9840), and then filter down to just the samples you want to compare. There are four gene expression datasets in this study. Two are normalized using with-in sample methods. The 'RSEM norm\_\_count' dataset is normalized by the upper quartile method, the 'RSEM expected\_\_count \(DESeq2 standardized\)' dataset is by DESeq2 normalization. Therefore, these two gene expression datasets should be used.

{% hint style="info" %}
Start with [this bookmark](https://xenabrowser.net/?bookmark=057c5fe67d5d79488b843d7a6e1a9840) and then filter from there
{% endhint %}

More information on how to filter can be found here:

[https://ucsc-xena.gitbook.io/project/overview-of-features/filter-and-subgrouping](https://ucsc-xena.gitbook.io/project/overview-of-features/filter-and-subgrouping)

More information on how to compare gene expression between subgroups of samples \(i.e. your subgroups\) can be found here:

[https://ucsc-xena.gitbook.io/project/how-do-i/how-do-i-compare-gene-expression-between-subgroups](https://ucsc-xena.gitbook.io/project/how-do-i/how-do-i-compare-gene-expression-between-subgroups)

## Walk-through example

In this example we will be looking to compare MYC gene expression between normal colon tissue from GTEx to TCGA colon adenocarcinoma.

### 1. Filter

Start with the [TCGA TARGET GTEx study](https://xenabrowser.net/?bookmark=057c5fe67d5d79488b843d7a6e1a9840), first, we filter the cohort and only keep the colon samples. The search term that was used to filter is: **colon**.

![](../.gitbook/assets/colonfilter.gif)

cheat link: [https://xenabrowser.net/?bookmark=9c75da8586d85ac10f1a6aa26059ba14](https://xenabrowser.net/?bookmark=9c75da8586d85ac10f1a6aa26059ba14)

### 2. Add gene

All we have to do now is to 'Click to Add Column' to add our favorite gene \(e.g. MYC\), click 'gene expression' and click 'Done'.

![](../.gitbook/assets/addgene.gif)

cheat link: [https://xenabrowser.net/?bookmark=25d653e7869a0a3e65f56b202aad30f6](https://xenabrowser.net/?bookmark=25d653e7869a0a3e65f56b202aad30f6)

### 3. Chart

Clicking on the 'Chart' in the upper right will make a box plot comparing average gene expression across our groups, complete with a p-value to test for significance.

![](../.gitbook/assets/chart.gif)

cheat link: [https://xenabrowser.net/?bookmark=c64978e15bfa3ac0d49d0fc84f74506c](https://xenabrowser.net/?bookmark=c64978e15bfa3ac0d49d0fc84f74506c)

