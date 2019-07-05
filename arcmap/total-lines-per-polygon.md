# Total lines per polygon

Suppose you have one layer of road lines (`ROAD`) and another layer of state polygons (`STATE`), and want to calculate the total road length within each state. This tutorial shows how, and these same steps can be applied to any similar problem of summing any line lengths within any set of polygons (for example, total river lengths per country).

Solution
From the toolbox, select Analysis Tools > Overlay > Identity, and set the following parameters:
- Input Features = `ROAD`
- Identity Features = `STATE`
- Output Feature Class = `ROAD_Identity`
- JoinAttributes = "ALL"

This splits roads at the state borders, and creates a new layer (`ROAD_Identity`), which contains all the `ROAD` and related `STATE` attributes for each road segment. We now need to recalculate the length of these new road segments:

- Open the `ROAD_Identity` attribute table
- Options > Add field > "NewLength"
- Right-click the "NewLength" column header > Calculate Geometry > Length (m)

Next we sum the road lengths by state. From the toolbox, select Analysis Tools > Statistics > Summary Statistics, and set the following parameters:

- Input Table = `ROAD_Identity`
- Output Table = `ROAD_Stats.dbf`
- Statistics Field = `NewLength` ... Statistic Type = 'SUM'
- Case Field = `STATEABBR` (or some other field that uniquely identifies each state)

This creates a new table (`ROAD_Stats.dbf`), with each row containing the `STATEABBR` and the total road length for the corresponding state. You will need to click the "Source" tab in the data frame in order to see the `ROAD_Stats.dbf` table.

Join this data to the state attribute table using the `STATEABBR` field – for details, see the [Join Table](arcmap/join-table.md) recipe.
