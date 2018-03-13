.. _sec_measured_data_text:

Measured data text file (\*.csv)
=================================

Measured data text file contains the positions of measured data and the
measured values (scalar values and vector values). :numref:`measured_example`
shows an example of measured data text file.

.. code-block:: text
   :name: measured_example
   :caption: Example of measured data text file

   X,Y,Elevation,VecX,VecY
   100,120,5.12,3,4
   100,140,7.2,1,-3.2
   0,120,8.12,-2,1
   0,140,9.2,4,-6.2

Measured data text file must have a header line. The header line defines
the data contained in each column. The header line has to stick to the
following rules:

-  First column must be "X" (the x-coordinate of the measured
   point), and the second column must be "Y" (the y-coordinate of
   the measured point). The following column names are arbitrary.

-  Columns names must consist of only alphabets and numbers.

-  When there are column names that end with "X" and "Y" (for example,
   "VecX", "VecY"), those columns are regarded as X component and Y
   component of a vector value.

On the second line and the following lines, the coordinates of
measured points and measured data are stored. The values have to be real
numbers.
