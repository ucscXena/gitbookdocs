---
description: metadata (.json file) specification for maps and survival time unit
---

# Metadata Specification

## MAPs

MAPs are tsne, umap, pca embeddings in 2D or 3D, or spatial maps for spatical data.

**map** is a list in the .json metadata file

For each map

**"label"** free text. Display label of the map, should be easily readable by users

**"dataSubType"** a string. Describe the natur of the map, must be **embedding**, **spatial** . Note this is the dataSubType attribute for the map, not the dataSubType attribute for the file

**"dimension"** a list of strings. They are the column headers of the dimention columns in the data file. They are used to retrieve data from db.

If it is a spatial map, there might be microscopy image\(s\) associated with each map.

**"unit"** \(optional, only relevent to spatial map\) a string. The unit of map values, e.g. pixel, micrometer

**"micrometer\_per\_unit"** \(optional, only relevent to spatial map\) a floting point number. The physical size in micrometer \(µm\) of value =1 . The parameter will be used in rendering scale bar is the spatil map. If not specified, scale will not be shown.

**"spot\_diameter"** \(optional, relevant to spatial map\) a floting point number. The parameter will be used to determine sphere size shown in spatial map. If not specified, the size of the sphere will be dertermined by the browser.

**"image"** \(optional, only relevant to a spatial map\) an array of images, each image is a json object. See below.

For each image

**"label"** free text. Display label of the image, should be easily readable by users

**"channel"** json object. Key-value pairs. Key is color, value is of each color channel is represented, such as DAPI.

**"path"** file path to the image file

**"size"** an array of intergers. Image size in pixels.

**"offset"** an array of intergers. Image offset in pixel unit in this image in x and y dimension. See below for conversion from spatial coordinate values in map to pixel position in this image.

**"image\_scalef"**: floating point number. A scaling factor that converts spatial coordinate values in the spatial map \(e.g. pixel or micrometer\) to the pixel unit in this image. It works together with the "offset" parameter to convert spatial coordinate values in the spatial map to the actual pixel positions in this image.

* pixel\_in\_image\_x =  image\_scalef \* spatial\_coordinate\_x + offset\_x
* pixel\_in\_image\_y =  image\_scalef \* spatial\_coordinate\_y + offset\_y

Example, map without image

```javascript
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

Example, spatial map with matching microscopy image

```javascript
{
    "type": "clinicalMatrix",
    "cohort": "name of the cohort",
    "label": "display label of the file",
    "dataSubType": "the section the dataset is displayed under in Xena Datapages, describe what data is in the life",
    "map": [
    {
        "label": "display label of the map",
        "dataSubType": "embedding",
        "dimension": ["UMAP_1","UMAP_2","UMAP_3"],
        "unit": "pixel",
        "spot_diameter": 178.37655999999998,
        "micrometer_per_unit": 0.3083364764966877,
        "image": [
            {
                "label": "display label of the image",
            "channel":
            {
                "red":"CD45",
                "green":"Pan-Cytokeratin",
                "blue":"DAPI"
            },
            "path": "image file path",
            "size": [24240, 24240],
            "offset": [0,0],
            "image_scalef": 1,
            },
            {
            "label": "display label of the image",
            "channel":
            {
                "red":"CD45",
                "green":"Pan-Cytokeratin"
            },
            "path": "image file path",
            "size": [2000, 2000],
            "offset": [0,0],
            "image_scalef": 0.08250825
            }]
      }]
}
```

## SURVIVAL TIME UNIT

Surival time unit is displayed on the x-axis of the KM plot. You specify it in metadata file under the **"units"** attribute.

**"units"** free text , KM plot x-axis unit, e.g. years, months, days

example

```javascript
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

## COLUMN DISPLAY NORMALIZATION\

For genomic data matrix, the optional metadata parameter _colNormalization_ sets the default display scale. If not specified, the browser automatically determines the scale.

**colNormalization**: ‘true’ \| ‘log2\(x\)’ \| ‘normal2’

* true: display centerred by column mean, x - column average, example usage is gene expression matrix that already log transformed. 
* log2\(x\): display in log2\(x+1\) scale, example usage is count matrix 
* normal2: display value of 2 in the background color \(i.e. white\), typically used for copy number data where the normal = 2

example

```javascript
{
     "cohort": "TCGA Acute Myeloid Leukemia (LAML)",
     "dataSubType": "gene expression RNAseq",
     "label": "IlluminaHiSeq",
     "colNormalization": true,
     "type": "genomicMatrix",
     "unit": "log2(norm_count+1)"
}
```

