# Visual Spreadsheet

This dynamic, powerful, and flexible view is our default view into the data.

The Visual Spreadsheet allows you to add an arbitrary number of columns of any data type \(mutation, copy number, expression, protein, phenotype, methylation, etc\) into a spreadsheet-like view. We line up all columns so that each row is the same sample, allowing you to easily see trends in the data. Data is always sorted left to right and sub-sorted on columns thereafter.

Get started by going to the [Xena Browser](https://xenabrowser.net/heatmap/) and following the wizard to enter your data of interest.

## Making a Visual Spreadsheet

The wizard on the screen will guide you to choose a cohort of samples to view and TWO columns of data to view on those samples. Note that if you do not choose at least two columns, the wizard will not exit and let you interact with the data.

### Selecting a cohort

TBD

### Adding a Gene or Position

Please use HUGO gene names or the probe names in the dataset. Go to dataset pages to learn more about names that will be recognized.

To display a genomic region, enter the genomic region, choose your dataset and click 'done'. We accept entire chromosomes \(e.g. chr1\), arms of chromosomes \(e.g. chr19q\), or chromosomes coordinates. Coordinates need to be in this format: chr1:100-4,000. 

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

### Basics

#### If you entered a single gene

TBD

#### If you entered multiple genes

Note that if you entered more than one gene and selected a mutation dataset, we will only show the first gene. If you wish to see multiple mutation columns, please enter each gene individually and click 'done'

#### If you entered a chromosome or chromosome position

When displaying a chromosome range, genes will be shown in dark blue at the top of the column. Hovering over a gene will display the gene name in the tooltip. Alt-click to freeze the tooltip to click on the gene name and learn more about that gene. Note that introns are always shown in this mode.

#### If you chose a phenotype data

TBD

#### Mutation and CNV data

When displaying a single gene, the gene model will be displayed at the top of the column. The gene model is a composite of all transcripts of the gene. Boxes show different exons with UTR regions being short and CDS regions being tall. We display 2Kb upstream to show the promoter region. Use the column menu to toggle to show intronic regions.

### Data values

Individual values for each dataset mean different things. The legend at the bottom of the dataset will tell you the units for your particular dataset, including any normalization that was performed. 

If this does not answer your question we recommend going to the dataset details page to learn more about the dataset. To get there, click on the column menu and choose 'About'.

![](../../.gitbook/assets/aboutmenu.gif)

### Sample sorting

The Xena Browser uses y axis for samples, x axis/columns for genomic/phenotypic features. Data from a single sample is always on the same horizontal line across all columns. Linking samples across columns allows you to see screen-wide trends. The Xena Browser orders samples left to right first by the first columns, then the second, etc. If there are multiple genes, identifiers, probes within in a column, samples is ordered from left to right by 1st sub-column, then 2nd sub-column, and so on. 

Numerical data \(e.g. 1.2, 3.5, etc\) are ordered in descending order \(e.g. 3.5, 1.2, ...\). Categorical data \(e.g. stage, tumor type, etc\) are ordered by categories. CNV data is sorted by the average of the entire column. Positional mutation data is ordered by by genomic coordinates \(from 5'-&gt;3'\) and then by type of mutation \(mutations that destroy the transcript such as frameshift, mutations that change the transcript such as missense, silent mutations such as UTR mutations\). For both the CNV and positional mutation data, you can choose to instead sort by the region you are zoomed to. Click the columns menu at the top of the column and choose  'Sort by zoom region avg'.

To reverse the ordering for any column, click the column menu at the top of the column and chose 'Reverse sort'

### Zooming

Click and drag any where in any column to zoom in in either direction. Zoom out to all samples by clicking the 'Clear Zoom' at the top. Zoom out to the whole column by clicking the red 'x' at the top of a column

![](../../.gitbook/assets/allzoominout.gif)

### Tooltip

The Tooltip at the top of the Visual Spreadsheet shows more information about the data under the mouse. [More information about using the data in the tooltip.](../../how-do-i/freeze-and-un-freeze-tooltip.md)

