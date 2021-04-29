Polygons CSV file (\*.csv)
========================================

Polygons CSV file (\*.csv\) is a text file to import or export [Polygons].

:numref:`polygon_csv_cols_table` shows the list of columns in CSV file,
and :numref:`polygon_csv_example` shows an example, respectively.

The encoding of Polygons CSV file is UTF-8.

.. _polygon_csv_cols_table:

.. list-table:: The list of columns in Polygons CSV file
   :header-rows: 1

   * - Column number
     - Name
     - Description
   * - 1
     - pid
     - Polygon ID. The value should be the same for the vertices in the same polygon.

   * - 2
     - vid
     - Vertex ID. For vertices in the same polygon, the values should be 1, 2, ...
     
   * - 3
     - x
     - X coordinate

   * - 4
     - y
     - Y coordinate

   * - 5
     - name
     - Name of polygon

   * - 6
     - value
     - Value of polygon

.. code-block:: text
   :name: polygon_csv_example
   :caption: Example of Polygons CSV file

   pid,vid,x,y,name,value
   1,1,0.187,-1.072,Polygon3,3
   1,2,-0.234,-1.398,Polygon3,3
   1,3,-0.202,-2.113,Polygon3,3
   1,4,0.471,-2.218,Polygon3,3
   1,5,1.449,-2.123,Polygon3,3
   1,6,2.311,-1.587,Polygon3,3
   1,7,2.248,-1.366,Polygon3,3
   1,8,1.838,-1.261,Polygon3,3
   1,9,0.965,-1.461,Polygon3,3
   1,10,0.65,-1.156,Polygon3,3
   1,11,0.187,-1.072,Polygon3,3
   2,1,0.503,0.641,Polygon2,2
   2,2,0.334,-0.189,Polygon2,2
   2,3,1.228,-0.557,Polygon2,2
   2,4,2.448,-0.557,Polygon2,2
   2,5,2.669,0.011,Polygon2,2
   2,6,2.69,0.379,Polygon2,2
   2,7,2.017,0.179,Polygon2,2
   2,8,1.365,0.179,Polygon2,2
   2,9,0.986,0.242,Polygon2,2
   2,10,0.745,0.589,Polygon2,2
   2,11,0.503,0.641,Polygon2,2
   3,1,-0.765,0.707,Polygon1,1
   3,2,-0.765,-0.098,Polygon1,1
   3,3,-0.003,-0.591,Polygon1,1
   3,4,0.034,-0.317,Polygon1,1
   3,5,-0.168,0.14,Polygon1,1
   3,6,-0.326,0.799,Polygon1,1
   3,7,-0.424,1.042,Polygon1,1
   3,8,-0.765,0.707,Polygon1,1
