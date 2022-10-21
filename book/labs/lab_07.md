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

# Lab 7

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

Visualize the [USGS Watershed Boundary Dataset](https://developers.google.com/earth-engine/datasets/catalog/USGS_WBD_2017_HUC04) with outline color only, no fill color.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/oFyEZpD.png)

+++

## Question 2

Filter the USGS Watershed Boundary dataset and select the watershed that intersects Knox Country, TN

```{code-cell} ipython3

```

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/dEXq0Ci.png)

+++

## Question 3

Clip the [USGS 3DEP 10m DEM](https://developers.google.com/earth-engine/datasets/catalog/USGS_3DEP_10m) the watershed that intersects Knox County, TN. Display the DEM with a proper color palette and color bar.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/pXSDGrH.png)

+++

## Question 4

Use the [USGS National Land Cover Database](https://developers.google.com/earth-engine/datasets/catalog/USGS_NLCD_RELEASES_2019_REL_NLCD) and [US Census States](https://developers.google.com/earth-engine/datasets/catalog/TIGER_2018_States) to create a split-panel map for visualizing land cover change (2001-2019) for a selected state. Make sure you add the NLCD legend to the map.

```{code-cell} ipython3

```

```{code-cell} ipython3

```

```{code-cell} ipython3

```

![](https://i.imgur.com/0GNX5x3.png)
