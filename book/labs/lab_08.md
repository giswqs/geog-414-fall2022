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

# Lab 8

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

**Image Overlay:**  Create a map to visualize [NOAA GFS Temperature Data](https://developers.google.com/earth-engine/datasets/catalog/NOAA_GFS0P25) and add a color bar and [NOAA logo](https://www.noaa.gov/sites/default/files/2022-03/noaa_emblem_logo-2022.png) to the map. 

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/G3z6JBA.png)

+++

## Question 2

**Linked Maps:** Create a 2*2 linked map to visualize the Landsat imagery (`ee.Image('LANDSAT/LE7_TOA_5YEAR/1999_2003')`) with different band combinations.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/QDNuFaS.gif)

+++

## Question 3

**Timeseries Inspector:** Create a map with timeseries inspector to visualize [USDA NASS Cropland Data Layers](https://developers.google.com/earth-engine/datasets/catalog/USDA_NASS_CDL) from 2010 to 2021.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/ZzkXB5g.gif)

+++

## Question 4

**Time slider:** Create a map with the time slider to visualize [Sentinel-2](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S2_SR) for Knoxville, TN.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/SCWDCQO.gif)

+++

## Question 5

**Split-panel Map:** Use the following datasets to create a split-panel map for visualizing the ESA land cover data in the US. Add the ESA land cover legend to the map (Hint: the built-in legend for ESA land cover is `ESA_WorldCover`).

- [US Census States](https://developers.google.com/earth-engine/datasets/catalog/TIGER_2018_States): `ee.FeatureCollection("TIGER/2018/States")`
- [ESA WorldCover 10m](https://developers.google.com/earth-engine/datasets/catalog/ESA_WorldCover_v100): `ee.ImageCollection("ESA/WorldCover/v100")`
- Landsat: `LANDSAT/LE7_TOA_5YEAR/1999_2003`

+++

Currently, the split-map control of ipyleaflet plotting backend has a bug ([source](https://github.com/jupyter-widgets/ipyleaflet/issues/1066)). Use the folium plotting backend instead.

```{code-cell} ipython3
import geemap.foliumap as geemap  
```

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/VUAT8tZ.gif)
