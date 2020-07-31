.. _sec_raster_data:

Editing the [Raster Data]
=============================

**Description**: Sets the values of geographic data defined
in each cell of raster data.

It is unique in raster data that it can handle data with dimensions like
time or depth. For example when a dimension "Time" is adopted, you can
handle rainfall data as a function of position and time.

:numref:`image_example_raster_data` shows an example of 
the [Raster Data].

.. _image_example_raster_data:

.. figure:: images/example_raster_data.png
   :width: 340pt

   Example of the [Raster Data]

Currently, Function to edit [Raster Data] is not implemented yet.

.. note:: Importing multiple raster data with time dimension

   When you import multiple raster data with time dimension, for example rainfall data,
   the list of time value have to coincide between those data.

   It is not possible to import data for different time range, or with different time
   interval, an error message is shown.
