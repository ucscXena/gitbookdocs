---
description: There are 4 ways to download data
---

# Download Data

## The four ways to download data

1\. Download data in a single column of a Visual Spreadsheet In a Visual Spreadsheet, click on the column Hamburger menu, then "Download" to download just the data from the column.

2\. Download data in an entire Visual Spreadsheet In a Visual Spreadsheet, clicking on the download icon in the upper right corner of the spreadsheet.

![](<../.gitbook/assets/screen-shot-2019-11-01-at-2.51.29-pm (2) (2) (2) (2) (2) (2) (2) (2) (2).png>)

3\. Bulk download a whole dataset file Click top banner "**Data Sets**" to navigate to the dataset of your interest, where a **download url** link is in the page. You can also reach the dataset page by clicking on the column Hamburger menu, then "**About**".  Click on the **download url** to download the entire dataset. Or use "wget", "curl" to download from command line.&#x20;

4\. Via our APIs:

* [**Python**](accessing-data-through-python.md) &#x20;
* [**R**](https://cran.r-project.org/web/packages/UCSCXenaTools/vignettes/USCSXenaTools.html) &#x20;

## **How do I open the download files?**

Our files are tab-delimited or '.tsv'. We recommend opening them on the command line if you hare able.

If you not able to use the command line then we recommend using your favorite spreadsheet program, such as Microsoft Excel, which will automatically convert the tabs into new columns. Please note that if you have many thousands of samples, Microsoft Excel will likely have difficulty opening the file.&#x20;

{% hint style="warning" %}
Please be careful when opening files that have gene names in Microsoft Excel as Microsoft Excel will automatically convert some gene names into dates. For more information see: [https://genomebiology.biomedcentral.com/articles/10.1186/s13059-016-1044-7](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-016-1044-7)
{% endhint %}
