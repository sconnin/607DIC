# 607DIC
This repository contains files constructed for a Data In Context presentation on 02/24/21 by the author. The presentation offered an example strategy for identifying and eliminating erroneous spatial data from a tablular data set. 

The dataset (dirty_solar_data) derives from NYSUN's solar project queue (see: https://data.ny.gov/Energy-Environment/Solar-Electric-Programs-Reported-by-NYSERDA-Beginn/3x8r-34rs) and has been altered by the author to create mistakes in coordinate location and related labels. 

A subset of this data (dirty_adk_data) has been saved, respresenting 14 counties of NYS. This data also includes errors. 

Steps described to identify and correct these mistakes during the presentation (see: DIC_GIS.pdf):

1. Load both data sets into QGIS as delimited text files (Layer>Add Layer>Text Delimited Layer), set the coordinate system to WGS84-EPSG4326. These will appear as individual "layers" on the map.

2. Load the ANCA 14 Counties Shoreline Dissolved.shp shapefile (boundary for the 14 county area) into QGIS as a vector layer. Note that this file includes a number of extensions which should be included in your project folder. I've also included an additional shoreline shapefile. How is it different? What might happen if it is selected for Step 4?

3. Not that a number of dirty_adk_data points lay outside the perimeter of the boundary. These data have coordinate/label errors.

4. Use the vector > geoprocessing > intersect tool to "clip" the dirty_adk_data with the shorelines.shp layer. The intersection will
create an intersection layer that excludes these errors. 

5. Right click on the intersection layer (located under the Layers window) and select > Export > Save Feature As > .......

Notes: 
These files should be downloaded to desktop into a common project folder. 
Ensure that csv and shp files are projected to WGS84-EPSG4326.
This outline assumes some basic knowledge of GIS software and use. 


