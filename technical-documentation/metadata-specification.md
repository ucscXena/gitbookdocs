---
description: metadata (.json file) specification for maps and survival time unit 
---

# Metadata specification

## MAPs
MAPs are tsne, umap, pca embeddings in 2D or 3E, or spatial maps for spatical data.

**map** is a list in the .json metadata file

For each map

**"label"** free text. Display label of the map, should be easily readable by users

**"dataSubType"** a string. Describe the natur of the map, must be **embedding**, **spatial_map** . Note this is the dataSubType attribute for the map, not the dataSubType attribute for the file 

**"dimension"** a list of strings. They are the column headers of the dimention columns in the data file. They are used to retrieve data from db.

example
```json
{
    "type": "clinicalMatrix",
    "cohort": "name of the cohort",
    "label": "display label of the file",
    "dataSubType": "the section the dataset is displayed under in Xena Datapages, describe what data is in the life",
    "map": [
      {
        "label": "display label of the map",
        "dataSubType": "embedding",
        "dimension": ["UMAP_1","UMAP_2","UMAP_3"]
      }
    ]
}
```

## survival time unit
Surival time unit is displayed on the x-axis of the KM plot. You specify it in metadata file under the **"units"** attribute. 

**"units"** free text , KM plot x-axis unit, e.g. years, months, days

example
```json
{
    "cohort": "TCGA Breast Cancer (BRCA)", 
    "dataSubType": "phenotype", 
    "label": "Curated survival data", 
    "type": "clinicalMatrix", 
    "units": {
        "OS": "days",
        "DSS": "days",
        "DFI": "days",
        "PFI": "days"
    }
}

```
