Georeferenced file (\*.jgw, etc.)
==================================

A georeferenced file (world file) gives coordinate data to an
image to overlap an image with a grid. The following is an
example of a georeferenced file.
Words in parentheses ( ) are remarks and are not included in the
actual file.

.. code-block:: text
   :name: georef_example
   :caption: Example of georeferenced file

   2.5 (a: increment of x-coordinate per pixel)
   0.0 (b: rotation condition)
   0.0 (c: rotation condition)
   -2.5 (d: increment of y-coordinate per pixel)
   -131.82 (e: x-coordinate of the pixel at top left of the image)
   223.57 (f: y-coordinate of the pixel at top left of the image)

"a" expresses an increment of x-coordinate per 1 pixel movement from
left to right.
"d" expresses an increment of y-coordinate per 1 pixel movement from
top to bottom.

Coordinates (e, f) express the coordinates of the pixel of top left
image.

"b" and "c" express rotation. However, iRIC does not read "b" and "c"
because it does not accommodate "rotation."

:numref:`table_georef_relationship` shows the relationship between
an image file and the extension of georeferenced file.

.. _table_georef_relationship:

.. list-table:: Relationship between an image file and the extension of georeferenced file
   :header-rows: 1

   * - Image file
     - Georeferenced file
   * - \*.jpg, \*.jpeg
     - \*.jgw
   * - \*.png
     - \*.pgw
   * - \*.bmp
     - \*.bpw
   * - \*.tif
     - \*.tfw

When a georeferenced file of the same file name as an image file is
located in the same directory, the georeferenced file is read for
adjusting the alignment of the image data.
