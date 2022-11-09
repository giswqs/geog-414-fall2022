---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.14.1
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Lab 9

**Firstname Lastname**

```{code-cell} ipython3
from datetime import datetime

now = datetime.now()
print(f"Submitted time: {now}")
```

```{code-cell} ipython3
# !pip install geemap
```

```{code-cell} ipython3
import ee
import geemap
```

```{code-cell} ipython3
geemap.ee_initialize()
```

+++ {"tags": []}

## Question 1

Use the following datasets to create an interactive map with two layers: the elevation layer for Tennessee and county boundary layer for Tennessee. Add a color bar for the elevation layer.


- [US Census Counties](https://developers.google.com/earth-engine/datasets/catalog/TIGER_2018_Counties): `ee.FeatureCollection('TIGER/2018/Counties')`
- [NASA SRTM Digital Elevation 30m](https://developers.google.com/earth-engine/datasets/catalog/USGS_SRTMGL1_003): `ee.Image("USGS/SRTMGL1_003")`

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/wzUOUXj.png)

+++

## Question 2

Use zonal statistics to find out the mean elevation of each county in Tennessee. Create a bar chart to show the mean elevation of counties in Tennessee.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/RNFs8g9.png)

+++

## Question 3

Select the top 3 counties with the highest mean elevation and highlight them on the map (e.g., adding as a new layer).

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/aANMfGi.png)

+++

## Question 4

Use the following datasets to create an interactive map with two layers: the landcover layer for Tennessee and the county boundary layer for tennessee. Add the corresponding legend for the land cover layer. 

 - [ESA WorldCover 10m](https://developers.google.com/earth-engine/datasets/catalog/ESA_WorldCover_v100): `ee.ImageCollection("ESA/WorldCover/v100")`
 - [US Census Counties](https://developers.google.com/earth-engine/datasets/catalog/TIGER_2018_Counties): `ee.FeatureCollection('TIGER/2018/Counties')`

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/UTdjvX8.png)

+++

## Question 5

Use zonal statistics by group to find out the cropland area by county. Create a bar chart and pie chart to show the cropland area by county.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/5JZEBGM.png)

```{code-cell} ipython3

```

![](https://i.imgur.com/5UFWnfF.png)
