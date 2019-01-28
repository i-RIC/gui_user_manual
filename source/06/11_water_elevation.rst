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

   Point,Normal,H27,H29
   27.00,2,7,10.5
   27.50,2.2,7.2,10.7
   28.00,2.3,7.3,10.8
   28.50,2.4,7.4,10.9
   29.00,2.45,7.45,10.95
   29.50,2.48,7.48,10.98
   30.00,2.5,7.5,11

Water Elevation data file is a Comma-delimited text file. Each column
has the following meaning:

-  1st column: The name of cross-section
-  2nd column and the followings: Water elevation

The first line is recognized as a header line.

.. note:: Importing multiple water elevation data

   iRIC 3.0 and later versions can import multiple water elevation data
   from one file.

   iRIC 2.x just skipped the header line, but iRIC 3.0 and later load
   the names of water elevation data from the 2nd column and the followings,
   from the header line.
   For example, in case of :numref:`water_elevation_example`,
   "Normal", "H27", "H29" are loaded as names.
