Grayscale 16bit PNG file (\*.png)
====================================

iRIC can import raster elevation data from grayscale 16bit PNG files.

It is expected that user use this function to import elevation data prepared for
game engine Unreal Engine 4.

When you import grayscale 16bit PNG file, please prepare the files in 
:numref:`16bit_png_file_table`.

.. _16bit_png_file_table:

.. list-table:: The list of file to import grayscale PNG file
   :header-rows: 1

   * - File
     - Description

   * - \*.png
     - The data that stores raster elevation data

   * - \*.pgw
     - The world file that stores the horizontal position of raster data

   * - \*.png.meta
     - The meta data file that stores the vertical offset and scale

\*.png
----------

Grayscale 16bit PNG file that stores raster elevation data.
Refer to the follwing URL about the detail of PNG file format.

http://www.libpng.org/


\*.pgw
----------

The world file that stores the horizontal position of raster data.
Refet to :ref:`sec_file_georef` about the detail of world file.

\*.png.meta
---------------

The metadata file that contains vertical offset and scale about values stored in \*.png.

In grayscale 16bit PNG files, Each pixel stores value between 0 and 65535. 0 corresponds to black,
65535 corresponds to white.

iRIC reads offset (:math:`o`) and scale (:math:`s`) from \*.png.meta file, and calculate the 
elevation value :math:`h` from color value :math:`c` with the following equation.

.. math::

   h = c \times s + o

\*.png.meta is a YAML format text file. Offset and scale values should be specified with
name "base" and "resolution", respectively.

:numref:`16bitpng_meta__example` shows an example of \*.png.meta.

.. code-block:: text
   :name: 16bitpng_meta__example
   :caption: Example of \*.png.meta

   base: 312.5
   resolution: 0.1
