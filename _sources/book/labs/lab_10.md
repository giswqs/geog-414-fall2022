---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.14.0
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

# Lab 10

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

Use the following datasets to create a cloud-free imagery for Knox County, TN for the year of 2021.

- [Sentinel-2 MSI](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S2_SR_HARMONIZED): `ee.ImageCollection("COPERNICUS/S2_SR_HARMONIZED")`
- [US Census Counties](https://developers.google.com/earth-engine/datasets/catalog/TIGER_2018_Counties): `ee.FeatureCollection('TIGER/2018/Counties')`

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/82PY5uM.png)

+++

## Question 2

Download the cloud-free imagery created in Question 1 to your computer. You might need to specify `region`, `scale`, and `crs` when downloading the imagery. If you are not sure about the `crs`, check the first image in the resulting collection like this:

`collection.first().select(0).projection().getInfo()`

```{code-cell} ipython3

```

```{code-cell} ipython3

```

## Question 3

Create a fishnet of 5 rows * 5 cols covering Knox County and download the cloud-free imagery created in Question 1 by fishnet.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/hqJeJoA.png)

+++

## Question 4

Create a Landsat timelapse (1984-2022) for Knox County, TN. 

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/ggw5d31.gif)

+++

## Question 5

Create a NAIP imagery timelapse for Knox County, TN. 

```{code-cell} ipython3

```

```{code-cell} ipython3

```

+++ {"tags": []}

![](https://i.imgur.com/Aat7dIB.gif)
