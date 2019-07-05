# Convert data to CAD format

ArcMap can convert shapefiles and other vector datasets to CAD format for use in programs such as Rhino and AutoCAD.

1. Start ArcMap (Start menu > All Programs > ArcGIS)
2. Open ArcToolbox by clicking the  icon in the ArcMap toolbar
3. Open Conversion Tools > To CAD > Export to CAD
4. Under Input Features, click the folder icon and navigate to the shapefile you wish to convert. (You may select and convert several files at once.)
5. Under Output Type, select the CAD format you wish to create. (probably "DWG_R2010" for AutoCAD)
6. Under Output File, click the folder icon to specify a location and name
7. Check "Ignore Paths in Tables" to create a single file, leave unchecked to create multiple files using paths in document entity fields (this may or may not be relevant depending on GIS files).
8. Click OK to export. (This may take some time depending on file size/complexity).

For more information on this conversion process and how it works, see the official [Export to CAD](http://desktop.arcgis.com/en/arcmap/latest/tools/conversion-toolbox/export-to-cad.htm) webpage.  Esri also has a free plug-in called [ArcGIS for AutoCAD](https://www.esri.com/en-us/arcgis/products/arcgis-for-autocad) that provides enhanced functionality for working with GIS files within AutoCAD.
