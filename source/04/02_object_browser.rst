
[Object Browser]
================

:numref:`image_ob_of_pre_window` shows an example of the [Object Browser]
of [Pre-processing Window].

.. _image_ob_of_pre_window:

.. figure:: images/ob_of_pre_window.png
   :width: 300pt

   The [Object Browser] of the [Pre-processing Window]

Operations related to elements shown in object browser are explained in
the following sections.

[Geographic Data]
-----------------

[Geographic Data] is used when importing or editing geographic data that
is used for grid attribute interpolation. Refer to :ref:`sec_pre_geodata`
for operations on [Geographic Data].

[Grid Creating Condition]
-------------------------

[Grid Creating Condition] is used when selecting and edit setting on
grid creating condition. Refer to :ref:`sec_pre_grid_creating_func`
for operations on [Grid Creating Condition].

[Grid]
------

[Grid] is used when editing grid. Refer to :ref:`sec_pre_grid`
for operations on [Grid].

[Measured Values]
-----------------

[Measured Values] is used when importing measured values. Refer to
:ref:`sec_pre_measured_data` for operations on [Measured Values].

[Background Images]
-------------------

[Background Images] is used when importing background images. Refer to
:ref:`sec_pre_bg_image_data` for operations on [Background Images].

.. _sec_pre_ob_bg_internet:

[Background Images (Internet)]
---------------------------------

[Background Images (Internet)] is used to show images got from
internet and shows as background images.

When you check on the child item, like [Google Maps (Road)], the
map is shown as background images.

When you want to use this function, you have to specify the coordinate system
used in the project. Please refer to :ref:`sec_file_property` about the way
to specify the coordinate system.

You can add or remove the maps to show. When you want to use Google Maps
images as background images, you need to create an account on Google, and
input the API Key you've created. Please refer to 
:ref:`pref_bgimg_internet_tab` about the detail.

.. _sec_pre_axes:

[Axes]
------

Shows X-Y axes in the drawing region. :numref:`image_example_of_axes`
shows the example of axes.

When [Axes] is selected in the [Object browser], you can change the
position and size of the axes by mouse dragging operation in the drawing
region.

.. _image_example_of_axes:

.. figure:: images/example_of_axes.png
   :width: 60pt

   Example of axes

.. _sec_pre_distance_measures:

[Distance Measures]
-------------------

Shows lines that is used to measure the distance in the drawing region.

You can add measures, by selecting [Distance Measures] in the [Object
Browser], and selecting [Add Measure] in the right-clicking menu.

By selecting measure element (the child elements of [Distance
Measures]), and left-dragging operation in the drawing region, you can
draw a line that represents the distance between the drag start point
and the drag end point.
:numref:`example_of_distance_measure` shows the example of the distance
measure line.

.. _example_of_distance_measure:

.. figure:: images/example_of_distance_measure.png
   :width: 160pt

   Example of the distance measure line

Line color, start position, and end position etc. of the distance
measure line can be edited from the [Property] dialog.
:numref:`distance_measure_prop_dialog` shows
the example of [Distance Measure] property dialog.

.. _distance_measure_prop_dialog:

.. figure:: images/distance_measure_prop_dialog.png
   :width: 220pt

   [Distance Measure] property dialog
