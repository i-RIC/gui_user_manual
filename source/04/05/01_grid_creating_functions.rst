.. _sec_pre_grid_creating_func:

Grid creating functions
=========================

The grid creating functions is explained in this section. Refer to
:ref:`sec_abst_create_grid` for an overview of grid creation.

When the [Pre-processing Window] is active, grids can be created by
using the menu items in [Grid] menu. Grids can be created in the
following procedure:

1. Select an algorithm for creating a grid.
2. Set grid creating condition necessary for the algorithm using.
3. Create a grid.

Operations for 2. and 3. differ by algorithm.

:numref:`grid_creating_algorithms_table` shows the grid creating algorithms
that can be used for iRIC.

.. _grid_creating_algorithms_table:

.. list-table:: Grid creating algorithms available in iRIC
   :header-rows: 1

   * - Grid type
     - Item
     - Description
   * - Two-dimensioinal structured grid
     - [Create grid from polygonal lines and width]
     - Creates a grid that smoothly follows a polygonal line.
   * -
     - [Create grid from cross-section data]
     - Creates a grid from [Cross-Section Data]. In addition to transverse lines being set, division points are set on the transverse lines the river centerline and left / right bank lines.
   * -
     - [Create grid by dividing rectangular region]
     - Creates a rectangular grid that is evenly divided in the x and y directions.
   * -
     - [Create compound channel grid]
     - Creates a grid that has lower channel, by defining grid creating region and lower channel region.
   * -
     - [Create grid shape solving Poisson equation]
     - By solving Poisson equation, generate grid whose cell shape are similar to squares.
   * -
     - [General purpose grid generation tool]
     - By solving convergence calculation, generate grid whose cell edge length
       changes smoothly.
   * - Two-dimensional unstructured grid
     - [Create grid from polygon shape]
     - Creates an unstructured grid from polygon shape. Grid region, refinement regions, hole regions are defined as polygons.
   * - One-dimensional structured grid (Each node holds the cross-section data.)
     - [Create grid from River Survey Data]
     - Creates grid from River Survey Data. In addition to transverse lines being set, division points are set on the transverse lines, the river centerline and left/right bank lines.

The common operations available for all of these algorithms are
explained in :ref:`sec_grid_creation_common_funcs`.
Operations specific to the algorithms are
explained in :ref:`sec_grid_create_polyline_and_width`
to :ref:`sec_grid_creation_polygon`.

Operations available for each algorithm are accessible as sub menu item
of the following:

**Menu bar**: [Grid] (G) --> [Grid Creating Conditions] (C)

.. toctree::
   :maxdepth: 1

   01_01_common_functions
   01_02_polygonal_line_and_width
   01_03_riv_data_2d
   01_05_rectangular_region
   01_06_compound_channel
   01_07_poisson
   01_07_laplace
   01_07_riv_data_1d
   01_08_polygon
