.. _sec_grid_create_polyline_and_width:

[Create grid from Polygonal line and width]
===========================================

**Description**: Creates a grid that smoothly follows a Polygonal line.
:numref:`image_example_grid_polyline_and_width` shows an example of
a grid created by this algorithm.

.. _image_example_grid_polyline_and_width:

.. figure:: images/example_grid_polyline_and_width.png
   :width: 340pt

   Example of grid created from Polygonal lines and widths

After selecting this algorithm, click on the canvas to specify a few
points on the centerline of the grid. To finish, press the Enter key or
double click.
:numref:`image_polyline_display_after_centerline_set` shows an example of
the display when the grid centerline has been set.

After the centerline has been set, select [Create Grid] from [Grid] on
the menu. The [Grid Creation] dialog
(:numref:`image_example_grid_creation_dialog`)
will open. Click on [Apply] to see the resulting grid, adjust the
input data and click on [OK].

.. _image_polyline_display_after_centerline_set:

.. figure:: images/polyline_display_after_centerline_set.png
   :width: 380pt

   Example of display after the grid centerline has been set

.. _image_example_grid_creation_dialog:

.. figure:: images/example_grid_creation_dialog.png
   :width: 240pt

   Example of the [Grid Creation] dialog

To edit the vertexes of the centerline, select from the menu shown in
:numref:`menu_polygonal_line_and_width_table`.

Menu items
----------

:numref:`menu_polygonal_line_and_width_table` shows the menu
configurations of the submenu of [Grid] (G) -->
[Grid Creating Conditions] (C) when [Create grid from Polygonal lines
and widths] is selected as the grid creating algorithm.

.. _menu_polygonal_line_and_width_table:

.. list-table:: Menu items for the algorithm [Create grid from Polygonal lines and widths]
   :header-rows: 1

   * - Menu
     - Description
   * - [Add Vertex] (A)
     - Adds a vertex on the centerline.
   * - [Remove Vertex] (R)
     - Removes a vertex from the centerline.
   * - [Edit Vertices Coordinates] (O)
     - Edits the coordinates of a vertex.
   * - [Line Direction] (C)
     - Reverses the direction of center line.
   * - [Remove Centerline] (C)
     - Removes the centerline.

[Add Vertex] (A)
----------------

**Description**: Adds vertices to the centerline.

While selecting it, move the mouse onto the centerline. The mouse cursor
changes shape as shown in :numref:`image_poly_cursor_add_vertex`.
Left clicking adds a new vertex.

.. _image_poly_cursor_add_vertex:

.. figure:: images/poly_cursor_add_vertex.png
   :width: 20pt

   Mouse cursor display when adding a vertex is possible

[Remove Vertex] (R)
-------------------

**Description**: Removes a vertex from the centerline.

While selecting it, move the mouse onto the centerline. The mouse cursor
changes shape as shown in :numref:`image_poly_cursor_remove_vertex`.
Left clicking removes the selected vertex.

.. _image_poly_cursor_remove_vertex:

.. figure:: images/poly_cursor_remove_vertex.png
   :width: 20pt

   Mouse cursor shape when removing the vertex is possible

[Edit Vertices Coordinates] (O)
-------------------------------

**Description**: Edits the coordinates of the vertex of centerline.

When you select this, the [Polyline Coordinates] dialog
(:numref:`image_poly_centerline_coordinates_dialog`)
will open. Edit the coordinates and click on [OK].

.. _image_poly_centerline_coordinates_dialog:

.. figure:: images/poly_centerline_coordinates_dialog.png
   :width: 180pt

   [Centerline Coordinates] dialog

[Line Direction] (E)
---------------------

**Description**: Reverce the center line direction.
:numref:`image_poly_example_reversing` shows an
example. Note that the "Upstream" and "Downstream" are reversed.

.. _image_poly_example_reversing:

.. figure:: images/poly_example_reversing.png
   :width: 420pt

   Example of Center line before and after reversing

[Remove Centerline] (C)
------------------------

**Description**: Removes the centerline and restores the condition
immediately after the algorithm was selected.

After removing the centerline, click on the canvas to define the
centerline in the same way as the first centerline was defined after
selecting the algorithm.
