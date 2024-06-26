---
description: Viewing the HCA Census of Immune Cells cohort
---

# Single-cell HCA Tutorial

## Video of walk through

![](../.gitbook/assets/hcatutorial-1.gif)

## Step by step instructions

1\. Start [here](https://singlecell.xenabrowser.net/heatmap/)

2\. Search for the study 'HCA Census of Immune Cells' and select. Click 'Done' at the bottom of the column.

3\. Choose 'Phenotypic' and select 'louvain\_cluster' and 'organ\_part'. Click 'Done' at the bottom of the column.

4\. Click 'Add Column' next to last column, select 'Analytic', and select 'cluster 3 markers - gene expression' and 'cluster 5 & 7 markers - gene expression'. Click 'Done' at the bottom of the column.

5\. Click the bottom right corner of a column and drag it to make the column wider. Click and drag the top of a column to change the row sort order to find new patterns.

## Final View

![](../.gitbook/assets/hca-census-of-immune-cells\_public\_private-1.png)

### [Click here for a Live View](https://singlecell.xenabrowser.net/?columns=%5B%7B%22width%22%3A127%2C%22columnLabel%22%3A%22%22%2C%22fieldLabel%22%3A%22louvain\_cluster%22%2C%22host%22%3A%22https%3A%2F%2Fsinglecellnew.xenahubs.net%22%2C%22name%22%3A%22HCA%2FCensus\_of\_Immune\_Cells%2Fcluster.tsv%22%2C%22fields%22%3A%22louvain\_cluster%22%7D%2C%7B%22width%22%3A120%2C%22columnLabel%22%3A%22%22%2C%22fieldLabel%22%3A%22organ\_parts%20\(derived\)%22%2C%22host%22%3A%22https%3A%2F%2Fsinglecellnew.xenahubs.net%22%2C%22name%22%3A%22HCA%2FCensus\_of\_Immune\_Cells%2Fcells.tsv%22%2C%22fields%22%3A%22derived\_organ\_parts\_label%22%7D%2C%7B%22width%22%3A222%2C%22columnLabel%22%3A%22single%20cell%20RNAseq%20gene%20expression%20-%20Optimus%20count%22%2C%22fieldLabel%22%3A%22cluster%203%20markers%22%2C%22host%22%3A%22https%3A%2F%2Fsinglecellnew.xenahubs.net%22%2C%22name%22%3A%22HCA%2FCensus\_of\_Immune\_Cells%2Fexpression.tsv%22%2C%22fields%22%3A%22LYZ%20S100A9%20S100A8%20S100A6%20S100A4%20LGALS1%20SRGN%20TYROBP%20CST3%20CYBA%20FCN1%20FOS%22%7D%2C%7B%22width%22%3A230%2C%22columnLabel%22%3A%22single%20cell%20RNAseq%20gene%20expression%20-%20Optimus%20count%22%2C%22fieldLabel%22%3A%22clusters%205%2F7%20markers%22%2C%22host%22%3A%22https%3A%2F%2Fsinglecellnew.xenahubs.net%22%2C%22name%22%3A%22HCA%2FCensus\_of\_Immune\_Cells%2Fexpression.tsv%22%2C%22fields%22%3A%22CD74%20CD37%20CD79A%20MS4A1%20CD79B%20HLA-DRB1%20TCL1A%20HLA-DQA1%20HLA-DQB1%20CD52%20FAM129C%20BANK1%22%7D%5D\&heatmap=%7B%22showWelcome%22%3Afalse%2C%22mode%22%3A%22heatmap%22%7D)

In this example we provide the Louvain clusters as part of our public hub. To add data from your own private hub to the view send us an [email](mailto:genome-cancer@soe.ucsc.edu) and we'll get you started.

### More information about this view

_Gene expression from an HCA 800,000 cell scRNA-seq dataset at a single cell resolution._ The view displays expression profiles of 24 genes with two cell annotations from the HCA Census of Immune Cells study. The 26-parameter data from all 794,365 cells is held in compressed form in the Browser, with no down-sampling applied in generating the view. Each row across the entire display represents a single cell. Xena’s public-private data join feature enables users to combine large public resource data, such as the gene expression data from HCA, with their own analysis results, such as the Louvain clusters.
