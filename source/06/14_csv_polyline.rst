Lines CSV file (\*.csv)
==========================

Lines CSV file (\*.csv\) is a text file to import or export [Lines].

:numref:`polyline_csv_cols_table` shows the list of columns in CSV file,
and :numref:`polyline_csv_example` shows an example, respectively.

The encoding of Lines CSV file is UTF-8.

.. _polyline_csv_cols_table:

.. list-table:: The list of columns in Lines CSV file
   :header-rows: 1

   * - Column number
     - Name
     - Description
   * - 1
     - lid
     - Line ID. The value should be the same for the vertices in the same line.

   * - 2
     - vid
     - Vertex ID. For vertices in the same line, the values should be 1, 2, ...

   * - 3
     - x
     - X coordinate

   * - 4
     - y
     - Y coordinate

   * - 5
     - name
     - Name of line

   * - 6
     - value
     - Value of line

.. code-block:: text
   :name: polyline_csv_example
   :caption: Example of Lines CSV file

   lid,vid,x,y,name,value
   1,1,-1.93,0.117,Line4,4
   1,2,-2.191,1.632,Line4,4
   1,3,-2.096,3.005,Line4,4
   1,4,-0.77,4.047,Line4,4
   1,5,0.722,4.355,Line4,4
   1,6,2.758,4.094,Line4,4
   2,1,2.498,-1.422,Line3,3
   2,2,3.469,-2.89,Line3,3
   2,3,4.321,-4.69,Line3,3
   2,4,2.285,-5.305,Line3,3
   2,5,0.248,-4.642,Line3,3
   2,6,-0.675,-3.766,Line3,3
   2,7,-1.031,-2.985,Line3,3
   3,1,-0.746,2.224,Line2,2
   3,2,2.048,2.911,Line2,2
   3,3,3.232,1.774,Line2,2
   3,4,4.416,-0.594,Line2,2
   3,5,4.534,-2.346,Line2,2
   3,6,4.392,-2.866,Line2,2
   4,1,-0.949,1.167,Line1,1
   4,2,-0.869,-0.571,Line1,1
   4,3,-0.174,-1.867,Line1,1
   4,4,1.266,-3.482,Line1,1
   4,5,2.569,-3.814,Line1,1
   4,6,2.829,-3.979,Line1,1
