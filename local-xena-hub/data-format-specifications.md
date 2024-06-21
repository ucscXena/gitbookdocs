# Data format specifications and supported biological data types

There are 2 basic data formats and 2 advanced data formats. Each of these formats has one or more biological data types that it supports.

## General Specifications for all data formats

We support most types of genomic and phenotype/clinical/sample annotations. For genomic data we support calls made on the raw data including but not limited to expression calls, mutation calls, etc. This is what TCGA calls ‘Level 3’ data and is typically a value on gene, transcript, probe, etc. We do not support FASTQ, BAMs, or other ‘raw’ files. Please contact us if you have any questions.

We support tab-delimited and Microsoft Excel files (.xlsx and .xls). Tab-delimited files generally have a file name ending in .tsv or .txt, though we do not require this. Note that we load tab-delimited files much faster than Excel files. You can export a Microsoft Excel file as a tab-delimited file using the 'Save as ...' function.

Please do not have any duplicate genes/probes/identifiers or samples. We will allow you to load with duplicates but will only display the first one encountered in the file.

We assume you use a '.' to indicate a decimal place as opposed to a ',' .

Here is a[ folder](https://drive.google.com/file/d/0BxeGFxkAhivXVkwyMmh2cVZ6U00) with example data in addition to the examples below.

## **Basic Genomic data: numbers in a rectangle/matrix/spreadsheet**

These are numeric data called on genomic regions (e.g. exon expression or gene-level copy number). This data is in a rectangle where samples are columns and rows are the genomic regions (e.g. HUGO gene symbol, transcript ID, probe ID, etc). We also support samples as rows and genomic regions as the columns (i.e. the opposite orientation). For supported genomic regions, please see [supported gene and probe names](supported-gene-and-probe-names.md).

### Supported data types

* RNA-seq expression (exon, transcript, gene, etc)
* Array-based expression (probe, gene, etc)
* Gene-level mutation
* Gene-level copy number
* DNA methylation
* RPPA
* and more ...

[Contact us](../contact-us.md) if you're unsure if we will support your data

{% hint style="info" %}
For samples that do not have expression for a particular gene, either have a blank field or use "NA".
{% endhint %}

An example of a genomic matrix file (in this case, expression):

| **Sample** | **TCGA-BA-4074-01** | **TCGA-BA-4075-01** | **TCGA-BA-4076-01** |
| ---------- | ------------------- | ------------------- | ------------------- |
| **ACAP3**  | **0.137**           | **NA**              | **0.022**           |
| **CTRT2**  | **0.024**           | **0.805**           | **0.256**           |
| **ALK**    | **0.098**           | **0.805**           | **1.87**            |

## Basic Phenotypic data: categories or non-genomic in a rectangle/**matrix/spreadsheet**

These are data on a sample or patient that is categorical in nature (e.g. Tumor Stage or 'wild type' or 'mutant' for a gene) or is numerical but non-genomic (e.g. age or a genomic signature). Samples can be columns and rows can be phenotype/clinical/sample orientation or vice versa. We support both orientations.

### Supported data types

* phenotype/patient/clinical data (age, weight, if there was blood drawn, etc)
* sample/aliquot data (where it was sequenced, tumor weight, etc)
* derived data (regulon activity for a gene, etc)
* genomic signatures (EMT signature score, stemness score, etc)
* other (whether a sample has an ERG-TMPRSS2 fusion, whether a sample has WGS data available, etc)

This is our most flexible data type. If you are wondering if your data is considered to be 'phenotypic' please [contact us](../contact-us.md).

### Categorial vs numerical data

We support both numerical and categorical data. For numerical data please use a blank field for any samples which may be missing data. For categorical data you can use a blank field or "NA" for any samples which may be missing data.&#x20;

{% hint style="info" %}
Note that if you use "NA" for a missing numerical field then the Xena software will automatically treat that column as a category.&#x20;
{% endhint %}

To have it be treated as a numerical field please use a blank field.

{% hint style="info" %}
For more information about configuring your phenotype fields, such as controlling the order for categorical features, please see our [Metadata Specifications](../technical-documentation/metadata-specification-1.md#custom-categorical-phenotype).
{% endhint %}

An example of a phenotype matrix file:

| **sample**          | **ER\_status** | **disease\_status**      | **age** |
| ------------------- | -------------- | ------------------------ | ------- |
| **TCGA-BA-4074-01** | **positive**   | **complete remission**   | **63**  |
| **TCGA-BA-4082-01** | **positive**   | **complete remission**   | **54**  |
| **TCGA-BA-4078-01** | **negative**   | **undergoing treatment** | **65**  |

## **Advanced Segmented data**

For segmented data, we require the following 5 columns: sample, chr, start, end, and value. Note that your column headers must be these names exactly!

Please use 'NA' to indicate no data.

### Supported data types

* copy number

We currently accept hg38, hg19, hg18 coordinates.

Example segmented copy number data with required columns:

| **sample**          | **chr**  | **start**    | **end**       | **value**   |
| ------------------- | -------- | ------------ | ------------- | ----------- |
| **TCGA-V4-A9EL-01** | **chr1** | **61735**    | **16815530**  | **0.041**   |
| **TCGA-V4-A9EL-01** | **chr1** | **16816090** | **17190862**  | **-0.4227** |
| **TCGA-V4-A9EF-01** | **chr4** | **86979944** | **115173700** | **0.0414**  |

## **Advanced Positional data**

For positional data, we require 6 columns: sample, chr, start, end, reference, alt. Note that your column headers must be these names exactly!

Other columns that may follow are: gene, effect, DNA\_VAF, RNA\_VAF, and Amino\_Acid\_Change. These other columns are not required but will enhance the visualization of this data, such as the "gene" column will enable displaying mutations when queried by gene names in addition to queried by genomic coordinates. The “effect” column will color the mutations by effect (the default color is gray). The effect terms are "Nonsense" (color red), "Frameshift" (red), "Splice" (orange), "missense" (blue), "Silent" (green), and etc. The full list of accepted terms can be found [here in our code](https://github.com/ucscXena/ucsc-xena-client/blob/master/js/models/mutationVector.js#L85).

{% hint style="info" %}
Note that Xena will not call the gene, variant effect, etc for you. All gene annotation information must be included in the file
{% endhint %}

### Supported data types

* mutation data

We currently accept hg38, hg19, hg18 coordinates.

Example mutation data with the six required columns, plus the gene column:

| **sample**          | **chr**  | **start**     | **end**       | **reference** | **alt** | **gene**  |
| ------------------- | -------- | ------------- | ------------- | ------------- | ------- | --------- |
| **TCGA-AB-2802-03** | **chr2** | **29917721**  | **29917721**  | **G**         | **A**   | **ALK**   |
| **TCGA-AB-2802-03** | **chr1** | **119270684** | **119270687** | **TTAAA**     | **T**   | **MYC**   |
| **TCGA-AB-2867-03** | **chr1** | **150324146** | **150324146** | **T**         | **G**   | **PRPF3** |

{% hint style="info" %}
To specify a sample is assayed but no mutation is detected, you need a line in the file with three columns filled: sample, start, end. "start" and "end" are required to be integer (if left empty, the data loader will reject the file), so use -1 to indicate that these are bogus coordinates. The rest of the columns are empty strings.
{% endhint %}

## **Advanced Other data**

We support a number of other specialty data types such as structural variants. Please [contact us](../contact-us.md) if you have this data so we can help you load it.
