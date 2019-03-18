# Advanced data and datasets

## For TCGA, which gene expression RNAseq dataset should I use for my analysis?

#### Gene expression RNAseq \(IlluminaHiSeq\)

For comparison within a single TCGA cohort, you can use the "gene expression RNAseq" data. Values in this dataset is log2\(x+1\) where x is the RSEM value.

#### Gene expression RNAseq \(IlluminaHiSeq pancan normalized\)

For questions regarding the gene expression of a particular cohort in relation to other types tumors, you can use the pancan normalized version of the "gene expression RNAseq" data.  Values in this dataset are generated at UCSC by combining "gene expression RNAseq" values \(above\) of all TCGA cohorts, values are then mean-centered per gene, then extracting the converted data only belongs to the cohort of interest \(e.g. TCGA breast cancer\). Since there are 30-40 cancer types with RNAseq data, the TCGA pancan data can serve as a proxy of background distribution of gene expression. 

#### Gene expression RNAseq \(IlluminaHiSeq percentile\)

For comparing with data outside TCGA, you can use the percentile version if your non-TCGA RNAseq data is normalized by percentile ranking. Values in this dataset are generated at UCSC by rank RSEM values per sample.  The values are percentile ranks ranges from 0 to 100, lower values represent lower expression. You can also combine the TCGA RNAseq data with your RNAseq data, perform normalization across the combined dataset using whatever method you choose, then analyze the combined dataset further.

#### TCGA Pan-Cancer gene expression

For comparison across multiple or all TCGA cohorts. Dataset is generated at UCSC by combining "gene expression RNAseq \(IlluminaHiSeq\) data" \(see above\) from all TCGA cohorts. No further normalization is performed. [https://genome-cancer.soe.ucsc.edu/proj/site/xena/datapages/?dataset=public/TCGA/TCGA.PANCAN.sampleMap/HiSeqV2&host=https://genome-cancer.ucsc.edu:443/proj/public/xena](https://genome-cancer.soe.ucsc.edu/proj/site/xena/datapages/?dataset=public/TCGA/TCGA.PANCAN.sampleMap/HiSeqV2&host=https://genome-cancer.ucsc.edu:443/proj/public/xena)

## What is the difference between RPPA data and RPPA\_RBN data?

The TCGA RPPA data are generated at MD Anderson.  RPPA data is values generated using method described at [http://bioinformatics.mdanderson.org/main/TCPA:Overview](http://bioinformatics.mdanderson.org/main/TCPA:Overview). We download the RPPA values from TCGA DCC. 

The RPPA\_RBN data is normalized value generated using the RBN \(replicate-base normalization\) method developed by MDACC.  For more information: [http://bioinformatics.mdanderson.org/main/TCPA:Overview](http://bioinformatics.mdanderson.org/main/TCPA:Overview).  We downloaded the RBN values from synapse at [https://www.synapse.org/\#!Synapse:syn1750330](https://www.synapse.org/#!Synapse:syn1750330).  

## Can I combine data from the methylation 450k and 27k datasets?

The methylation 450k dataset has [90% of the probes from the 27k dataset](https://bmcgenomics.biomedcentral.com/articles/10.1186/1471-2164-14-293). However, we have discovered the range of data for each dataset to be slightly different. As such, we recommend applying some sort of normalization. We recommend looking in the literature to see what methods people have used.

## What is the difference between GISTIC 2 and GISTIC 2 thresholded datasets?

Many copy number estimation algorithms estimate copy number variation on a continuous scale even though it is measuring something discrete \(i.e. the number of copies of piece of chromosome or a gene in the cell\). The GISTIC 2 thresholded data attempts to assign discrete numbers to these fragments by thresholding the data. The estimated values -2,-1,0,1,2, represent homozygous deletion, single copy deletion, diploid normal copy, low-level copy number amplification, or high-level copy number amplification respectively. More information can be found in the [GISTIC 2 paper](https://genomebiology.biomedcentral.com/articles/10.1186/gb-2011-12-4-r41) and at the [Broad Institute](http://gdac.broadinstitute.org/), which is the group that processed this data. 

## Where is the transcript-level expression data?

As of March 2019, our transcript-level data is in the [TCGA Pan-Cancer cohort](https://xenabrowser.net/datapages/?cohort=TCGA%20Pan-Cancer%20%28PANCAN%29). From here choose 'Advanced' and select any of the transcript-level expression datasets. Enter your transcript of interest as a Ensembl identifier \(not a gene\). 



