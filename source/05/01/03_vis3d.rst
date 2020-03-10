.. _sec_3d_vis_func:

3D visualization functions
===========================

Below are the functions for visualizing the 3D calculation results.

Use [3D Post-processing Window] for 3D visualization of simulation
results as explained below.

[Open New 3D Post-processing Window]
--------------------------------------

.. |post3d-window-icon| image:: images/post3d-window-icon.png

Either of the following actions opens a new [3D Post-processing Window].

**Menu bar:** [Calculation Results] (R) --> [Open New 3D Post-processing Window]

**Operation Toolbar:** Select |post3d-window-icon|

The new [3D Post-processing Window] (:numref:`image_post3d_window_example`) will open.

.. _image_post3d_window_example:

.. figure:: images/post3d_window_example.png
   :width: 320pt

   [3D Post-processing Window]

Menu items
------------

:numref:`table_post3d_window_menu` shows the additional menu items for
the [3D Post-processing Window]. The additional menu items are shown
between [Import] and [Simulation] on the Menu bar when the [3D
Post-processing Window] is active.

.. _table_post3d_window_menu:

.. list-table:: Additional menu items for [3D Post-processing Window]
   :header-rows: 1

   * - Menu
     -
     - Description
   * - [Display Setting] (D)
     - [Grid Shape] (G)
     - Sets the [Grid Shape] dialog.
   * -
     - [Contour] (C)
     - Sets the [Contour] dialog.
   * -
     - [Iso Surface] (I)
     - Sets the [Isosurface] dialog.
   * -
     - [Arrow] (A)
     - Sets the [Arrow] (i.e., vector) dialog.
   * -
     - [Streamline] (S)
     - Sets the [Streamline] dialog.
   * -
     - [Particles] (P)
     - Sets the [Particles] dialog.
   * -
     - [Title] (T)
     - Sets the [Title] dialog.
   * -
     - [Time] (M)
     - Sets the [Time] dialog.

[Object Browser]
-------------------

:numref:`image_post3d_window_objbrowser_example` shows an example
of the [Object Browser] of [3D Post-processing Window].

.. _image_post3d_window_objbrowser_example:

.. figure:: images/post3d_window_objbrowser_example.png
   :width: 280pt

   The [Object Browser] of the [3D Post-processing Window]

Settings on the elements shown in the [Object Browser] of [3D
Post-processing Window] can be edited mainly from [Draw] menu. For
operations on [Axes], refer to :ref:`sec_pre_axes`.

[Grid Shape] (G)
------------------

**Description**: Sets the grid shape settings.

When you select [Grid Shape], the [Grid Shape Setting] dialog
(:numref:`image_post3d_grid_shape_dialog`) will open.
Set it and click on [OK].
:numref:`image_post3d_grid_shape_wireframe_lines` shows examples
of the display when the setting is for [Wireframe] and [Grid line],
respectively.

.. _image_post3d_grid_shape_dialog:

.. figure:: images/post3d_grid_shape_dialog.png
   :width: 100pt

   [Grid Shape] dialog

.. _image_post3d_grid_shape_wireframe_lines:

.. figure:: images/post3d_grid_shape_wireframe_lines.png
   :width: 400pt

   Examples of graphics displayed by the [Grid Shape] setting

[Contour] (C)
---------------

**Description**: Sets the contour settings.

When you select [Contour], the [Contour Group Setting] dialog
(:numref:`image_post3d_contour_dialog`) will open.
Set it and click on [OK].
:numref:`image_post3d_contours_by_displaysetting`
shows examples of the contour display for the
[Counter] setting.

Please refer to :ref:`sec_geo_common_color_setting`
about the dialog that is shown when you select
[Custom] as [Colormap] and click on [Setting…] button.

.. _image_post3d_contour_dialog:

.. figure:: images/post3d_contour_dialog.png
   :width: 340pt

   [Contour Group Setting] dialog

.. _image_post3d_contour_colorbar_setting_dialog:

.. figure:: images/post3d_contour_colorbar_setting_dialog.png
   :width: 160pt

   [Color Legend Setting] dialog

.. _image_post3d_contours_by_displaysetting:

.. figure:: images/post3d_contours_by_displaysetting.png
   :width: 440pt

   Examples of the contour display by the [Display Setting] setting

[Iso Surface]
--------------

**Description**: Sets the iso-surface settings.

When you select [Iso Surface], the [Iso Surface Setting] dialog
(:numref:`image_post3d_isosurface_setting_dialog`)
will open. Set it and click on [OK].
:numref:`image_post3d_isosurface_example` shows examples of
the iso surface display.

.. _image_post3d_isosurface_setting_dialog:

.. figure:: images/post3d_isosurface_setting_dialog.png
   :width: 180pt

   [Iso Surface Setting] dialog

.. _image_post3d_isosurface_example:

.. figure:: images/post3d_isosurface_example.png
   :width: 300pt

   The Isosurface example

[Arrow] (A)
------------

**Description**: Sets the arrow (or vector) group settings.

When you select [Arrow], the [Arrow Group Setting] dialog
(:numref:`image_post3d_arrow_setting_dialog`)
will open. Set it and click on [OK].
:numref:`image_post3d_arrow_example` shows an example
of the [Arrow] display.

.. _image_post3d_arrow_setting_dialog:

.. figure:: images/post3d_arrow_setting_dialog.png
   :width: 300pt

   [Arrow Group Setting] dialog

.. _image_post3d_arrow_example:

.. figure:: images/post3d_arrow_example.png
   :width: 260pt

   Example of the [Arrow] display

[Streamline] (S)
-----------------

**Description**: Sets the streamline settings.

When you select [Streamline], the [Streamline Setting] dialog
(:numref:`image_post3d_streamline_setting_dialog`)
will open. Set it and click on [OK].
:numref:`image_post3d_streamline_example` shows an example
of the streamline display.

.. _image_post3d_streamline_setting_dialog:

.. figure:: images/post3d_streamline_setting_dialog.png
   :width: 200pt

   [Streamline Setting] dialog

.. _image_post3d_streamline_example:

.. figure:: images/post3d_streamline_example.png
   :width: 200pt

   Example of the [Streamline] display

[Particles (auto)] (P)
--------------------------

**Description**: Sets the particle settings.

[Particles (auto)] is the function to generate particles
in GUI, and simulate where where the particles will move to, 
using velocity in calculation result, and visualize the particles.

When you select [Particles], the [Particle Setting] dialog
(:numref:`image_post3d_particle_dialog`)
will open. Set it and click on [OK].
:numref:`image_post3d_particles_example` shows an example
of the [Particles] display.

.. _image_post3d_particle_dialog:

.. figure:: images/post3d_particle_dialog.png
   :width: 180pt

   [Particle Setting] dialog

.. _image_post3d_particles_example:

.. figure:: images/post3d_particles_example.png
   :width: 180pt

   Example of the [Particles] display

[Particles] (R)
------------------

**Description**: Sets the particle settings.

[Particles] is the function to load particles output by solber,
and visualize the particles.

When scalar attributes are output, user can change particle colors.
When vector attributes are output, user can show arrows.

When you select [Property] menu in right-clicking menu of
[Scalar] and [Vector] Folder under [Particles], the dialogs in 
:numref:`image_post3d_particles_solver_scalar_dialog`, 
:numref:`image_post3d_particles_solver_vector_dialog` will be shown.
Please edit the setting, and click on [OK] button.

:numref:`image_post3d_particles_solver_example`
shows an example of the [Particles] display.

.. _image_post3d_particles_solver_scalar_dialog:

.. figure:: images/post3d_particles_solver_scalar_dialog.png
   :width: 280pt

   [Particle Scalar Setting] dialog

.. _image_post3d_particles_solver_vector_dialog:

.. figure:: images/post3d_particles_solver_vector_dialog.png
   :width: 200pt

   [Arrow Setting] dialog

.. _image_post3d_particles_solver_example:

.. figure:: images/post3d_particles_example.png
   :width: 230pt

   Example of the [Particles] display

[Title] (T)
------------

**Description**: Sets the title settings.

When you select [Title], the [Title Setting] dialog
(:numref:`image_post3d_title_setting_dialog`) will open.
Set it and click on [OK].

.. _image_post3d_title_setting_dialog:

.. figure:: images/post3d_title_setting_dialog.png
   :width: 200pt

   [Title Setting] dialog

[Time] (M)
------------

**Description**: Sets the time settings.

When you select [Time], the [Time Setting] dialog
(:numref:`image_post3d_time_setting_dialog`)
will open. Set it and click on [OK].

.. _image_post3d_time_setting_dialog:

.. figure:: images/post3d_time_setting_dialog.png
   :width: 100pt

   [Time Setting] dialog
