.. _sec_file_import_geo_data:

地理情報 (E)
======================

地理情報をインポートします。

地理情報は、:numref:`import_geodata_formats_table` に示す
ファイルフォーマットからインポートできます。

.. _import_geodata_formats_table:

.. list-table:: 地理情報をインポート可能なファイルフォーマット
   :header-rows: 1

   * - 種類
     - フォーマット
   * - 河川測量データ
     - 河川測量データ (\*.riv)
   * - 
     - 日本 国土交通省 河川測量データ (\*.csv)
   * - 地勢データ
     - 地勢データ (\*.tpo, \*.anc)
   * -
     - RIC-Nays DEMデータ (\*.dat, \*.txt)
   * -
     - USGS NED (\*.adf)
   * -
     - STLファイル (\*.stl)
   * -
     - LandXML ファイル (\*.xml)
   * - ポリゴン
     - ESRI Shapefile (\*.shp)
   * - 折れ線
     - ESRI Shapefile (\*.shp)
   * - ラスターデータ
     - GeoTIFF ファイル (\*.tif)
   * - 時系列ラスターデータ
     - NetCDFファイル (\*.nc)
   * -
     - XバンドMPレーダーデータ (\*.\*)

「地理情報」を選択すると、インポート可能な地理情報のリストが
サブメニューとして表示されます。ここでインポートしたい地理情報を選択すると、
:numref:`image_select_file_to_import_dialog`
に示すダイアログが表示されます。ファイルを選択すると、
選択したファイルから地理情報がインポートされます。

インポートされた地理情報は、オブジェクトブラウザーで確認できます。インポート後の
iRIC の表示例を :numref:`image_iric_after_importing_riv_data` に示します。

.. _image_select_file_to_import_dialog:

.. figure:: images/select_file_to_import_dialog.png
   :width: 400pt

   インポートするファイルの選択ダイアログ

.. _image_iric_after_importing_riv_data:

.. figure:: images/iric_after_importing_riv_data.png
   :width: 360pt

   河川測量データインポート後の iRIC 表示例

河川測量データからインポートする場合、ファイル選択後に
:numref:`image_rivdata_import_setting_dialog`
に示すダイアログが表示されます。
インポートの設定を行って「OK」ボタンを押します。

.. _image_rivdata_import_setting_dialog:

.. figure:: images/rivdata_import_setting_dialog.png
   :width: 180pt

   河川測量データインポート設定ダイアログ

ESRI シェープファイルからポリゴンをインポートする場合、ファイル選択後に
:numref:`image_polygon_import_setting_dialog`
に示すダイアログが表示されます。
インポートの設定を行って「OK」ボタンを押します。

.. _image_polygon_import_setting_dialog:

.. figure:: images/polygon_import_setting_dialog.png
   :width: 320pt

   ポリゴンインポート設定ダイアログ

NetCDF ファイルを、時間など位置以外の次元を持つ地理情報にインポートする
場合、ファイル選択後に
:numref:`image_netcdf_import_setting_dialog` に示すダイアログが表示されます。
次元のマッピングに関する設定を行い、「OK」ボタンを押します。

.. _image_netcdf_import_setting_dialog:

.. figure:: images/netcdf_import_setting_dialog.png
   :width: 160pt

   次元のマッピング設定ダイアログ

XRAINの雨量データを地理情報にインポートする場合、一つのフォルダ内に XRAIN の
雨量データファイルのみが含まれているように保存し、それらのファイルの1つを選択します。
すると、そのフォルダ内に保存された全ての雨量データファイルが読み込まれ、インポートされます。
