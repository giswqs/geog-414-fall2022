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

# Using Local Geospatial Data

```{contents}
:local:
:depth: 2
```

## Introduction

+++

## Technical requirements

```bash
conda create -n gee python
conda activate gee
conda install -c conda-forge mamba
mamba install -c conda-forge geemap pygis
```

```bash
jupyter lab
```

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/giswqs/geebook/blob/master/chapters/04_local_data.ipynb)

```{code-cell} ipython3
# pip install pygis
```

```{code-cell} ipython3
import ee
import geemap
```

```{code-cell} ipython3
geemap.ee_initialize()
```

## Local raster datasets

### Single-band imagery

```{code-cell} ipython3
url = 'https://github.com/giswqs/data/raw/main/raster/srtm90.tif'
filename = 'srtm90.tif'
geemap.download_file(url, filename)
```

```{code-cell} ipython3
Map = geemap.Map()

Map.add_raster(filename, palette='terrain', layer_name="DEM")

vis_params = {'min': 0, 'max': 4000, 'palette': 'terrain'}

Map.add_colorbar(vis_params, label='Elevation (m)')
Map
```

### Multi-band imagery

```{code-cell} ipython3
url = 'https://github.com/giswqs/leafmap/raw/master/examples/data/cog.tif'
filename = 'cog.tif'
geemap.download_file(url, filename)
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_raster(filename, band=[4, 1, 2], layer_name="Color infrared")
Map
```

### Interactive raster GUI

+++

## Cloud Optimized GeoTIFF (COG)

### Visualizing COG

```{code-cell} ipython3
url = 'https://tinyurl.com/24bo8umr'
```

```{code-cell} ipython3
geemap.cog_bounds(url)
```

```{code-cell} ipython3
geemap.cog_center(url)
```

```{code-cell} ipython3
geemap.cog_bands(url)
```

```{code-cell} ipython3
geemap.cog_tile(url)
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_cog_layer(url, name="Fire (pre-event)")
Map
```

```{code-cell} ipython3
url2 = 'https://tinyurl.com/2awjl66w'
Map.add_cog_layer(url2, name="Fire (post-event)")
Map
```

### Creating COG

```{code-cell} ipython3
url = "https://github.com/giswqs/data/raw/main/raster/srtm90.tif"
geemap.cog_validate(url)
```

```{code-cell} ipython3
geemap.cog_validate(url, verbose=True)
```

```{code-cell} ipython3
out_cog = "cog.tif"
geemap.image_to_cog(url, out_cog)
```

```{code-cell} ipython3
geemap.cog_validate(out_cog)
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_raster(out_cog, palette="terrain", layer_name="Local COG")
Map.add_cog_layer(url, palette="gist_earth", name="Remote COG")

vis_params = {'min': 0, 'max': 4000, 'palette': 'gist_earth'}
Map.add_colorbar(vis_params, label='Elevation (m)')
Map
```

### Converting NumPy arrays to COG

```{code-cell} ipython3
url = 'https://github.com/giswqs/leafmap/raw/master/examples/data/cog.tif'
in_cog = 'cog.tif'
out_cog = "ndvi.tif"
geemap.download_file(url, in_cog)
```

```{code-cell} ipython3
arr = geemap.image_to_numpy(in_cog)
```

```{code-cell} ipython3
arr.shape
```

```{code-cell} ipython3
ndvi = (arr[3] - arr[0]) / (arr[3] + arr[0])
```

```{code-cell} ipython3
ndvi.shape
```

```{code-cell} ipython3
geemap.numpy_to_cog(ndvi, out_cog, profile=in_cog)
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_raster(in_cog, band=[4, 1, 2], layer_name="Color infrared")
Map.add_raster(out_cog, palette="Greens", layer_name="NDVI")
Map
```

+++

### Clipping image by mask

```{code-cell} ipython3
url = 'https://github.com/giswqs/data/raw/main/raster/srtm90.tif'
dem = 'dem.tif'
geemap.download_file(url, dem)
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_raster(dem, palette='terrain', layer_name="DEM")
Map
```

```{code-cell} ipython3
mask = (
    'https://raw.githubusercontent.com/giswqs/leafmap/master/examples/data/mask.geojson'
)
```

```{code-cell} ipython3
mask = Map.user_roi
```

```{code-cell} ipython3
mask = [
    [-119.679565, 37.256566],
    [-119.679565, 38.061067],
    [-118.24585, 38.061067],
    [-118.24585, 37.256566],
    [-119.679565, 37.256566],
]
```

```{code-cell} ipython3
output = 'clip.tif'
geemap.clip_image(dem, mask, output)
Map.add_raster(output, palette='coolwarm', layer_name="Clip Image")
Map
```

## SpatioTemporal Asset Catalog (STAC)

```{code-cell} ipython3
url = 'https://tinyurl.com/22vptbws'
```

```{code-cell} ipython3
geemap.stac_bounds(url)
```

```{code-cell} ipython3
geemap.stac_center(url)
```

```{code-cell} ipython3
geemap.stac_bands(url)
```

```{code-cell} ipython3
geemap.stac_tile(url, bands=['B3', 'B2', 'B1'])
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_stac_layer(url, bands=['pan'], name='Panchromatic')
Map.add_stac_layer(url, bands=['B3', 'B2', 'B1'], name='False color')
Map
```

## Vector datasets

### GeoJSON

```{code-cell} ipython3
in_geojson = (
    'https://github.com/giswqs/geemap/blob/master/examples/data/cable_geo.geojson'
)
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_geojson(in_geojson, layer_name="Cable lines", info_mode="on_hover")
Map
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_basemap("CartoDB.DarkMatter")
callback = lambda feat: {"color": "#" + feat["properties"]["color"], "weight": 2}
Map.add_geojson(in_geojson, layer_name="Cable lines", style_callback=callback)
Map
```

```{code-cell} ipython3
url = "https://github.com/giswqs/geemap/blob/master/examples/data/countries.geojson"
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_geojson(
    url, layer_name="Countries", fill_colors=['red', 'yellow', 'green', 'orange']
)
Map
```

```{code-cell} ipython3
import random

Map = geemap.Map()


def random_color(feature):
    return {
        'color': 'black',
        'weight': 3,
        'fillColor': random.choice(['red', 'yellow', 'green', 'orange']),
    }


Map.add_geojson(url, layer_name="Countries", style_callback=random_color)
Map
```

```{code-cell} ipython3
Map = geemap.Map()

style = {
    "stroke": True,
    "color": "#0000ff",
    "weight": 2,
    "opacity": 1,
    "fill": True,
    "fillColor": "#0000ff",
    "fillOpacity": 0.1,
}

hover_style = {"fillOpacity": 0.7}

Map.add_geojson(url, layer_name="Countries", style=style, hover_style=hover_style)
Map
```

### Shapefile

```{code-cell} ipython3
url = "https://github.com/giswqs/geemap/blob/master/examples/data/countries.zip"
geemap.download_file(url)
```

```{code-cell} ipython3
Map = geemap.Map()
in_shp = "countries.shp"
Map.add_shp(in_shp, layer_name="Countries")
Map
```

### KML

```{code-cell} ipython3
in_kml = "https://github.com/giswqs/geemap/blob/master/examples/data/us_states.kml"
```

```{code-cell} ipython3
Map = geemap.Map(center=[40, -100], zoom=4)
Map.add_kml(in_kml, layer_name="US States")
Map
```

### GeoDataFrame

```{code-cell} ipython3
import geopandas as gpd
```

```{code-cell} ipython3
Map = geemap.Map(center=[40, -100], zoom=4)
gdf = gpd.read_file('countries.shp')
Map.add_gdf(gdf, layer_name="US States")
Map
```

### Other vector formats

```{code-cell} ipython3
Map = geemap.Map()
data = 'https://github.com/giswqs/geemap/blob/master/examples/data/countries.gpkg'
Map.add_vector(data, layer_name="Countries")
Map
```

## Creating points from XY

### CSV to vector

```{code-cell} ipython3
data = 'https://github.com/giswqs/geemap/blob/master/examples/data/us_cities.csv'
geemap.csv_to_df(data)
```

```{code-cell} ipython3
geemap.csv_to_geojson(
    data, 'cities.geojson', latitude="latitude", longitude='longitude'
)
```

```{code-cell} ipython3
geemap.csv_to_shp(data, 'cities.shp', latitude="latitude", longitude='longitude')
```

```{code-cell} ipython3
geemap.csv_to_gdf(data, latitude="latitude", longitude='longitude')
```

```{code-cell} ipython3
geemap.csv_to_vector(data, 'cities.gpkg', latitude="latitude", longitude='longitude')
```

### Adding points from XY

```{code-cell} ipython3
cities = 'https://github.com/giswqs/geemap/blob/master/examples/data/us_cities.csv'
regions = (
    'https://github.com/giswqs/geemap/blob/master/examples/data/us_regions.geojson'
)
```

```{code-cell} ipython3
Map = geemap.Map(center=[40, -100], zoom=4)
Map.add_points_from_xy(data, x="longitude", y="latitude")
Map
```

```{code-cell} ipython3
Map = geemap.Map(center=[40, -100], zoom=4)

Map.add_geojson(regions, layer_name='US Regions')

Map.add_points_from_xy(
    data,
    x='longitude',
    y='latitude',
    layer_name='US Cities',
    color_column='region',
    icon_names=['gear', 'map', 'leaf', 'globe'],
    spin=True,
    add_legend=True,
)
Map
```

### Circle markers from points

```{code-cell} ipython3
data = 'https://github.com/giswqs/geemap/blob/master/examples/data/us_cities.csv'
```

```{code-cell} ipython3
Map = geemap.Map(center=[40, -100], zoom=4)
Map.add_circle_markers_from_xy(
    data,
    x="longitude",
    y="latitude",
    radius=10,
    color="blue",
    fill_color="black",
    fill_opacity=0.5,
)
Map
```

## Vector data to Earth Engine

```{code-cell} ipython3
in_geojson = (
    'https://github.com/giswqs/geemap/blob/master/examples/data/countries.geojson'
)
Map = geemap.Map()
fc = geemap.geojson_to_ee(in_geojson)
Map.addLayer(fc.style(**{'color': 'ff0000', 'fillColor': '00000000'}), {}, 'Countries')
Map
```

```{code-cell} ipython3
url = "https://github.com/giswqs/geemap/blob/master/examples/data/countries.zip"
geemap.download_file(url)
```

```{code-cell} ipython3
in_shp = "countries.shp"
fc = geemap.shp_to_ee(in_shp)
```

```{code-cell} ipython3
import geopandas as gpd

gdf = gpd.read_file(in_shp)
fc = geemap.gdf_to_ee(gdf)
```

```{code-cell} ipython3
fc = geemap.vector_to_ee(url)
```

## Joining attribute tables

```{code-cell} ipython3
Map = geemap.Map()
countries = ee.FeatureCollection(geemap.examples.get_ee_path('countries'))
Map.addLayer(countries, {}, 'Countries')
Map
```

```{code-cell} ipython3
geemap.ee_to_df(countries)
```

```{code-cell} ipython3
data = (
    'https://github.com/giswqs/geemap/blob/master/examples/data/country_centroids.csv'
)
df = geemap.csv_to_df(data)
df
```

```{code-cell} ipython3
fc = geemap.ee_join_table(countries, data, src_key='ISO_A2', dst_key='country')
```

```{code-cell} ipython3
geemap.ee_to_df(fc)
```

```{code-cell} ipython3
Map.addLayer(fc, {}, 'Countries with attr')
Map
```

## Converting NetCDF to ee.Image

```{code-cell} ipython3
import os
```

```{code-cell} ipython3
url = 'https://github.com/giswqs/geemap/blob/master/examples/data/wind_global.nc'
nc_file = 'wind_global.nc'
if not os.path.exists(nc_file):
    geemap.download_file(url)
```

```{code-cell} ipython3
Map = geemap.Map()
img = geemap.netcdf_to_ee(nc_file=nc_file, var_names='u_wind')
vis_params = {'min': -20, 'max': 25, 'palette': 'YlOrRd', 'opacity': 0.6}
Map.addLayer(img, vis_params, "u_wind")
Map
```

```{code-cell} ipython3
Map = geemap.Map()
img = geemap.netcdf_to_ee(nc_file=nc_file, var_names=['u_wind', 'v_wind'])
Map.addLayer(
    img,
    {'bands': ['v_wind'], 'min': -20, 'max': 25, 'palette': 'coolwarm', 'opacity': 0.8},
    "v_wind",
)
Map
```

## OpenStreetMap data

### OSM to GeoDataFrame

```{code-cell} ipython3
gdf = geemap.osm_to_gdf("Knoxville, Tennessee")
gdf
```

### OSM to ee.FeatureCollection

```{code-cell} ipython3
Map = geemap.Map()
fc = geemap.osm_to_ee("Knoxville, Tennessee")
Map.addLayer(fc, {}, "Knoxville")
Map.centerObject(fc, 11)
Map
```

### Downloading OSM data

```{code-cell} ipython3
Map = geemap.Map()
gdf = geemap.osm_gdf_from_geocode("New York City")
Map.add_gdf(gdf, layer_name="NYC")
Map
```

```{code-cell} ipython3
place = "Bunker Hill, Los Angeles, California"
tags = {"building": True}
gdf = geemap.osm_gdf_from_place(place, tags)
gdf
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_gdf(gdf, layer_name="Los Angeles, CA")
Map
```

```{code-cell} ipython3
gdf = geemap.osm_gdf_from_address(
    address="New York City", tags={"amenity": "bar"}, dist=1500
)
gdf
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_gdf(gdf, layer_name="NYC bars")
Map
```

```{code-cell} ipython3
gdf = geemap.osm_gdf_from_point(
    center_point=(46.7808, -96.0156),
    tags={"natural": "water"},
    dist=10000,
)
gdf
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_gdf(gdf, layer_name="Lakes")
Map
```

```{code-cell} ipython3
Map = geemap.Map(center=[40.7500, -73.9854], zoom=16)
Map
```

```{code-cell} ipython3
Map.add_osm_from_view(tags={"amenity": "bar", "building": True})
```

## Reading PostGIS data

```bash
mamba install sqlalchemy psycopg2 -c conda-forge
```

```{code-cell} ipython3
con = geemap.connect_postgis(
    database="nyc", host="localhost", user=None, password=None, use_env_var=True
)
```

```{code-cell} ipython3
sql = 'SELECT * FROM nyc_neighborhoods'
gdf = geemap.read_postgis(sql, con)
gdf
```

```{code-cell} ipython3
Map = geemap.Map()
Map = geemap.gdf_to_ee(gdf)
Map.addLayer(fc, {}, "NYC EE")
Map.centerObject(fc)
Map
```

```{code-cell} ipython3
Map = geemap.Map()
Map.add_gdf_from_postgis(
    sql, con, layer_name="NYC Neighborhoods", fill_colors=["red", "green", "blue"]
)
Map
```

## Summary

## References

- https://geemap.org/notebooks/25_load_rasters/
- https://geemap.org/notebooks/44_cog_stac/
- https://geemap.org/notebooks/56_local_data/
- https://geemap.org/notebooks/68_netcdf_to_ee/
- https://geemap.org/notebooks/83_local_tile/
- https://geemap.org/notebooks/58_add_vector/
- https://geemap.org/notebooks/74_csv_to_points/
- https://geemap.org/notebooks/76_osm_to_ee/
- https://geemap.org/notebooks/80_point_layer/
- https://geemap.org/notebooks/83_local_tile/
- https://geemap.org/notebooks/84_openstreetmap/
- https://geemap.org/notebooks/85_postgis/
- https://geemap.org/notebooks/87_add_points_from_xy/
- https://geemap.org/notebooks/88_circle_markers/
- https://geemap.org/notebooks/95_create_cog/
- https://geemap.org/notebooks/97_join_table/
- https://geemap.org/notebooks/100_numpy_to_cog/
- https://geemap.org/notebooks/104_clip_image/
