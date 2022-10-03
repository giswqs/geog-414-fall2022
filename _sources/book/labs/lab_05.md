---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Lab 5

**Firstname Lastname**

```{code-cell} ipython3
from datetime import datetime

now = datetime.now()
print(f"Submitted time: {now}")
```

## Readings

- [3.3 Earth Engine data types](https://book.geemap.org/chapters/03_gee_data.html#earth-engine-data-types)
- [3.4. Earth Engine Data Catalog](https://book.geemap.org/chapters/03_gee_data.html#earth-engine-data-catalog)

+++ {"tags": []}

## Question 1

Find a DEM dataset in the [Earth Engine Data Catalog](https://developers.google.com/earth-engine/datasets/), clip the DEM to your home state, and display the DEM with a proper color palette on the map. For example, the sample map below shows the DEM of the state of Colorado.

```{code-cell} ipython3
import ee
import geemap
```

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/B70UGZV.png)

+++

## Question 2

Use [Sentinel-2](https://developers.google.com/earth-engine/datasets/catalog/sentinel-2) or [Landsat-9 data](https://developers.google.com/earth-engine/datasets/catalog/landsat-9), create a cloud-free imagery of the year 2021 for your home state. Display the imagery on the map with a proper band combination. For example, the sample map below shows a cloud-free false-color composite of Sentinel-2 imagery of the year 2021 for the state of Colorado.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/lqqgeSW.png)
