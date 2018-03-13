.. _sec_file_export_calc_result:

計算結果 (R)
=============

計算結果をエクスポートします。エクスポートファイルの形式はVTKまたはCSVです。

計算結果のエクスポートダイアログ
(:numref:`image_export_calc_result_dialog`)
が表示されます。「OK」ボタンを押すと、出力フォルダにエクスポートファイルが
保存されます。ファイル名は、
「（プレフィックス）+ （連番の番号） + （".vtk" または ".csv"）」となります。

一部のタイムステップのデータのみをエクスポートする時は、「全タイムステップ」
チェックボックスのチェックを外し、エクスポートする範囲の開始時間、終了時間
及び間引きの間隔を設定します。

一部の領域のデータのみをエクスポートする時は、「詳細を表示(D)」ボタンを
押し、「全領域」チェックボックスのチェックを外し、エクスポートする
範囲を設定します (:numref:`image_export_calc_result_dialog_detail` 参照)。

.. _image_export_calc_result_dialog:

.. figure:: images/export_calc_result_dialog.png

   計算結果のエクスポートダイアログ

.. _image_export_calc_result_dialog_detail:

.. figure:: images/export_calc_result_dialog_detail.png

   計算結果のエクスポートダイアログ 詳細表示
