.. _sec_pre_attribute_grid:

[Attribute Mapping]
=====================

Attribute Mapping function is described in this page.

In iRIC, grid can have attributes. Attributes can be defined at the 
following positions. Solver developer can decide the character of the grid
attributes: the position and the value type.

- Nodes
- Cells

Grid attributes can be mapped from geographic data. If multiple geographic
data exists in the geographic data folder, the data in the upper side
has higher priority.

Grid attribute mapping is executed automatically after the grid is generated.
Users can manually execute attribute mapping, after editing geographic data,
for example.

[Execute]
-----------

**Description**: Execute grid attribute mapping.

You can execute grid attribute mapping with the
following action:

**Menu bar:** [Grid] (G) --> [Attributes Mapping] (A) --> [Execute] (E)

"Attribute Mapping" dialog (:numref:`image_mapping_exec_dialog`) is shown,
so check on the grid attribute you want to execute mapping, and click on
[OK] button.

.. _image_mapping_exec_dialog:

.. figure:: images/mapping_exec_dialog.png
   :width: 180pt

   [Attribute Mapping] dialog

[Setting] (S)
------------------

**Description**: Edit the setting about grid attribute mapping

You can edit grid attribute mapping setting with the following action:

**Menu bar:** [Grid] (G) --> [Attributes Mapping] (A) --> [Setting] (S)

[Grid Attribute Mapping Setting] dialog is shown, so edit setting, 
and click on [OK] button.

.. _image_mapping_setting_dialog:

.. figure:: images/mapping_setting_dialog.png
   :width: 260pt

   [Grid Attribute Mapping Setting] dialog

.. _sec_geodata_mapping:

About mapping geographic data
---------------------------------

In this section, the algorithm to map geographic data to grid attributes
is described.

[River Survey Data]
~~~~~~~~~~~~~~~~~~~~~~~~

**[Node attribute]**

[Node attribute] values are mapped with the values calculated from the
cross section elevation data. The calculation is executed like below:

Cross sections are linked with cubic spline lines. The cubic spline lines links
the corresponding points of each cross section, like left bank, right bank,
river center line, etc.

Value at grid nodes are calculated from the values defined at
cross sections on the spline line, that passes the grid nodes.
The value is a weighted average value calculated from the values at 
upstream side cross section and downstream side cross section.

**[Cell attribute]**

[River Survey Data] does not support mapping to [Cell attribute].

[Pointset Data]
~~~~~~~~~~~~~~~~~~~

**[Node attribute]**

[Pointset Data] is mapped using TIN, as default. When a triangle that
contains the grid node is found, the weighted averaged value that
is calculated from the values at triangle nodes are mapped.

**[Cell attribute]**

[Pointset Data] is mapped using TIN. When a triangle that contains the 
cell center is found, the weighted averaged value that is calculated
from the values at triangle nodes are mapped.

[Polygon]
~~~~~~~~~~~

**[Node attribute]**

When the node is included in the polygon, the value of polygon is mapped.

**[Cell attribute]**

When the cell center is included in the polygon, the value of polygon is mapped.

.. note:: Specification changelog

   Until iRIC 3.0.3, [Polygon] value was mapped to grid cells when all the 
   nodes of the grid cell are inside the polygon.

[Raster Data]
~~~~~~~~~~~~~~~

**[Node attribute]**

Find the pixel (quadrangle) that contains the grid node, and map the 
value defined at the pixel.

**[Cell attribute]**

Find the pixel (quadrangle) that contains the grid cell center, and map the 
value defined at the pixel.
