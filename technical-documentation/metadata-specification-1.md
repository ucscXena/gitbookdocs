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

**"micrometer\_per\_pixel\_fullres"** \(optional, only relevent to spatial map\) a floting point number. The physical size of a pixel in micrometer \(µm\) in a full-resolution image.

**"spot\_diameter\_fullres"** \(optional, relevant to spatial map, visium platform\) a floting point number. The number of pixels that span the diameter of a tissue spot in the original, full-resolution image. The parameter will be used in rendering scale bar is the spatil map.

**"image"** \(optional, only relevant to a spatial map\) an array of images, each image is a json object. See below.

For each image

**"label"** free text. Display label of the image, should be easily readable by users

**"channel"** json object. Key-value pairs. Key is color, value is of each color channel is represented, such as DAPI.

**"path"** file path to the image file

**"size"** an array of intergers. Image size in pixels.

**"offset"** an array of intergers. Image offset in pixels. The offset converts spatial map coordinate to its corresponding pixel position in the full-resolution image.

**"image\_scalef"**: floating point number. A scaling factor that converts pixel positions in the original, full-resolution image to pixel positions in this image.

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
        "spot_diameter_fullres": 178.37655999999998,
        "micrometer_per_pixel_fullres": 0.3083364764966877,
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

