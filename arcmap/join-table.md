# Join tabular data

Suppose you have one layer of state borders (`STATE`), and want to add some additional data (`MYDATA`) that you have collected for each state. This tutorial shows how, and these same steps can be applied to any similar problem of adding tabular data to an existing set of points, lines, or polygons.

ArcMap can import tabular data from a variety of formats, including:
- Comma-separated values (.csv)
- Tab-delimited files (.csv, .txt)
- Dbase files (.dbf)
- Microsoft Excel files (.xls)

If you have difficulties importing your table into ArcMap, check that:
- The first row contains the column headers (field names)
- Column headers only contain alphanumeric (a-z, A-Z, 0-9) and underscore ("_") characters

Load your borders and your table into ArcMap. In order to join the data, there must be a column in both sources that contains the same identifier for each state. In this example, our `STATE` layer has a column named `STATEABBR`, which contains the 2-letter U.S. postal code for the state, but the `MYDATA` table has a column named `STATECODE`. (The columns don't have to have the same name, just the same values.)

In the data frame, right-click on your borders layer, and select `Joins and Relates > Join...` and set the following parameters:
- What do you want to join to this layer? = Join attributes from a table
- Choose the field in this layer that the join will be based on = `STATEABBR`
- Choose the table to join to this layer... = `MYDATA`
- Choose the field in the table to base the join on = `STATECODE`

You may open the attribute table to confirm that the join succeeded. To permanently add these new columns, right-click the `STATE` layer and select `Data > Export Data...` and set the following parameters:
- Export = All features
- Use the same coordinate system as = this layer's source data
- Output shapefile or feature class = (enter path to new file here)

After saving, you will be prompted "Do you want to add the exported data to the map as a layer?" In most cases, yes. At this point, you could also remove the original STATE layer from the data frame.
