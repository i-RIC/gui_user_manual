.. _sec_2d_vis_func:

2D visualization functions
============================

The functions for visualizing the 2D calculation results are explained.

Use [2D Post-processing Window] for 2D visualization of simulation
results as explained below.

[Open New 2D Post-processing Window]
-------------------------------------

.. |post2d-window-icon| image:: images/post2d-window-icon.png

Either of the following actions opens a new [2D Post-processing Window].

**Menu bar:** [Calculation Results] (R) --> [Open New 2D Post-processing Window]

**Operation Toolbar:** |post2d-window-icon|

The new [2D Post-processing Window] (:numref:`image_post2d_window_example`)
will open.

.. _image_post2d_window_example:

.. figure:: images/post2d_window_example.png

   [2D Post-processing Window]

Additional menu items
----------------------

:numref:`table_post2d_window_menu` shows the additional menu items for
the [2D Post-processing Window] display.
The additional menus are shown between [Import] and
[Simulation] when [2D Post-processing Window] is active.

.. _table_post2d_window_menu:

.. list-table:: Additional menu items for [2D Post-processing Window]
   :header-rows: 1

   * - Menu
     -
     - Description
   * - [Display Setting] (D)
     - [Grid Shape] (G)
     - Displays the [Grid Shape] dialog.
   * -
     - [Contour] (C)
     - Displays the [Contour] dialog.
   * -
     - [Arrow] (A)
     - Displays the [Arrow] (i.e., vector) dialog.
   * -
     - [Streamline] (S)
     - Displays the [Streamline] dialog.
   * -
     - [Particles] (P)
     - Displays the [Particles] dialog.
   * -
     - [Cell Attributes]
     - Displays the [Cell Attributes] dialog.
   * -
     - [Title]
     - Displays the [Title] dialog.
   * -
     - [Time]
     - Displays the [Time] dialog.
   * - [Measured Data] (M)
     - [Scalar] (S)
     - Displays the [Scalar Setting] dialog.
   * -
     - [Arrows] (A)
     - Displays the [Arrows Setting] dialog.
   * -
     - [Import] (I)
     - Import [Measured Data]

[Object Browser]
------------------

:numref:`image_post2d_window_objbrowser_example` shows an example
of the [Object Browser] of [2D
Post-processing Window].

.. _image_post2d_window_objbrowser_example:

.. figure:: images/post2d_window_objbrowser_example.png

   The [Object Browser] of the [2D Post-processing Window]

Settings on the elements shown in the [Object Browser] of [2D
Post-processing Window] can be edited mainly from [Draw] menu and
[Measured Data] menu. For operations on [Axes] and [Distance Measures],
refer to :ref:`sec_pre_axes` and :ref:`sec_pre_distance_measures`
respectively.

[Grid Shape] (G)
------------------

**Description**: Sets the grid shape settings.

When you select [Grid Shape], the [Grid Shape Setting] dialog
(:numref:`image_post2d_grid_shape_dialog`) will open.
Set it and click on [OK].
:numref:`image_post2d_grid_shape_wireframe_lines` shows examples of
the display when the setting is for [Wireframe] and [Grid line],
respectively.

.. _image_post2d_grid_shape_dialog:

.. figure:: images/post2d_grid_shape_dialog.png

   [Grid Shape] dialog

.. _image_post2d_grid_shape_wireframe_lines:

.. figure:: images/post2d_grid_shape_wireframe_lines.png

   Examples of graphics displayed by the [Grid Shape] setting

[Contour] (C)
---------------

**Description**: Sets the contour settings

When you select [Contour], the [Contour Setting] dialog
(:numref:`image_post2d_contour_dialog`) will open.
Set it and click on [OK].

When you click on [Region Setting] button, [Region Setting]
dialog (:numref:`image_post2d_contour_region_structured_dialog` or
:numref:`image_post2d_contour_region_unstructured_dialog`) will open.

When you click on [Color Bar Setting] button, [Color Legend Setting]
dialog (:numref:`image_post2d_contour_colorbar_setting_dialog`) will open.

Please refer to :ref:`sec_geo_common_color_setting` about the dialog
that is shown when you select
[Custom] as [Colormap] and click on [Setting…] button.

.. _image_post2d_contour_dialog:

.. figure:: images/post2d_contour_dialog.png

   [Contour Setting] dialog

.. _image_post2d_contour_region_structured_dialog:

.. figure:: images/post2d_contour_region_structured_dialog.png

   [Region Setting] dialog (Structured grid)

.. _image_post2d_contour_region_unstructured_dialog:

.. figure:: images/post2d_contour_region_unstructured_dialog.png

   [Region Setting] dialog (Unstructured grid)

.. _image_post2d_contour_colorbar_setting_dialog:

.. figure:: images/post2d_contour_colorbar_setting_dialog.png

   [Color Legend Setting] dialog

.. _image_post2d_contours_by_displaysetting:

.. figure:: images/post2d_contours_by_displaysetting.png

   Examples of the contour display by the [Display Setting] setting

[Arrow] (A)
-------------

**Description**: Sets the [Arrow] display.

When you select [Arrow], the [Arrow Setting] dialog
(:numref:`image_post2d_arrow_setting_dialog_structured` or
:numref:`image_post2d_arrow_setting_dialog_unstructured`) will open.
Set it and click on [OK]. :numref:`image_post2d_arrow_example`
shows an example of the [Arrow] display.

.. _image_post2d_arrow_setting_dialog_structured:

.. figure:: images/post2d_arrow_setting_dialog_structured.png

   [Arrow Setting] dialog (structured)

.. _image_post2d_arrow_setting_dialog_unstructured:

.. figure:: images/post2d_arrow_setting_dialog_unstructured.png

   [Arrow Setting] dialog (unstructured)


.. _image_post2d_arrow_region_structured_dialog:

.. figure:: images/post2d_arrow_region_structured_dialog.png

   [Region Setting] dialog (Structured grid)

.. _image_post2d_arrow_region_unstructured_dialog:

.. figure:: images/post2d_arrow_region_unstructured_dialog.png

   [Region Setting] dialog (Unstructured grid)

.. _image_post2d_arrow_example:

.. figure:: images/post2d_arrow_example.png

   Example of the [Arrow] display

[Streamline] (S)
------------------

**Description**: Sets the streamline settings.

When you select [Streamline], the [Streamline Setting] dialog
(:numref:`image_post2d_streamline_structured_dialog` or
:numref:`image_post2d_streamline_unstructured_dialog`)
will open. Set it and click on [OK].
:numref:`image_post2d_streamline_example` shows an example
of the streamline display.

.. _image_post2d_streamline_structured_dialog:

.. figure:: images/post2d_streamline_structured_dialog.png

   [Streamline Setting] dialog (Structured)

.. _image_post2d_streamline_unstructured_dialog:

.. figure:: images/post2d_streamline_unstructured_dialog.png

   [Streamline Setting] dialog (Unstructured)

.. _image_post2d_streamline_example:

.. figure:: images/post2d_streamline_example.png

   Example of the [Streamline] display

[Particles] (P)
------------------

**Description**: Sets the particle settings.

When you select [Particles], the [Particle Setting] dialog
(:numref:`image_post2d_particles_structured_dialog` or
:numref:`image_post2d_particles_unstructured_dialog`)
will open. Set it and click on [OK].
:numref:`image_post2d_particles_example`
shows an example of the [Particles] display.

.. _image_post2d_particles_structured_dialog:

.. figure:: images/post2d_particles_structured_dialog.png

   [Particle Setting] dialog (Structured)

.. _image_post2d_particles_unstructured_dialog:

.. figure:: images/post2d_particles_unstructured_dialog.png

   [Particle Setting] dialog (Unstructured)

.. _image_post2d_particles_example:

.. figure:: images/post2d_particles_example.png

   Example of the [Particles] display

[Cell Attributes] (C)
-----------------------

**Description**: Sets the cell color and the order of display for
cell attributes.

When you select [Cell Attributes], the [Cell Attributes] dialog
(:numref:`image_post2d_cellattributes_dialog`) will open.
Set it and click on [OK].

.. _image_post2d_cellattributes_dialog:

.. figure:: images/post2d_cellattributes_dialog.png

   [Cell Attributes] dialog

[Title] (T)
------------

**Description**: Sets the title settings.

When you select [Title], the [Title Setting] dialog
(:numref:`image_post2d_title_setting_dialog`) will open.
Set it and click on [OK].

.. _image_post2d_title_setting_dialog:

.. figure:: images/post2d_title_setting_dialog.png

   [Title Setting] dialog

[Time] (M)
------------

**Description**: Sets the time settings.

When you select [Time], the [Time Setting] dialog
(:numref:`image_post2d_time_setting_dialog`)
will open. Set it and click on [OK].

.. _image_post2d_time_setting_dialog:

.. figure:: images/post2d_time_setting_dialog.png

   [Time Setting] dialog

[Measured Data] (M)
---------------------

The functions related to [Measured Data] that are available in [2D
Post-processing Window] are the same to those in [Pre-processing
Window]. Refer to :ref:`sec_pre_measured_data`.
