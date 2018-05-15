River Survey File (\*.riv)
===========================

Overview
---------

The River Survey File (\*.riv) contains transverse data
(x and y coordinates of left/right banks) and cross-section data
(distance from left bank and riverbed elevation).

River Survey Files should be ASCII files. :numref:`image_riv_structure`
and Figure 6‑1 show
the structure and concept, respectively.

* Break points of input data (for example, cross-section identification
  number and x-coordinate value) are identified by "space", "tab" or
  "enter" characters. When break points are properly identified,
  iRIC automatically recognizes the data. Please note that
  cross-section identification number must be a real number.

* Rows after the "#survey" row are recognized as cross-section data.

  * Each row contains data for one cross-section.
  * Data row: (Cross-section identification number)
    (x-coordinate value of the left bank) (y-coordinate value of the left bank)
    (x-coordinate value of the right bank) (y-coordinate value of the right bank)

* Rows after the "#x-section" row are recognized as cross-section data
  (consisting of the "header line" and "data lines").

  * Header line: (Cross-section identification number) (No. of coordinates)
    (Index 1) (Index 2) (Index 3) (Index 4)

  Indexes 1 to 4 specify points on a cross-sectional coordinate system
  by sequential integer numbers. (The top is 1.) Data prior to Index 1
  and after Index 4 are discarded. The point specified by Index 1
  is set as the left bank and the point specified by Index 4
  is set as the right bank. The points specified by Indexes 2 and 3 are
  to be the division points (or nodes) of the automatically created grid.
  The Center Point of the river is set at the point midway between
  Indexes 2 and 3.

  You can omit Index data. In such case, all the coordinate cross-section
  data are read and the first point of the coordinate cross-section data
  is set as the left bank and the last point is set as the right bank. The
  Center Point of the river is set at the mid-point between the left and
  right banks.

  When Index data are not set for every cross-section data, the index data
  of all cross-sections are ignored.

  * Data line: (Distance from left bank) (Riverbed elevation) Continue
    to create rows of data until there are as many rows as there
    are cross-sections.

  Each row describes up to five sets of combinations of (Distance from
  left bank) and (Riverbed elevation) data.

.. _image_riv_structure:

.. figure:: images/riv_structure.png
   :width: 400pt

   Structure of River Survey File

.. _image_riv_concept:

.. figure:: images/riv_concept.png
   :width: 420pt

   Concept of River Survey File data

:numref:`image_riv_concept` shows the concept of
the River Survey File data. iRIC does
not display the four dots (data of Indexes 1 to 4).

The coordinates in the cross-sectional direction displayed in the
[Cross-section] window have been converted as follows; note that they
are different from [Distance from left bank] in the cross-section data
of the River Survey File.

* The coordinates of the Center Point of the river have been calculated
  from the longitudinal data and the cross-section data.

* The distance from the Center Point along the cross-sectional line has
  been calculated.

Scheduled driver longitudinal/cross-section data creation guideline and cross-sectional River Survey Data
------------------------------------------------------------------------------------------------------------

The Ministry of Land, Infrastructure, Transport and Tourism () publishes
guidelines for creating the scheduled river longitudinal/cross-section
data

`*http://www.mlit.go.jp/river/shishin\_guideline/kasen/gis/pdf\_docs/juoudan/guideline0805.pdf* <http://www.mlit.go.jp/river/shishin_guideline/kasen/gis/pdf_docs/juoudan/guideline0805.pdf>`__

:numref:`table_riv_survey_data_guideline` shows how to
convert the Guideline data items to the River
Survey Data items.

.. _table_riv_survey_data_guideline:

.. list-table:: Relationship between the River Survey Data items and the Guideline data
   :header-rows: 1

   * - River Survey Data item
     - How to convert the guideline data (surveyed cross-sectional numerical data) to River Survey Data items

   * - Coordinates of left/right banks
     - Specify the coordinates of the left/right bank distance posts.

   * - Cross-section data
     - | Specify the distance of the cross-sectional coordinate data for the distance from the left bank.
       | Specify the elevation of the cross-sectional coordinate data.

   * - Index data
     - | Set as follows:
       | Index 1: Number that corresponds to the left bank distance post
       | Index 2: Number that corresponds to the left bank shoreline post
       | Index 3: Number that corresponds to the right bank shoreline post
       | Index 4: Number that corresponds to the right bank distance post
