---
description: How to programmatically specify Xena Browser views
---

# Deep Linking Into Xena

Xena has the ability to draw visualizations based on parameters passed through URL. You will need to URL encode the parameters.

The list of supported parameters below is not exhaustive. If you do not see your functionality supported below please [contact us](../contact-us.md)**.**

## **Examples**

**Display Column Setup Examples**

[Example 1](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22tcga_Kallisto_tpm%22%2C%22host%22%3A%22https%3A%2F%2Ftoil.xenahubs.net%22%2C%22fields%22%3A%22TP53%20FOXM1%22%7D%5D) One data column (with two subcolumns) display

[Example 2](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22tcga_Kallisto_tpm%22%2C%22host%22%3A%22https%3A%2F%2Ftoil.xenahubs.net%22%2C%22fields%22%3A%22TP53%20FOXM1%22%7D%2C%7B%22name%22%3A%22TCGA.PANCAN.sampleMap%2FGistic2_CopyNumber_Gistic2_all_data_by_genes%22%2C%22host%22%3A%22https%3A%2F%2Ftcga.xenahubs.net%22%2C%22fields%22%3A%22FOXM1%22%7D%5D\&heatmap=%7B%22mode%22%3A%22chart%22%7D) Display in chart mode

[Example 3](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22Survival_SupplementalTable_S1_20171025_xena_sp%22%2C%22host%22%3A%22https%3A%2F%2Fpancanatlas.xenahubs.net%22%2C%22fields%22%3A%22cancer%20type%20abbreviation%22%7D%2C%7B%22name%22%3A%22TCGA.PANCAN.sampleMap%2FGistic2_CopyNumber_Gistic2_all_data_by_genes%22%2C%22host%22%3A%22https%3A%2F%2Ftcga.xenahubs.net%22%2C%22fields%22%3A%22FOXM1%22%7D%2C%7B%22name%22%3A%22broad.mit.edu_PANCAN_Genome_Wide_SNP_6_whitelisted.xena%22%2C%22host%22%3A%22https%3A%2F%2Fpancanatlas.xenahubs.net%22%2C%22fields%22%3A%22chr3%3A4000000-4100000%22%7D%5D) Three data column display, one clinical data column, two genomic data columns

[Example 4](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22Survival_SupplementalTable_S1_20171025_xena_sp%22%2C%22host%22%3A%22https%3A%2F%2Fpancanatlas.xenahubs.net%22%2C%22fields%22%3A%22cancer%20type%20abbreviation%22%7D%2C%7B%22name%22%3A%22tcga_Kallisto_tpm%22%2C%22host%22%3A%22https%3A%2F%2Ftoil.xenahubs.net%22%2C%22width%22%3A400%2C%22columnLabel%22%3A%22top%20column%20label%22%2C%22fieldLabel%22%3A%22bottom%20column%20label%22%2C%22fields%22%3A%22ENST00000064780.6%20ENST00000066544.7%20ENST00000070846.10%20ENST00000072516.7%20ENST00000072644.5%20ENST00000072869.8%20ENST00000074304.9%20ENST00000075120.11%20ENST00000075322.10%22%7D%5D) Specify column width, top label, and bottom label on Column C

[Example 5](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22tcga_Kallisto_tpm%22%2C%22host%22%3A%22https%3A%2F%2Ftoil.xenahubs.net%22%2C%22fields%22%3A%22TP53%20FOXM1%22%2C%22sortDirection%22%3A%22reverse%22%7D%5D) Reverse sort on Column B

[Example 6](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22tcga_Kallisto_tpm%22%2C%22host%22%3A%22https%3A%2F%2Ftoil.xenahubs.net%22%2C%22fields%22%3A%22TP53%22%7D%2C%7B%22name%22%3A%22tcga_Kallisto_tpm%22%2C%22host%22%3A%22https%3A%2F%2Ftoil.xenahubs.net%22%2C%22fields%22%3A%22TP53%22%2C%22geneAverage%22%3Atrue%7D%5D) Display gene average in Column C

[Example 7](https://xenabrowser.net/heatmap/?columns=%5B%7B%22name%22%3A%22TCGA-BRCA.somaticmutation_wxs.tsv%22%2C%22host%22%3A%22https%3A%2F%2Fgdc.xenahubs.net%22%2C%22fields%22%3A%22TP53%22%7D%2C%7B%22name%22%3A%22TCGA-BRCA.somaticmutation_wxs.tsv%22%2C%22host%22%3A%22https%3A%2F%2Fgdc.xenahubs.net%22%2C%22fields%22%3A%22TP53%22%2C%22showIntrons%22%3Atrue%7D%5D\&heatmap=%7B%22showWelcome%22%3Afalse%7D) Display introns in Column C; Hide welcome banner

{% file src="../.gitbook/assets/linktest.html" %}
HTML file showing how to build examples 1 - 7.
{% endfile %}

**Highlight Samples Examples**

[Example 8:](https://xenabrowser.net/heatmap/?columns=%5B%7B%22width%22%3A136%2C%22columnLabel%22%3A%22gene%20expression%20RNAseq%20-%20IlluminaHiSeq%22%2C%22fieldLabel%22%3A%22TP53%22%2C%22showIntrons%22%3Atrue%2C%22host%22%3A%22https%3A%2F%2Ftcga.xenahubs.net%22%2C%22name%22%3A%22TCGA.BRCA.sampleMap%2FHiSeqV2%22%2C%22fields%22%3A%22TP53%22%7D%2C%7B%22width%22%3A200%2C%22columnLabel%22%3A%22somatic%20mutation%20%28SNPs%20and%20small%20INDELs%29%20-%20wustl%20curated%22%2C%22fieldLabel%22%3A%22TP53%22%2C%22host%22%3A%22https%3A%2F%2Ftcga.xenahubs.net%22%2C%22name%22%3A%22TCGA.BRCA.sampleMap%2Fmutation_curated_wustl%22%2C%22fields%22%3A%22TP53%22%7D%5D\&heatmap=%7B%22showWelcome%22%3Afalse%2C%22searchSampleList%22%3A%5B%22TCGA-C8-A131-01%22%2C%22TCGA-BH-A0DL-01%22%5D%7D) highlight TCGA-C8-A131-01 or TCGA-BH-A0DL-01 samples

[Example 9:](https://xenabrowser.net/heatmap/?columns=%5B%7B%22width%22%3A136%2C%22columnLabel%22%3A%22gene%20expression%20RNAseq%20-%20IlluminaHiSeq%22%2C%22fieldLabel%22%3A%22TP53%22%2C%22showIntrons%22%3Atrue%2C%22host%22%3A%22https%3A%2F%2Ftcga.xenahubs.net%22%2C%22name%22%3A%22TCGA.BRCA.sampleMap%2FHiSeqV2%22%2C%22fields%22%3A%22TP53%22%7D%2C%7B%22width%22%3A200%2C%22columnLabel%22%3A%22somatic%20mutation%20%28SNPs%20and%20small%20INDELs%29%20-%20wustl%20curated%22%2C%22fieldLabel%22%3A%22TP53%22%2C%22host%22%3A%22https%3A%2F%2Ftcga.xenahubs.net%22%2C%22name%22%3A%22TCGA.BRCA.sampleMap%2Fmutation_curated_wustl%22%2C%22fields%22%3A%22TP53%22%7D%5D\&heatmap=%7B%22showWelcome%22%3Afalse%2C%22search%22%3A%22B%3A%3E10%22%7D) highlight samples matching arbitrary criteria, such as samples in Column B with values > 10

{% file src="../.gitbook/assets/samplehighlight2.html" %}
HTML files showing how to build examples 8 & 9
{% endfile %}

**Sample Filtering (specify what samples to display in the view) Examples**

{% file src="../.gitbook/assets/sample_highlight_filter.html" %}
HTML file showing how to specify what samples to display in the view
{% endfile %}

## **Base URL and URL construction**

```
var page = ‘https://xenabrowser.net/heatmap/’;
var url = page + ‘?columns=’ + encodeURIComponent(columns_parameter) + \
    ‘&heatmap=’ + encodeURIComponent(heatmap_parameter);
```

## _**columns**_ **parameter**

The _columns_ parameter is a JSON-encoded array of objects, specifying the columns to display.

### **Properties**

To specify a single column you need to, at a minimum, specify the dataset ID, the hub where the data resides, and the fields that you want to display.

```
var column = {name: dataset1, host: hub1, fields: 'foo bar'};
var columns_parameter = JSON.stringify([column]);
var url = page + ‘?columns=’ + encodeURIComponent(columns_parameter);
```

#### _Fields_ for genomic columns

Fields can be a gene, probe, or chromosome position. All fields need to be of the same type (i.e. all genes or all probes). You can only enter one chromosome position per column.

#### _Fields_ for phenotypic columns

Field should be the field ID as it appears exactly in the dataset

### **Optional properties**

_width: \<number>_

Width in pixels

_columnLabel: \<string>_

Text for top column label

_fieldLabel: \<string>_

Text for bottom column label

_geneAverage: \<boolean>_

Display the gene average instead of the individual probes for a gene. You can use this only when a single gene is specified for a dataset that has probes on a gene

_normalize: ‘none’ | ‘mean’ | ‘log2’ | ‘normal2’_

How the data should be dynamically normalized on the fly. 'mean' is x-mean (subtract mean), applied per (sub)column. 'log2' is log2(x+1). 'normal2' is (x-2).

_showIntrons: \<boolean>_

Show introns for mutation and segmented copy number columns

_sortDirection: 'reverse'_

Reverse sort the samples

_sortVisible: \<boolean>_

Sort column on the zoomed region

## _**filterColumns**_ **parameter**

Same as the _columns_ parameter, but these columns will not be displayed. They are available for sample filtering. See the _filter_ property of the _heatmap_ parameter, below.

## _**heatmap**_ **parameter**

The _heatmap_ parameter is a JSON-encoded object specifying global display options

### **Properties**

_mode: 'chart'_

Display in chart mode rather than visual spreadsheet mode.

_showWelcome: \<boolean>_

Show the welcome banner.

_searchSampleList: \[\<string>, ...]_

Highlight the specified samples in the view.

_search: \<string>_

Equivalent to typing this text into the 'Find' feature in Xena. In this example it is highlighting the samples that for column B have a value of 'TARGET'. [More examples of possible search terms.](../overview-of-features/filter-and-subgrouping/)

_filter: \<string>_

Like the _search_ parameter, but filter the view to the matching samples. Equivalent to [selecting 'Filter' from the 'Find' UI](../overview-of-features/filter-and-subgrouping/#general-functionality). Columns that are only needed for filtering (not visualization) can be added to the _filterColumns_ parameter, and appear semantically after _columns_. For example, if _columns_ has length two they are labeled 'B' and 'C', and the first column in _filterColumns_ will be 'D'.

Both _search_ and _filter_ can be specified in the same url, in which case the samples will be filtered, and any remaining samples matching _search_ will be highlighted. Note that the _search_ expression should only reference _columns_, not _filterColumns_, since the latter are not available for visualization.

```
var heatmap_paramter = JSON.stringify({
      showWelcome: false,
      search: "B:=TARGET"
});
var url = page + ‘?columns=’ + encodeURIComponent(columns_parameter) + \
      ‘?heatmap=’ + encodeURIComponent(heatmap_paramter);
```
