---
title: Getting Setup
---
# Installs
Disclaimer, all of these instructions are aimed at Linux users.

There are two main pieces of software that are needed and a couple of plugins to help make life easier:
1. [QGIS](https://www.qgis.org/en/site/): An open source Geographic Information System (GIS). Available on most Linux distributions directly from the package manager
    1. I had to install `gdal`, `python-gdal`, and `python-psycopg2` (possibly `python3` instead of `python`, depending on distro). It still throws `ModuleNotFoundError: No module named 'owslib'`, but hasn't negatively impacted the tool, so that error persists.
    1. The [GRASS](https://grass.osgeo.org/) program, which can be called from QGIS, will also come in handy later
1. [Inkscape](https://inkscape.org/): An open source vector drawing program. Also available on most distros from the package manager.

# File Downloads

## Topographical Data

If the desired map location is in the United States, the US Geological Survey (USGS) provides a nice [website](https://apps.nationalmap.gov/downloader/) for downloading topographical data. 
1. Navigate to the aforementioned website
1. Zoom the map into the desired region
1. (Optional) Select "Extent" and draw a rectangle on the map to narrow down the search. Otherwise the whole visible area will be the search region.
1. Under "Data" Select "Elevation Products (3DEP)". This will ensure that the result is a digital elevation map that QGIS can interpret.
1. Feel free to play around with the defaults for "Subcategories", "Extent", etc, but the defaults seem to work well enough.
1. Scroll back up and hit the "Search Products" button. If all goes well, something similar will appear
[![usgs_results][1]][1]

[1]: ./pictures/usgs_results.png
1. Click "Downlink Link (TIF)". This may take a moment as the files can be pretty large, this one is 424 MB.
1. Repeat as many times as necessary to cover the desired region. It's possible to stitch the files together later on, so don't worry if the region spans two files. When available, it's best to have data for a region that's a bit larger than the final product. More on that later.

If the map location is outside of the US, searching for "digital elevation map \<country\>" or looking through [OpenDEM](https://opendem.info/opendemsearcher.html) will probably turn up the necessary files.

## Human Made Features

Where to find these datasets will vary a little more. Similarly searching for "shapefile \<region\>" or "GIS \<region\>" is likely to provide something useful, such as this [Yosemite website](https://www.nps.gov/yose/learn/nature/gis-resources.htm) listing out all of their GIS related resources. 

[OpenStreetMap](http://download.geofabrik.de/) data is a good place to start, and in the US, the [Census Bureau](https://www.census.gov/cgi-bin/geo/shapefiles/index.php) provides everything from school district boundaries to roads, updated on a yearly cadence. 

Download the desired files and put them in a folder with the DEM data.

# Next Steps

Onto [Making A Map](./making_a_map.html) or back to the [index](./index.html).
