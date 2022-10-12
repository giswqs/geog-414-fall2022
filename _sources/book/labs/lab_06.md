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

# Lab 5

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

## Datasets

The datasets being used in the lab are listed below:

- [TIGER: US Census Counties](https://developers.google.com/earth-engine/datasets/catalog/TIGER_2018_Counties)
- [Landsat-9](https://developers.google.com/earth-engine/datasets/catalog/LANDSAT_LC09_C02_T1_L2)
- [Sentinel-2](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S2_SR)
- [NAIP](https://developers.google.com/earth-engine/datasets/catalog/USDA_NAIP_DOQQ)

+++ {"tags": []}

## Question 1

Write a program to find out how many counties are named `Knox` in the US.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

```{code-cell} ipython3

```

```{code-cell} ipython3

```

## Question 2

Display Knox county of Tennesse with outline only (no fill color) on the map. (Hint: The `STATEFP` of Tennessee is `47`)

```{code-cell} ipython3

```

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/F8hJB13.png)

+++

## Question 3

Use [Landsat-9](https://developers.google.com/earth-engine/datasets/catalog/LANDSAT_LC09_C02_T1_L2) data to create a cloud-free imagery for Knox County, TN. Display the imagery on the map with a proper band combination.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/jgYaOa4.png)

+++

## Question 4

Use [Sentinel-2](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S2_SR) data to create a cloud-free imagery for Knox County, TN. Display the imagery on the map with a proper band combination.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/r0BpIxW.png)

+++

## Question 5

Use [NAIP](https://developers.google.com/earth-engine/datasets/catalog/USDA_NAIP_DOQQ) imagery to create a cloud-free imagery for Knox County, TN. Display the imagery on the map with a proper band combination.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/0YfuDE8.png)
