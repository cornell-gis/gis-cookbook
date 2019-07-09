# Labels with callout lines

Callouts, sometimes called leader lines, are lines between labels and features on a map.
They are useful when constraints of space force a label to be moved away from the
feature.  The callout helps to reconnect the label to the feature it refers to.

![image](https://user-images.githubusercontent.com/3355358/40939594-2bbc2588-6813-11e8-85cc-cd51da7cf6de.png)

There are probably multiple ways to do this, but here is one way using a geometry generator in QGIS 3.x:

![callouts_qgis](https://user-images.githubusercontent.com/3355358/40941874-5d0e364c-681a-11e8-8f6b-e7ee816378d2.gif)

## 1. Turn on labels for the layer
- Style dock > Labels tab
- Change "No labels" to "Show labels for this layer"
- Select the field to "Label with"

## 2. Move individual labels
The upgrade to QGIS 3.0 has made label placement easier to customize.  When you move a label, QGIS tracks the new location using hidden auxiliary storage fields that we'll use to draw the lines.
- Make sure the Label Toolbar is enabled (View menu > Toolbars)
- Select the "Move Label" tool ![image](https://user-images.githubusercontent.com/3355358/40940755-ce4db372-6816-11e8-8fcf-ecaf66dfa25a.png)
- Click and drag the to move the labels. (The first time you click to move a label, you will be asked for a primary key to use for tracking the labels.  Pick a field that has an id or otherwise unique values within your layer.)

## 3. Add the callout lines
- In the layer styling dock, click the green `+` to add a new marker component
- Set "Symbol layer type" to "Geometry generator"
- Set "Geometry Type" to "LineString / MultiLineString"
- Enter the following expression:
```
make_line(
  make_point($x, $y),
  make_point( "auxiliary_storage_labeling_positionx" , "auxiliary_storage_labeling_positiony" )
)
```
![image](https://user-images.githubusercontent.com/3355358/40941554-2d005e2c-6819-11e8-940b-86e61f583eea.png)
    
## 4. Improve the label display
- Add label buffers ("halos") so that the lines won't obscure the text of the label (3rd tab in the style dock)
- Adjust the label placement (6th tab in the style dock), data defined > alignment
    - set the horizontal alignment to 'Center'
    - set the vertical alignment to 'Half'
