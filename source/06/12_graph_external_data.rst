.. _sec_graph_external_data:

Graph window external data file (\*.csv)
==========================================

Graph window external data file contains the data to be displayed on
graph windows. :numref:`graph_external_example` shows an example of
graph window external data file.

.. code-block:: text
   :name: graph_external_example
   :caption: Example of graph window external data file

   X,Elevation,Depth
   0,120,5.12
   30,140,7.2,1
   35,120,8.12
   42,140,9.2,4

Graph window external data file must have a header line. The header line
defines the data contained in each column. The header line has to stick
to the following rules:

- First column must be "X" (the x-axis values on the graph). The
  following column names are arbitrary.

- Columns names must consist of only alphabets and numbers.

On the second line and the following lines, the X values and Y
values are stored. The values have to be real numbers.
