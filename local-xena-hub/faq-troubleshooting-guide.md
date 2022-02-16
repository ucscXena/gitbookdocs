# FAQ/Troubleshooting Guide

## I ran into APPLE warning you about “unidentified developer” warning when installing Xena. What do I do?

There are a couple of options. You can right-click the .dmg and chosen 'open'. You can also press the Control key, then click the app icon, then choose Open from the shortcut menu. These help pages might help:  [http://www.iclarified.com:8081/28180/how-to-open-applications-from-unidentified-developers-in-mac-os-x-mountain-lion](http://www.iclarified.com:8081/28180/how-to-open-applications-from-unidentified-developers-in-mac-os-x-mountain-lion) and from Apple: [https://support.apple.com/kb/PH25088?locale=en\_US](https://support.apple.com/kb/PH25088?locale=en\_US) .

## I see my probes/genes/transcripts when loading my data, but I don't know whether to choose hg18, hg19 or hg38?

The only time the assembly matters is if you decided to visualize part or all of a chromosome, rather than a gene/probe/transcript. If you want to visualize only genes/probes/transcripts than it does not matter which assembly you choose.

## I don't see my study listed in the visualization

You Local Xena Hub must be running to view any data that you have loaded into it. Please ensure it is started up. You can also check which studies are on your hub and what data is in them by going to the My Computer Hub page: [xenabrowser.net/datapages/?host=https%3A%2F%2Flocal.xena.ucsc.edu%3A7223](https://xenabrowser.net/datapages/?host=https%3A%2F%2Flocal.xena.ucsc.edu%3A7223).

You also may not see your study if the hub is still loading the data. Wait a few minutes and refresh the page.

## I'm entering a gene name but it only draws gray

When you loaded your genomic data we asked what type of genes, transcripts or probes you used. If you selected one of the options from the drop down menu then you can enter HUGO gene names or the identifiers in your file. If you did not select one of the options then you will need to enter the identifiers as they appear in your file.

## Can I load two or more phenotype files to the same study?&#x20;

Yes, we will allow you to select phenotypes from both files in the visualization.

## Help! My file is too large to open in Microsoft Excel.&#x20;

You might be able to load your file anyways, depending on the format. Give it a try and if you are unable to load it, write us an email and we may be able to fix your file for you.

## How do I convert my .xls or .xlsx into a tab-delimited file?&#x20;

You can export a Microsoft Excel file as a tab-delimited file using the 'Save as ...' function.

## Unix vs DOS

We require that your data files have a unix line ending. To ensure that your files have this line ending on a DOS, please follow the help here:&#x20;

{% embed url="https://til.hashrocket.com/posts/hu3jlszfrf-change-dos-to-unix-text-file-format-in-vim" %}

Note that this requirement is only for data files, not for the associated .json files.
