---
description: Step-by-step instructions to viewing your own data
---

# Getting Started

## **Overview**

Viewing your own data is easy! Simply:

1. [Install a Local Xena Hub on your computer](getting-started.md#installing-a-local-xena-hub)
2. [Start the Local Xena Hub](getting-started.md#starting-running-a-local-xena-hub)
3. [Load the data you want to view](getting-started.md#loading-data-into-a-local-xena-hub)
4. [View the data](getting-started.md#viewing-data-from-a-local-xena-hub)

We support most types of [genomic and/or phenotypic/clinical/annotation data](data-format-specifications.md). Genomic data needs to be values called on genes, transcripts, exons, probes or some other identifier. Phenotypic/clinical/annotation data can be almost anything, including patient data \(e.g. age, set, etc\), clinical data \([survival data for a KM plot](km-plots-using-data-from-a-local-xena-hub.md)\), and other data such as gene fusion calls, regulon activity, immune scores, and more. Samples can be bulk tissue, cell lines, cells, and more. We do not visualize raw data such as FASTQs or BAMs.

Data can be your own or from another source, like [GEO](https://www.ncbi.nlm.nih.gov/geo/) or a publication.  
  
Data on a Local Xena Hub can only be viewed or accessed by the same computer on which it is running, keeping private data secure.

The Local Xena Hub must be installed and running in order to load data, as well as any time you want to view data. The Local Xena Hub will remember previously loaded data.

## **Installing a Local Xena Hub**

Click on [**VIEW MY DATA**](https://xenabrowser.net/datapages/?addHub=https%3A%2F%2Flocal.xena.ucsc.edu%3A7223&host=https%3A%2F%2Flocal.xena.ucsc.edu%3A7223) ****and you will be prompted to download and install a local Xena Hub. 

Double click on the download to begin the installation of the Xena Hub. Follow the wizard to finish the install.

### System requirements

* Mac: OSX 10.7 and above
* Windows: 64-bit
* Linux: ability to run a .jar file

## **Starting/running a Local Xena Hub**

After installing a local Xena Hub, go back to [**VIEW MY DATA**](https://xenabrowser.net/datapages/?host=https%3A%2F%2Flocal.xena.ucsc.edu%3A7223) to auto-start the Hub. If it does not automatically start, refresh the page or double click on the Xena Hub application on your computer. The Xena Hub application should be in your Applications folder for Mac and Windows. Note that it typically takes a minute or two to start up.

## **Loading data into a Local Xena Hub**

Most people load data into their Local Xena Hub through our [website wizard](http://xenabrowser.net/datapages/?addHub=https%3A%2F%2Flocal.xena.ucsc.edu%3A7223&host=https%3A%2F%2Flocal.xena.ucsc.edu%3A7223), which leads you through the loading process step by step. Note that you will want to make sure your data is [properly formatted](data-format-specifications.md) ahead of time.

You can also load data [via the command line](loading-data-from-the-command-line.md).

## **Viewing data from a Local Xena Hub**

Click on [**VISUALIZATION**](https://xenabrowser.net/). If your study is not already selected as step 1 of the wizard, then select it from the drop down and click 'Done'. Note that if you did not enter a study name your data will be under 'New Study'.

### Gene names and identifiers for genomic data

When you loaded your genomic data we asked what type of genes, transcripts or probes you used. If you selected one of the options from the drop down menu then you can enter HUGO gene names or the identifiers in your file. If you did not select one of the options then you will need to enter the identifiers as they appear in your file.

### Help! I don't see my study listed

You Local Xena Hub must be running to view any data that you have loaded into it. Please ensure it is started up. You can also check which studies are on your hub and what data is in them by going to the My Computer Hub page: [xenabrowser.net/datapages/?host=https%3A%2F%2Flocal.xena.ucsc.edu%3A7223](https://xenabrowser.net/datapages/?host=https%3A%2F%2Flocal.xena.ucsc.edu%3A7223).  


