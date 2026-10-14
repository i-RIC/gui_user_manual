.. _sec_file_export_calc_result:

[Calculation Result] (R)
==========================

**Description**: Exports the calculation result.

Calculation result can be exported to the file formats below:

* VTK files (ASCII) (\*.vtk)
* VTK files (Binary) (\*.vtk)
* CSV files (\*.csv)
* Topography Files (\*.tpo)
* ESRI Shape files (\*.shp)

When you select [Calculation Result], the [Export Calcutation Result]
dialog (:numref:`image_export_calc_result_dialog`) will open.
Edit the setting and click on [OK] to start exporting.
File names of exported files will be "(Prefix) +
(Number) + (".vtk" or ".csv")".

When the data is exported to a CSV file, the name of each column that outputs a calculation result value
has a prefix that indicates the position where the value is defined.
For example, the value "Depth" defined at grid nodes is output to the column named "N_Depth".

.. list-table:: Prefixes of the column names in the CSV file
   :header-rows: 1

   * - Prefix
     - Position where the value is defined
   * - N\_
     - Grid node
   * - C\_
     - Cell center
   * - I\_
     - I-direction edge
   * - J\_
     - J-direction edge
   * - K\_
     - K-direction edge

When you want to export partial data, remove the check on [All
timesteps] and specify the range of timesteps by editing [Start] and
[End], and [Skip rate].

When you want to export partial region of the data, click [Show Detail],
remove the check on [Full region], and specify the range to export
(:numref:`image_export_calc_result_dialog_detail`).

.. _image_export_calc_result_dialog:

.. figure:: images/export_calc_result_dialog.png
   :width: 200pt

   The [Export Calculation Result] dialog

.. _image_export_calc_result_dialog_detail:

.. figure:: images/export_calc_result_dialog_detail.png
   :width: 200pt

   The [Export Calculation Result] dialog after clicking [Show Detail]
