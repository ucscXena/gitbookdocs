# Overview of Visual Spreadsheet

This dynamic, powerful, and flexible view is our default view into the data.

The Visual Spreadsheet allows you to add an arbitrary number of columns of any data type \(mutation, copy number, expression, protein, phenotype, methylation, etc\) into a spreadsheet-like view. We line up all columns so that each row is the same sample, allowing you to easily see trends in the data. Data is always sorted left to right and sub-sorted on columns thereafter.

Get started by going to the [Xena Browser](https://xenabrowser.net/heatmap/) and following the wizard to enter your data of interest.

## Making a Visual Spreadsheet

### Selecting a cohort

### Adding a Gene or Position

### Selecting a Dataset

#### Basic Datasets

We have pre-selected default datasets for most cohorts. These datasets are selected based because they are the most used datasets. Typically there is a default mutation, copy number, and expression dataset.

#### Advanced Datasets

Xena also has more datasets than those listed in the Basic Menu. Depending on the cohort, these can include DNA methylation, exon expression, thresholded CNV data and more. To access them, click on 'Show Advanced' below:

![Creating a column with the Advanced Dataset selection highlighted](../../.gitbook/assets/advancedmenu.png)

#### **More information on basic datasets**

We annotate datasets used in the basic Visual Spreadsheet wizard with a red asterisk in our datasets pages. For an example see: [https://xenabrowser.net/datapages/?cohort=TCGA%20Acute%20Myeloid%20Leukemia%20\(LAML\)](https://xenabrowser.net/datapages/?cohort=TCGA%20Acute%20Myeloid%20Leukemia%20%28LAML%29)

![Red asterisk indicating this dataset is the one used in the Basic Wizard](../../.gitbook/assets/redasterisk.png)

## After you made your Visual Spreadsheet

### Sample sorting

The Xena Browser uses y axis for samples, x axis/columns for genomic/phenotypic features. Data from a single sample is always on the same horizontal line across all columns. Linking samples across columns allows you to see screen-wide trends. The Xena Browser orders samples left to right first by the first columns, then the second, etc. If there are multiple genes, identifiers, probes within in a column, samples is ordered from left to right by 1st sub-column, then 2nd sub-column, and so on. 

Numerical data \(e.g. 1.2, 3.5, etc\) are ordered in descending order \(e.g. 3.5, 1.2, ...\). Categorical data \(e.g. stage, tumor type, etc\) are ordered by categories. CNV data is sorted by the average of the entire column. Positional mutation data is ordered by by genomic coordinates \(from 5'-&gt;3'\) and then by type of mutation \(mutations that destroy the transcript such as frameshift, mutations that change the transcript such as missense, silent mutations such as UTR mutations\). For both the CNV and positional mutation data, you can choose to instead sort by the region you are zoomed to. Click the columns menu at the top of the column and choose  'Sort by zoom region avg'.

To reverse the ordering for any column, click the column menu at the top of the column and chose 'Reverse sort'

### Zooming

Click and drag any where in any column to zoom in in either direction. Zoom out to all samples by clicking the 'Clear Zoom' at the top. Zoom out to the whole column by clicking the red 'x' at the top of a column

![](../../.gitbook/assets/allzoominout.gif)

### Tooltip

The Tooltip at the top of the Visual Spreadsheet shows more information about the data under the mouse. [More information about using the data in the tooltip.](../../how-do-i/freeze-and-un-freeze-tooltip.md)

