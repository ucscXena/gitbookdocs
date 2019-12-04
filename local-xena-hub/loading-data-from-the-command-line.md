# Loading data from the command line

In addition to the data itself, we require some metadata about your file. When you use our website to load your data we fill in this metadata for you. When you use the command line, you will need to provide this data in an additional file.

## **Metadata file requirements**

The metadata file is a .json file and follows[ json formatting](http://www.w3schools.com/json/). The metadata .json file needs to be in the same directory as the data file. The metadata file and the data file need to have the same base name \(e.g. my\_data and my\_data.json\).

There are two required fields: type and cohort.

### Type

Type can be:

* 'genomicMatrix' -&gt; [genomic data ](data-format-specifications.md#basic-genomic-data-numbers-in-a-rectangle-matrix-spreadsheet)where samples are columns and genomic regions are rows. Note that for loading on the command line we do not support the other orientation
* 'clinicalMatrix' -&gt; [phenotypic data](data-format-specifications.md#basic-phenotypic-data-categories-or-non-genomic-in-a-rectangle-matrix-spreadsheet) where samples are rows and phenotypic columns are rows. Note that for loading on the command line we do not support the other orientation
* 'mutationVector' -&gt; [mutation data](data-format-specifications.md#advanced-positional-data)
* ‘genomicSegment’-&gt; [segmented copy number data](data-format-specifications.md#advanced-segmented-data)

#### Example:

```text
{"type":"mutationVector"}
```

### **Cohort**

Cohort is used to know if there are other data on the samples that you are loaded. You can either specify a pre-existing cohort or create your own. Cohort names are displayed on the dataset pages and the cohort drop down menu on the Heatmaps page.

For existing cohorts, you need to enter the cohort name EXACTLY as it appears as the existing cohort name. Note that our cohort names are case sensitive.

#### Example

```text
{"type":"mutationVector", 
 "cohort":"TCGA Breast Cancer"}
```

### **Reference**

If you are loading a mutation or segmented copy number file you will also need to specify the reference genome. You do not need to specify this for other file types

#### Example

```text
{"type":"mutationVector", 
 "cohort":"TCGA Breast Cancer", 
 "assembly":"hg19"}
```

### **Probemap**

If you are loading a file that has probes, transcripts, or exons and you would like to query your data by gene, you will need to provide a mapping file. You do not need to specify this for other file types.

Here is an example probemap file \(a delimitated file\): [https://toil.xenahubs.net/download/probeMap/gencode.v23.annotation.gene.probemap](https://toil.xenahubs.net/download/probeMap/gencode.v23.annotation.gene.probemap)

```text
#id    gene    chrom    chromStart    chromEnd    strand 
id_1    AADACL3    chr1    12776118    12776347    +
```

We have many probemap files that you can see via our [xenaPython app](../overview-of-features/accessing-data-through-python.md). 

```text
host =“https://reference.xenahubs.net”
xenaPython.probemap_list(host)
```

If you do not see a probemap that will work for you, please let us know.

To reference a probemap you need three files: 

1. Include the probemap reference in your data file .json
2. Have the probemap file in the same directory as your data file and data file .json
3. Also have a .json file for the probemap so that we know how to load it

{% hint style="warning" %}
Note that to reference a probemap you need to load the probemap first, then load the data file.
{% endhint %}

#### Example data file .json

```text
{"type":"genomicMatrix", 
 "cohort":"TCGA Breast Cancer", 
 ":probeMap":"/unc_v2_exon_hg19_probe_TCGA"}
```

#### Example probemap

[https://toil.xenahubs.net/download/probeMap/gencode.v23.annotation.gene.probemap](https://toil.xenahubs.net/download/probeMap/gencode.v23.annotation.gene.probemap)

#### Example probemap .json file \(required to be in the same folder as the probemap\)

```text
{ “type”:“probeMap”, 
  “assembly”:“hg19"}
```

## **Commands to load data**

Put both your .tsv and .json files in your\_home\_directory/xena/files. Then run the jar, passing in the file name, like so:

```text
java -jar cavm-0.xx.0-standalone.jar -l ~/xena/files/*
```

 → loads all files

OR

```text
java -jar cavm-0.xx.0-standalone.jar -l ~/xena/files/file1.tsv
```

 → loads just file1.tsv

Note that you will need to substitute the name of the .jar. file As of the time of writing \(September 20, 2018\), the name of the .jar file was cavm-0.22.0-standalone.jar. On linux this will be in the directory where you opened the archive. On Windows or MacOS, use your operating system’s file search capability to search for cavm\*jar. On Windows you will need to use the full path to your home directory, instead of “~”.

Note you do not need to load the .json files. Xena will automatically look for these and load them.

## **Commands to delete data**

```text
java -jar cavm-0.xx.0-standalone.jar -x ~/xena/files/file1.tsv
```

 → delete just file1.tsv

```text
java -jar cavm-0.xx.0-standalone.jar -x ~/xena/files/file1.tsv ~/xena/files/file2.tsv
```

 → delete file1.tsv and file2.tsv
 

## Help

You can always type:

```text
java -jar cavm-0.xx.0-standalone.jar -h
```

for help.  


