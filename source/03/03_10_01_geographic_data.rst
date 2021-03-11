.. _sec_file_export_geo_data:

地理情報 (E)
==============

地理情報をエクスポートします。

地理情報は、:numref:`export_geodata_formats_table` に示す
ファイルフォーマットにエクスポートできます。

.. _export_geodata_formats_table:

.. list-table:: 地理情報をエクスポート可能なファイルフォーマット
   :header-rows: 1

   * - 種類
     - フォーマット

   * - 点群データ
     - 地勢データ (\*.tpo)
   * -
     - LandXML ファイル (\*.xml)
   * -
     - STLファイル (\*.stl)
   * -
     - VTKファイル (\*.vtk)

   * - 横断測量データ
     - 横断測量データ (\*.riv)
   * - 
     - テキストファイル (\*.txt)
   * - 
     - CSVファイル (\*.csv)
   * -
     - LandXML ファイル (\*.xml)

   * - ラスターデータ
     - GeoTIFF ファイル (\*.tif)
   * - 
     - Arc/Info ASCII ファイル (\*.asc)
   * - 
     - 16bit グレースケール PNG ファイル (\*.png)
   * - 
     - NetCDF ファイル (\*.nc)

   * - 時系列ラスターデータ
     - NetCDFファイル (\*.nc)

   * - ポリゴンデータ
     - ESRI シェープファイル (\*.shp)
   * -
     - CSV ファイル (\*.csv)

   * - ラインデータ
     - ESRI シェープファイル (\*.shp)
   * -
     - CSV ファイル (\*.csv)

   * - 点データ
     - ESRI シェープファイル (\*.shp)
   * -
     - CSV ファイル (\*.csv)

「地理情報」を選択すると、エクスポート可能な地理情報のリストが
サブメニューとして表示されます。
ここでエクスポートしたい地理情報を選択すると、
:numref:`image_select_file_to_export_dialog_for_geo_data`
に示すダイアログが表示されます。
エクスポートするファイル名を指定すると、
指定したファイルに地理情報がエクスポートされます。

.. _image_select_file_to_export_dialog_for_geo_data:

.. figure:: images/select_file_to_export_dialog_for_geo_data.png
   :width: 380pt

   エクスポートするファイル名の選択ダイアログ
