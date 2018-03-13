.. _sec_water_elevation_data:

Water Elevation data file (\*.csv)
====================================

Water Elevation data file contains the water surface elevation of river
cross-sections in river survey data.
:numref:`water_elevation_example` shows an example of
water elevation data file.

.. code-block:: text
   :name: water_elevation_example
   :caption: Example of Water elevation data file

   KP,WaterElevation
   27.00,5
   27.50,6.2
   28.00,9.3
   28.50,10.0

Water Elevation data file is a Comma-delimited text file. Each column
has the following meaning:

-  The name of cross-section
-  Water elevation

The first line is recognized as a header line, and skipped.
