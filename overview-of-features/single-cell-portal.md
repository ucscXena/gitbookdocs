---
description: Overview of how to view single cell data
---

# Single Cell Portal

## Entering the Single Cell Portal

To enter the single cell portal click on 'SINGLECELL' in the top navigation bar. This will welcome you to the portal where you can then click 'Enter'.

## Selecting a study

You can either double-click to select a study or click on a study and click next.

Note that we do not yet support users loading their own data. If there is data that you'd like to see on the Single Cell Portal, public or private, [contact us](../contact-us.md).

For many of the studies we generated data on top of what was provided by the authors, such as the coordinates for a 3D UMAP. Note that these Xena-derived data are in beta and are subject to change at any point.

## Selecting a layout

After you have selected a study you will be prompted to select a layout on the left. We offer two types of layouts: spatial and UMAP/t-SNE. Select one of these and then select the specific layout you would like from the drop down menu. Our UMAP/t-SNE plots can be 2D or 3D.

## Image configuration

Many of our spatial layouts have an image component, either H\&E or fluorescent image channels. Click on the 'image' tab in the right panel to manipulate the image component, if available. At the top of the tab will be an opacity slider for the H\&E image, if that is available for your layout. Below that are the image channels. The check boxes allow you to turn color channels on and off. You can select different channels by clicking on the channel name and choosing a new one from the drop down menu. The slider below the channel name allows you to adjust the saturation of the color. At the bottom of the tab you can toggle the cell segmentation on and off, if it is available for an image.

## Coloring the cell/dots

All of our layouts have the ability to color the cell or dot by various data. The options, which may or may not be available for a particular study, are donor, dataset, cell types/clusters, cell type/cluster scores, gene/protein, and more options. The 'cell type/cluster scores' allows you to more closely examine one cell type or cluster. 'Gene/protein' contains gene expression and protein expression data. More options contains a variety of additional data we have on those cells/dots.

Each of these options will also have an advanced options menu, where you can choose to sub-color by another variable, such as coloring a categorical feature by a continuous one so that the intensity of the categorical color is controlled by the continuous one. Not all combinations of data types are supported.

## Viewing single cell data in the Visual Spreadsheet or Chart View

In addition to viewing single cell data in the Single Cell Portal, you can also view it in the [Visual Spreasheet](visual-spreadsheet/) or [Chart View](chart-view.md). Select the study and columns or data you are interested in in the Visual Spreasheet, similar to the bulk data.&#x20;
