.. _sec_file_property:

プロパティ (P)
===============

現在のプロジェクトに関するプロパティダイアログを表示します。

プロパティダイアログの表示例を :numref:`image_project_property_dialog`
に示します。

このダイアログから、以下を設定することができます。

* 座標系
* オフセット
* t = 0 の日付

.. _image_project_property_dialog:

.. figure:: images/project_property_dialog.png
   :width: 280pt

   プロジェクトプロパティダイアログ

座標系
-------

「座標系」の横の「編集」ボタンを押すと、座標系の選択ダイアログ
(:numref:`image_select_coordsystem_dialog` 参照) が表示されます。ここから、
地理情報や格子で使用する座標系を選択して下さい。

.. _image_select_coordsystem_dialog:

.. figure:: images/select_coordsystem_dialog.png
   :width: 320pt

   座標系の選択ダイアログ

オフセット
-----------

「座標 オフセット」の横の「編集」ボタンを押すと、オフセット設定ダイアログ
(:numref:`image_offset_setting_dialog` 参照) が表示されます。ここから、
座標のオフセット値を入力して下さい。

座標系の原点から遠い位置にある地理情報や格子をプロジェクト内で利用する場合
(例えば、 UTM座標系を使用して赤道から遠く離れた領域のデータを扱う場合)、
オフセットを入力することにより、座標値に関する打切り誤差が減少して、データ処理の
精度が改善します。このようなケースでは、あなたが使用する地理情報や格子に
近い点の X, Y の値を入力して下さい。

.. _image_offset_setting_dialog:

.. figure:: images/offset_setting_dialog.png
   :width: 220pt

   オフセット設定ダイアログ

t = 0 の日付
---------------

「t = 0 の日付」の横の「編集」ボタンを押すと、 t = 0 の日付の設定ダイアログ
(:numref:`image_project_tzero_dialog` 参照) が表示されます。
ここから、t = 0 の日付を入力してください。

t = 0 の日付と書式を指定すると、
アニメーションツールバー
(:ref:`sec_animation_toolbar` 参照)、
二次元可視化ウィンドウ (:ref:`sec_vis2d_window_abst` 参照)、
三次元可視化ウィンドウ (:ref:`sec_vis3d_window_abst` 参照)
での時刻の表示設定に反映されます。

.. _image_project_tzero_dialog:

.. figure:: images/project_tzero_dialog.png
   :width: 300pt

   t = 0 の日付の設定ダイアログ
