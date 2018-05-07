.. _sec_file_import_geo_data:

地理情報 (E)
======================

地理情報をインポートします。

「地理情報」を選択すると、インポート可能な地理情報のリストが
サブメニューとして表示されます。ここでインポートしたい地理情報を選択すると、
:numref:`image_select_file_to_import_dialog`
に示すダイアログが表示されます。ファイルを選択すると、
選択したファイルから地理情報がインポートされます。

インポートされた地理情報は、オブジェクトブラウザーで確認できます。インポート後の
iRIC の表示例を :numref:`image_iric_after_importing_riv_data` に示します。

.. _image_select_file_to_import_dialog:

.. figure:: images/select_file_to_import_dialog.png

   インポートするファイルの選択ダイアログ

.. _image_iric_after_importing_riv_data:

.. figure:: images/iric_after_importing_riv_data.png

   河川測量データインポート後の iRIC 表示例

河川測量データからインポートする場合、ファイル選択後に
:numref:`image_rivdata_import_setting_dialog`
に示すダイアログが表示されます。
インポートの設定を行って「OK」ボタンを押します。

.. _image_rivdata_import_setting_dialog:

.. figure:: images/rivdata_import_setting_dialog.png

   河川測量データインポート設定ダイアログ

ESRI シェープファイルからポリゴンをインポートする場合、ファイル選択後に
:numref:`image_polygon_import_setting_dialog`
に示すダイアログが表示されます。
インポートの設定を行って「OK」ボタンを押します。

.. _image_polygon_import_setting_dialog:

.. figure:: images/polygon_import_setting_dialog.png

   ポリゴンインポート設定ダイアログ

NetCDF ファイルを、時間など位置以外の次元を持つ地理情報にインポートする
場合、ファイル選択後に
:numref:`image_netcdf_import_setting_dialog` に示すダイアログが表示されます。
次元のマッピングに関する設定を行い、「OK」ボタンを押します。

.. _image_netcdf_import_setting_dialog:

.. figure:: images/netcdf_import_setting_dialog.png

   次元のマッピング設定ダイアログ
