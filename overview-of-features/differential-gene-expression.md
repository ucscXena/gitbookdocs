# Differential Gene Expression

To run a differential gene expression analysis, click on the 3 dot column menu at the top of a categorical column \(not a numerical column\) and choose 'Differential Expression'.

This will take you to new page where you will define the two subgroups you would like to compare. After you have your subgroups, scroll to the bottom and click 'submit'.

{% hint style="info" %}
Note that you can select more than one category per subgroup \(i.e. you can compare Luminal A and Luminal B to Her2\).
{% endhint %}

{% hint style="danger" %}
Due to compute limitations you can only run a total of 2000 samples through the analysis pipeline.
{% endhint %}

This will start the analysis, which make take a while to run depending on the size of the dataset. As the results are completed, the web page will update. Scroll to see more results. Once the analysis is finished it will say 'Done' at the top of the page.

## Running it on your own data

We disable running our differential gene expression analysis on your own data since we send the data in the analysis to various websites, which may or may not be secure. There are 3 options to run our analysis on your own data:

1. **Upload your data to** [**BioJupies**](https://maayanlab.cloud/biojupies/) **to run a somewhat similar analysis.** BioJupies by the Ma'ayan lab will run a somewhat similar analysis to the one we run and has a very user friendly interface.
2. **Upload your data to the** [**Bulk RNA-seq analysis pipeline Appyter**](https://appyters.maayanlab.cloud/#/Bulk_RNA_seq) **to run a very similar analysis.** This pipeline is what our analysis is based off of and will require a bit more familiarity with running differential gene expression analyses. Our modifications to this analysis are just to automatically pick the best normalization, etc options based on our public data. You will need to know which options are best given your own data.
3. **Run our pipeline on your own computer.** This will give you identical results to our pipeline but requires the most engineering to set up and run. You will need to [set up a docker](https://gallery.ecr.aws/f8e3p8q3/xena_de) with all the dependencies pre-installed and then download and run the notebook on this docker.

## More details

The gene expression dataset chosen for a specific study/cohort is the same gene expression dataset as the one in the [Basic Datasets menu](visual-spreadsheet/#selecting-a-dataset). 

The Advanced Visualization parameters only apply to the PCA or t-SNE plot. They do not apply to any other analyses.

