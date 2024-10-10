---
description: Information on data from the Genomic Data Commons v41.0
---

# GDC

This help page is for the Genomic Data Commons (GDC) data we host from [GDC Data Release 41.0 - August 28, 2024](https://docs.gdc.cancer.gov/Data/Release\_Notes/Data\_Release\_Notes/). We display all GDC open access genomic data and its accompanying phenotype/clinical data. Explore the [GDC data on Xena](https://xenabrowser.net/datapages/?host=https%3A%2F%2Fgdc.xenahubs.net).

In addition to the data from the GDC, we added two new phenotype/clinical fields to all GDC cohorts: `age_at_earliest_diagnosis.diagnoses.xena_derived` and `age_at_earliest_diagnosis_in_years.diagnoses.xena_derived`. This was done because some GDC cohorts had multiple diagnoses, each with their own `age_at_diagnosis.diagnoses`. When there were multiple ages the Xena Visual Spreadsheet would display these fields as a category. In order to have a field that could always be displayed as a continuous feature, we created the `age_at_earliest_diagnosis.diagnoses.xena_derived` field that has the smallest value when there were multiple entries. `age_at_earliest_diagnosis_in_years.diagnoses.xena_derived` was created similarly, but also dividing the number of days by 365.&#x20;

For this release, we worked to not have samples that have no genomic data and only have phenotype/clinical data. This should make visualizing data in our Visual Spreadsheet easier.

You can still view data from the older [GDC Data Release v18.0 release - August 28, 2019](https://xenabrowser.net/datapages/?host=https%3A%2F%2FgdcV18.xenahubs.net\&removeHub=https%3A%2F%2Fgdc.xenahubs.net%3A443). This data will be available until October 2025. After October 2025 the data from this release will only be available for download.

## CPTAC-3

For the [CPTAC-3 ](https://gdc.cancer.gov/about-gdc/contributed-genomic-data-cancer-research/clinical-proteomic-tumor-analysis-consortium-cptac)cohort, we noted that occasionally samples were pooled into the same aliquot before sequencing was performed. Xena's visualizations are based on the sample-level, thus for these pooled aliquots there are several samples with duplicate data. An example of this is noted for case [C3N-03011](https://portal.gdc.cancer.gov/cases/df44d149-bfc1-4659-8a4e-f663855ab7b1?bioId=50460a1e-b6e3-48fe-a098-d3d5e11446af), where samples `C3N-03011-04`, `C3N-03011-02`, and `C3N-03011-01` were all pooled into the aliquot `CPT0226250007` before sequencing was performed.



