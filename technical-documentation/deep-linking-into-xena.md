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

#### HTML Code showing how to build examples 1-7

```html
<html>
<script>
	window.onload = function() {
        var browser = 'https://xenabrowser.net/';

        var hub1 = 'https://toil.xenahubs.net';
        var dataset1 = 'tcga_Kallisto_tpm';

		var hub2 = 'https://tcga.xenahubs.net';
		var dataset2 = 'TCGA.PANCAN.sampleMap/Gistic2_CopyNumber_Gistic2_all_data_by_genes';
		
		var hub3 = 'https://pancanatlas.xenahubs.net';
		var dataset3 = 'Survival_SupplementalTable_S1_20171025_xena_sp';

		var hub4 = 'https://pancanatlas.xenahubs.net';
		var dataset4 = 'broad.mit.edu_PANCAN_Genome_Wide_SNP_6_whitelisted.xena';

		var hub5 = 'https://gdc.xenahubs.net';
		var dataset5 = 'TCGA-BRCA.somaticmutation_wxs.tsv';

		var col1 = {name: dataset1, host: hub1, fields: 'TP53 FOXM1'};
		var col2 = {name: dataset2, host: hub2, fields: 'FOXM1'};
		var col3 = {name: dataset3, host: hub3, fields: 'cancer type abbreviation'};
		var col4 = {name: dataset4, host: hub4, fields: 'chr3:4000000-4100000'};
		var col5 = {
			name: dataset1,
			host: hub1,
			width: 400,
			columnLabel: 'top column label',
			fieldLabel: 'bottom column label',
			fields: 'ENST00000064780.6 ENST00000066544.7 ENST00000070846.10 ENST00000072516.7 ENST00000072644.5 ENST00000072869.8 ENST00000074304.9 ENST00000075120.11 ENST00000075322.10'
		};

		var col6 = {name: dataset1, host: hub1, fields: 'TP53'};
		var col6_geneAve = {name: dataset1, host: hub1, fields: 'TP53', geneAverage: true};

		var col7 = {name: dataset5, host: hub5, fields: 'TP53'};
		var col7_showIntron = {name: dataset5, host: hub5, fields: 'TP53', showIntrons: true};

		var col8 = {
			name: dataset1, 
			host: hub1, 
			fields: 'TP53 FOXM1', 
			sortDirection: 'reverse'
		};

		var heatmapChart = JSON.stringify({
			mode: 'chart'
		});

		var heatmapHideWelcome = JSON.stringify({
			showWelcome: false,
		});

		        var columns1 = JSON.stringify([col1]);
        var l1 = document.getElementById('link1');
        l1.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns1);

        var columns2 = JSON.stringify([col1, col2]);
        var l2 = document.getElementById('link2');
        l2.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns2) + '&heatmap=' + encodeURIComponent(heatmapChart);

        var columns3 = JSON.stringify([col3, col2, col4]);
        var l3 = document.getElementById('link3');
        l3.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns3);

        var columns4 = JSON.stringify([col3, col5]);
        var l4 = document.getElementById('link4');
        l4.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns4);

        var columns5 = JSON.stringify([col8]);
        var l5 = document.getElementById('link5');
        l5.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns5);

        var columns6 = JSON.stringify([col6, col6_geneAve]);
        var l6 = document.getElementById('link6');
        l6.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns6);

        var columns7 = JSON.stringify([col7, col7_showIntron]);
        var l7 = document.getElementById('link7');
        l7.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns7) + '&heatmap=' + encodeURIComponent(heatmapHideWelcome);
    };
</script>
<body>
    <a id=link1>Example 1</a> One data column (with two subcolumns) display
	<br><br>
	<a id=link2>Example 2</a> Display in chart mode
	<br><br>
	<a id=link3>Example 3</a> Three data column display, one clinical data column, two genomic data columns
	<br><br>
	<a id=link4>Example 4</a> Specify column width, top label, and bottom label on Column C
	<br><br>
	<a id=link5>Example 5</a> Reverse sort on Column B
	<br><br>
	<a id=link6>Example 6</a> Display gene average in Column C
	<br><br>
	<a id=link7>Example 7</a> Display introns in Column C; Hide welcome banner
</body>
</html>
```

**Highlight Samples Examples**

Below is HTML code showing how to generate URLs that:

1\) highlight samples TCGA-C8-A131-01 or TCGA-BH-A0DL-01

2\) highlight samples matching arbitrary criteria, such as samples in Column B with values > 10

#### HTML code for highlighting samples examples&#x20;

```html
<html>
<script>
	window.onload = function() {
		var browser = 'https://xenabrowser.net/';
		var columns = JSON.stringify([
			{
				"width": 136,
				"columnLabel": "gene expression RNAseq - IlluminaHiSeq",
				"fieldLabel": "TP53",
				"showIntrons": true,
				"host": "https://tcga.xenahubs.net",
				"name": "TCGA.BRCA.sampleMap/HiSeqV2",
				"fields": "TP53"
			},
			{
				"width": 200,
				"columnLabel": "somatic mutation (SNPs and small INDELs) - MC3 public version",
				"fieldLabel": "TP53",
				"host": "https://tcga.xenahubs.net",
				"name": "mc3/BRCA_mc3.txt",
				"fields": "TP53"
			}
		]);


		var heatmap1 = JSON.stringify({
			showWelcome: false,
			searchSampleList: ["TCGA-C8-A131-01", "TCGA-BH-A0DL-01"]
		});

		var l1 = document.getElementById('link1');
		l1.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns) + '&heatmap=' + encodeURIComponent(heatmap1);

		var heatmap2 = JSON.stringify({
			showWelcome: false,
			search: "B:>10"
		});

		var l2 = document.getElementById('link2');
		l2.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns) + '&heatmap=' + encodeURIComponent(heatmap2);
	};
</script>
<body>
	<a id=link1>Sample highlight example 1:</a> highlight samples of specific sample IDs, such as TCGA-C8-A131-01 or TCGA-BH-A0DL-01
	<br>
	<a id=link2>Sample highlight example 2:</a> highlight samples matching arbitary criteria, such as samples in Column B with values > 10
</body>
</html>
```

**HTML code showing sample filtering (to specify what samples to display in the view) examples**

```html
<html>
<script>
	window.onload = function() {
		var browser = 'http://dev.xenabrowser.net/';
		var columns = JSON.stringify([
			{
				"width": 90,
				"columnLabel": "",
				"fieldLabel": "site id",
				"host": "https://xena.treehouse.gi.ucsc.edu",
				"name": "clinical_TumorCompendium_v11_PolyA_2020-04-09.tsv",
				"fields": "site_id"
			},
			{
				"width": 150,
				"columnLabel": "gene expression RNAseq",
				"fieldLabel": "ALK",
				"host": "https://xena.treehouse.gi.ucsc.edu",
				"name": "TumorCompendium_v11_PolyA_AllSamples_AllGenes_Kallisto_HugoLog2TPM_20230630.tsv",
				"fields": "ALK"
			}
		]);


		var heatmap1 = JSON.stringify({
			showWelcome: false,
			searchSampleList: ["THR30_0820_S01", "THR30_0861_S01"]
		});

		var l1 = document.getElementById('link1');
		l1.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns) + '&heatmap=' + encodeURIComponent(heatmap1);

		var heatmap2 = JSON.stringify({
			showWelcome: false,
			search: "B:=TARGET"
		});

		var l2 = document.getElementById('link2');
		l2.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns) + '&heatmap=' + encodeURIComponent(heatmap2);

		var heatmap3 = JSON.stringify({
			filter: "B:TARGET",
		});

		var l3 = document.getElementById('link3');
		l3.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns) + '&heatmap=' + encodeURIComponent(heatmap3);

		var heatmap4 = JSON.stringify({
			showWelcome: false,
			filter: "B:TARGET OR B:TCGA",
		});

		var l4 = document.getElementById('link4');
		l4.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns) + '&heatmap=' + encodeURIComponent(heatmap4);

		var heatmap5 = JSON.stringify({
			showWelcome: false,
			filter: "B: TARGET",
			searchSampleList: ["TARGET-40-0A4I6O-01A-01R"]
		});

		var l5 = document.getElementById('link5');
		l5.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns) + '&heatmap=' + encodeURIComponent(heatmap5);

		var filterColumns = JSON.stringify([{
			"host": "https://xena.treehouse.gi.ucsc.edu",
			"name": "clinical_TumorCompendium_v11_PolyA_2020-04-09.tsv",
			"fields": "age_at_dx"
		}]);
		var heatmap6 = JSON.stringify({
			showWelcome: false,
			filter: "D:<5",
		});
		var l6 = document.getElementById('link6');
		l6.href = browser + 'heatmap/?columns=' + encodeURIComponent(columns) + '&filterColumns=' + encodeURIComponent(filterColumns) + '&heatmap=' + encodeURIComponent(heatmap6);
	};
</script>
<body>
	<a id=link1>Sample highlight Example 1:</a> highlight samples of specific sample IDs, such as THR30_0820_S01 or THR30_0861_S01
	<br><br>
	<a id=link2>Sample highlight Example 2:</a> highlight samples matching an arbitary criteria, such as TARGET samples
	<br><br>
	<a id=link3>Sample filtering Example 1:</a> specify (filter to) what samples to show in a view using a predicate, such as TARGET samples
	<br><br>
	<a id=link4>Sample filtering Example 2:</a> specify samples in a view using a predicate that includes a boolean term, such as TARGET and TCGA samples (use boolean OR)
	<br><br>
	<a id=link5>Sample filtering and highlight at the same time:</a> specify samples in a view using a predicate (e.g. just show TARGET samples), as well as highlight specific samples by IDs, such as TARGET-40-0A4I6O-01A-01R
	<br><br>
	<a id=link6>Sample filtering using data in a hidden filter column:</a> useful when you want to filter samples using data not displayed on the screen. You can use <i>HIDDEN FILTER COLUMN</i>. For exmaple, filter the samples to < 5 years old, but you don't want to actually display the age column on the screen.  
</body>
</html>
```

### Base URL and URL construction

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
