.. _sec_pre_geodata:

[Geographic Data]
=================

The functions for editing [Geographic Data] are explained in the
following sections. Refer to :ref:`sec_abst_edit_geo_data`
for the abstract of [Geographic Data].

Operations related to [Geographic Data] are available from [Geographic
Data] menu when the [Pre-processing Window] is active.

[Geographic Data] types that users can import and edit depend depends
on the solver.

There is an exception: the [Reference Information] group.
For projects for every solver, this group is shown. This is a special
group that is not for mapping attributes to grid, but just for showing
data as reference information.

For example, add poly lines for road center lines, area border lines
as [Reference Information].

Curently, iRIC supports the following three types of [Geographic Data].

-  River Survey Data
-  Pointset Data
-  Polygon
-  Raster Data

The common operations available for all of these types are explained in
:ref:`sec_geo_common_functions`. Operations specific to the data types
are explained in :ref:`sec_riv_data` to :ref:`sec_polygon_data`.

For importing and exporting [Geographic Data], refer to
:ref:`sec_file_import_geo_data` and :ref:`sec_file_export_geo_data`.

.. toctree::
   :maxdepth: 3

   04/01_common_functions
   04/02_riv_data
   04/03_pointset_data
   04/04_polygon
   04/05_raster
