# Georeference scanned maps using coordinate marks (ArcGIS)

## Define Projection
1. In ArcCatalog, from the left Explorer pane, find the scanned image and right click.
2. Select Properties, then scroll down to Spatial Reference section, clicking the Edit button.
3. Click the Select button and find the coordinate system that matches what is printed on the map, then click Add, then OK. Click OK one more time to save changes

## Georeference Image
1. Open ArcMap
2. Import projected image file (go ahead and build pyramids if asked -this will allow image to load faster)
3. Zoom into an area (e.g. tic mark or grid intersection) where coordinates (in defined projection) are clearly discernable.
4. Turn on the Georeferencing toolbar if necessary (right click top toolbar area and check option).
5. Make sure the image is selected as the Georeferencing layer on toolbar.
6. Click the Add Control Points tool.
7. First left click the point on map image you want to enter coordinates for, then right click on same spot and select Input X and Y.
8. Enter X (vertical lines/parallels) and Y (horizontal lines/parallels) coordinates*. Click OK when done. If needed, click the Full Extent globe icon on top toolbar to restore full view of image.
9. Repeat steps 3-8 several times, spread out and using different XY values/parallels each time if possible.
10. When done, from Georeferencing Toolbar menu, select Update Georeferencing to save control points.
11. If you would like to save a permanently rectified (warped, or "rubber-sheeted") copy of the raster, from the Georeferencing menu choose Rectify. You will have several format options to choose from.

Pay close attention to coordinate system information on map -reference marks may be in particular units of measurement, and need to be converted for the XY Input values. For example, marks may represent 1000 meter grid intervals, and need to be multiplied by 1000. Longitude and latitude XY values will need to be entered in Decimal Degrees. There are 60 seconds per minute, 60 minutes per degree, so to convert Degrees (dd) Minutes (mm) Seconds (ss) format to Decimal Degrees (dd.ff), use formula: dd.ff = dd + mm/60 + ss/36000

Also for longitude/latitude XY coordinates, remember to add a "- " minus sign before values in western or southern hemispheres (respectively).
