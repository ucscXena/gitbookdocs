---
description: How to programmatically specify Xena Browser views
---

# Deep Linking into Xena

Xena has the ability to draw visualizations based on parameters passed through URL. You will need to URL encode the parameters.

The list of supported parameters below is not exhaustive. If you do not see your functionality  supported below please [contact us](../contact-us.md)**.**

## **Examples**

[Example 1](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22tcga_Kallisto_tpm%22%2C%22host%22%3A%22https%3A%2F%2Ftoil.xenahubs.net%22%2C%22fields%22%3A%22TP53%20FOXM1%22%7D%5D) One data column \(with two subcolumns\) display  
  
[Example 2](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22tcga_Kallisto_tpm%22%2C%22host%22%3A%22https%3A%2F%2Ftoil.xenahubs.net%22%2C%22fields%22%3A%22TP53%20FOXM1%22%7D%2C%7B%22name%22%3A%22TCGA.PANCAN.sampleMap%2FGistic2_CopyNumber_Gistic2_all_data_by_genes%22%2C%22host%22%3A%22https%3A%2F%2Ftcga.xenahubs.net%22%2C%22fields%22%3A%22FOXM1%22%7D%5D&heatmap=%7B%22mode%22%3A%22chart%22%7D) Display in chart mode  
  
[Example 3](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22Survival_SupplementalTable_S1_20171025_xena_sp%22%2C%22host%22%3A%22https%3A%2F%2Fpancanatlas.xenahubs.net%22%2C%22fields%22%3A%22cancer%20type%20abbreviation%22%7D%2C%7B%22name%22%3A%22TCGA.PANCAN.sampleMap%2FGistic2_CopyNumber_Gistic2_all_data_by_genes%22%2C%22host%22%3A%22https%3A%2F%2Ftcga.xenahubs.net%22%2C%22fields%22%3A%22FOXM1%22%7D%2C%7B%22name%22%3A%22broad.mit.edu_PANCAN_Genome_Wide_SNP_6_whitelisted.xena%22%2C%22host%22%3A%22https%3A%2F%2Fpancanatlas.xenahubs.net%22%2C%22fields%22%3A%22chr3%3A4000000-4100000%22%7D%5D) Three data column display, one clinical data column, two genomic data columns  
  
[Example 4](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22Survival_SupplementalTable_S1_20171025_xena_sp%22%2C%22host%22%3A%22https%3A%2F%2Fpancanatlas.xenahubs.net%22%2C%22fields%22%3A%22cancer%20type%20abbreviation%22%7D%2C%7B%22name%22%3A%22tcga_Kallisto_tpm%22%2C%22host%22%3A%22https%3A%2F%2Ftoil.xenahubs.net%22%2C%22width%22%3A400%2C%22columnLabel%22%3A%22top%20column%20label%22%2C%22fieldLabel%22%3A%22bottom%20column%20label%22%2C%22fields%22%3A%22ENST00000064780.6%20ENST00000066544.7%20ENST00000070846.10%20ENST00000072516.7%20ENST00000072644.5%20ENST00000072869.8%20ENST00000074304.9%20ENST00000075120.11%20ENST00000075322.10%22%7D%5D) Specify column width, top label, and bottom label on Column C  
  
[Example 5](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22tcga_Kallisto_tpm%22%2C%22host%22%3A%22https%3A%2F%2Ftoil.xenahubs.net%22%2C%22fields%22%3A%22TP53%20FOXM1%22%2C%22sortDirection%22%3A%22reverse%22%7D%5D) Reverse sort on Column B  
  
[Example 6](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22tcga_Kallisto_tpm%22%2C%22host%22%3A%22https%3A%2F%2Ftoil.xenahubs.net%22%2C%22fields%22%3A%22TP53%22%7D%2C%7B%22name%22%3A%22tcga_Kallisto_tpm%22%2C%22host%22%3A%22https%3A%2F%2Ftoil.xenahubs.net%22%2C%22fields%22%3A%22TP53%22%2C%22geneAverage%22%3Atrue%7D%5D) Display gene average in Column C  
  
[Example 7](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22TCGA-BRCA.mutect2_snv.tsv%22%2C%22host%22%3A%22https%3A%2F%2Fgdc.xenahubs.net%22%2C%22fields%22%3A%22TP53%22%7D%2C%7B%22name%22%3A%22TCGA-BRCA.mutect2_snv.tsv%22%2C%22host%22%3A%22https%3A%2F%2Fgdc.xenahubs.net%22%2C%22fields%22%3A%22TP53%22%2C%22showIntrons%22%3Atrue%7D%5D&heatmap=%7B%22showWelcome%22%3Afalse%7D) Display introns in Column C; Hide welcome banner

{% file src="../.gitbook/assets/linktest.html" caption="File showing how to build examples 1 - 7" %}

**Example 8:**

## **Base URL and URL construction**

```text
var page = ‘https://xenabrowser.net/heatmap/’;
var url = page + ‘?columns=’ + encodeURIComponent(columns_parameter) + \
    ‘&heatmap=’ + encodeURIComponent(heatmap_parameter);
```

## _**columns**_ **parameter**

The _columns_ parameter is a JSON-encoded array of objects, specifying the columns to display. 

### **Properties**

To specify a single column you need to, at a minimum, specify the dataset ID, the hub where the data resides, and the fields that you want to display.

```text
var column = {name: dataset1, host: hub1, fields: 'foo bar'};
var columns_parameter = JSON.stringify([column]);
var url = page + ‘?columns=’ + encodeURIComponent(columns_parameter);

```

#### _Fields_ for genomic columns

Fields can be a gene, probe, or chromosome position. All fields need to be of the same type \(i.e. all genes or all probes\). You can only enter one chromosome position per column.

#### _Fields_ for phenotypic columns

Field should be the field ID as it appears exactly in the dataset

### **Optional properties**

_&lt;width: number&gt;_

Width in pixels

_&lt;columnLabel: string&gt;_

Text for top column label

_&lt;fieldLabel: string&gt;_

Text for bottom column label

_&lt;geneAverage: boolean&gt;_

Display the gene average instead of the individual probes for a gene. You can use this only when a single gene is specified for a dataset that has probes on a gene

_&lt;normalize: ‘none’ \| ‘mean’ \| ‘log2’ \| ‘normal2’&gt;_

How the data should be dynamically normalized on the fly. 'mean' is x-mean (subtract mean), applied per (sub)column. 'log2' is log2(x+1).  'normal2' is (x-2).

_&lt;showIntrons: boolean&gt;_

Show introns for mutation and segmented copy number columns

_&lt;sortDirection: 'reverse'&gt;_

Reverse sort the samples

_&lt;sortVisible: boolean&gt;_

Sort column on the zoomed region

## _**heatmap**_ **parameter**

The _heatmap_ parameter is a JSON-encoded object specifying global display options

### **Properties**

_&lt;mode: 'chart'&gt;_

Display in chart mode rather than visual spreadsheet mode.

_&lt;showWelcome: boolean&gt;_

Show the welcome banner.

_&lt;searchSampleList: \[string, ...\]&gt;_

Highlights the specified samples in the view. 

_&lt;search: string&gt;_

Equivalent to typing this text into the 'Find' feature in Xena. In this example it is highlighting the samples that for column B have a value of 'TARGET'. [More examples of possible search terms.](../overview-of-features/filter-and-subgrouping.md)  

```text
var heatmap_paramter = JSON.stringify({
      mode: ‘chart’,
      showWelcome: false,
      searchSampleList: ["THR30_0820_S01", "THR30_0861_S01"]
  });
var url = page + ‘?columns=’ + encodeURIComponent(columns_parameter) + \
      ‘?heatmap=’ + encodeURIComponent(heatmap_paramter);
```


