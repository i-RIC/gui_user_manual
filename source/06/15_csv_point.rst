.. _sec_file_point_csv:

Points CSV file (\*.csv)
========================================

Lines CSV file (\*.csv\) is a text file to import or export [Points].

:numref:`point_csv_cols_table` shows the list of columns in CSV file,
and :numref:`point_csv_example` shows an example, respectively.

The encoding of Points CSV file is UTF-8.

.. _point_csv_cols_table:

.. list-table:: The list of columns in Points CSV file
   :header-rows: 1

   * - Column number
     - Name
     - Description

   * - 1
     - x
     - X coordinate

   * - 2
     - y
     - Y coordinate

   * - 3
     - name
     - Name of point

.. code-block:: text
   :name: point_csv_example
   :caption: Example of Points CSV file

   x,y,name
   5.086,-5.509,Point10
   3.443,-5.447,Point9
   1.946,-4.610,Point8
   1.007,-3.722,Point7
   -0.084,-2.454,Point6
   1.210,-1.388,Point5
   -0.871,-1.312,Point4
   1.616,-0.247,Point3
   -0.998,2.493,Point2
   -3.104,0.083,Point1
