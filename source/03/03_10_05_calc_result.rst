.. _sec_file_export_calc_result:

計算結果 (R)
=============

計算結果をエクスポートします。エクスポートファイルの形式はVTKまたはCSVです。

計算結果は、以下のファイルフォーマットにエクスポートできます。

* VTK ファイル (ASCII) (\*.vtk)
* VTK ファイル (バイナリ) (\*.vtk)
* CSVファイル (\*.csv)
* 地勢データファイル (\*.tpo)
* ESRIシェープファイル (\*.shp)

計算結果のエクスポートダイアログ
(:numref:`image_export_calc_result_dialog`)
が表示されます。「OK」ボタンを押すと、出力フォルダにエクスポートファイルが
保存されます。ファイル名は、
「（プレフィックス）+ （連番の番号） + （".vtk" または ".csv"）」となります。

CSVファイルにエクスポートした場合、計算結果の値を出力する列の名前の先頭には、
その値が定義されている位置を表す以下のプレフィックスが付きます。
例えば、格子点で定義された「Depth」という名前の値は、「N_Depth」という名前の列に出力されます。

.. list-table:: CSVファイルの列名のプレフィックス
   :header-rows: 1

   * - プレフィックス
     - 値が定義されている位置
   * - N\_
     - 格子点
   * - C\_
     - セル中心
   * - I\_
     - I方向エッジ
   * - J\_
     - J方向エッジ
   * - K\_
     - K方向エッジ

一部のタイムステップのデータのみをエクスポートする時は、「全タイムステップ」
チェックボックスのチェックを外し、エクスポートする範囲の開始時間、終了時間
及び間引きの間隔を設定します。

一部の領域のデータのみをエクスポートする時は、「詳細を表示(D)」ボタンを
押し、「全領域」チェックボックスのチェックを外し、エクスポートする
範囲を設定します (:numref:`image_export_calc_result_dialog_detail` 参照)。

.. _image_export_calc_result_dialog:

.. figure:: images/export_calc_result_dialog.png
   :width: 200pt

   計算結果のエクスポートダイアログ

.. _image_export_calc_result_dialog_detail:

.. figure:: images/export_calc_result_dialog_detail.png
   :width: 200pt

   計算結果のエクスポートダイアログ 詳細表示
