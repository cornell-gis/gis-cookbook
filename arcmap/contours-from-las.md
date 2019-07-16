# Creating contour lines from .las LiDAR data

LiDAR pointcloud datasets are collections of three-dimensional x,y,z data, often distributed in LAS format with a .las filename extension.  LAS files can be downloaded from sites such as [OpenTopography.org](https://opentopography.org/) and the [US Interagency Elevation Inventory](https://coast.noaa.gov/inventory/).

1. After downloading the .las data, [create an LAS dataset](http://desktop.arcgis.com/en/arcmap/latest/manage-data/las-dataset/creating-a-las-dataset.htm) in ArcCatalog.
2. Convert that dataset into raster format using the [LAS Dataset to Raster tool](http://desktop.arcgis.com/en/arcmap/latest/manage-data/raster-and-images/las-dataset-to-raster-function.htm) (Conversion Tools > To Raster > LAS Dataset to Raster). You may need to define the projection.
3. Then use [the Contour tool](http://desktop.arcgis.com/en/arcmap/latest/tools/spatial-analyst-toolbox/contour.htm)  (Spatial Analyst Tools > Surface > Contour) to generate your contours. You may need to first turn on the Spatial Analyst Extension from the Customize menu.
4. If you need **convert the contours into CAD format** (optional), here’s how you can export elevation contours from ArcGIS to DWG as 3D lines:
    - In order to keep the z values, there must be an attribute field called "elevation".
    - The ArcGIS tool for generating the contours (ArcToolbox> Analyst Tools>Surface>Contour) creates a field called "CONTOUR",  so all you have to do is create a new field called "elevation" and copy the values from "CONTOUR". The steps are spelled out in the pink box [on this page](https://web.archive.org/web/20150212072402/http://www.gsd.harvard.edu/gis/manual/cad/).
    - After that, simply right-click the contour layer, selecting Data>Export to CAD... and select the latest DWG format ("DWG_R2010")
