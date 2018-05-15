[Property] (P)
===============

**Description**: Shows the property dialog of the current project.
:numref:`image_project_property_dialog` shows an example of
the [Project Property] dialog.

You can specify the coordinate system and offset from this dialog.

When you click on [Edit] button next to [Coordinate System], the
dialog in :numref:`image_select_coordsystem_dialog` appears,
and you can choose the coordinate system
for your geographic data and grid.

When you click on [Edit] button next to [Coordinate Offset], the
dialog in :numref:`image_offset_setting_dialog` appears, and you can
input the offset for the coordinates.

When you want to use geographic data and grids very far from the origin
point of the coordinate system (for example, using UTM coordinate System
and handles geographic data far from equator), inputting offset will
reduce the truncation error. In such cases, please input the x and y
for some point near to your geographic data (or grid).

.. _image_project_property_dialog:

.. figure:: images/project_property_dialog.png
   :width: 280pt

   The [Project Property] dialog

.. _image_select_coordsystem_dialog:

.. figure:: images/select_coordsystem_dialog.png
   :width: 320pt

   The [Select Coordinate System] dialog

.. _image_offset_setting_dialog:

.. figure:: images/offset_setting_dialog.png
   :width: 220pt

   The [Offset Setting] dialog
