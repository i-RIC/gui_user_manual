.. _sec_pre_editing_grid:

格子編集機能
===================

格子編集機能について説明します。

格子編集機能は、プリプロセッサーがアクティブな時に「格子 (G)」メニューから
行えます。格子については、以下の操作を行えます。

-  編集
-  削除

編集には、以下の4つがあります。

-  格子点座標の編集
-  格子点属性の編集
-  セル属性の編集
-  境界条件の編集

上記の編集操作は、いずれも以下の手順で行います。

#. オブジェクトブラウザーで、編集対象の格子を選択します。
#. 編集対象の格子点を選択します。
#. 選択した格子点について、座標もしくは属性を編集します。

1. と 3. については、行いたい操作ごとに
:ref:`sec_grid_edit_node_coordinates` ～
:ref:`sec_grid_edit_cell_atts` で説明します。
2. の格子点の選択については操作方法が共通ですので、
:ref:`sec_grid_edit_select_node` で説明します。

格子のインポートとエクスポートについては、それぞれ
:ref:`sec_file_import_grid` と
:ref:`sec_file_export_grid` を参照してください。

.. toctree::
   :maxdepth: 1

   02_01_select_node
   02_02_edit_node_coordinates
   02_03_edit_node_attributes
   02_04_edit_cell_attributes
   02_05_edit_boundary_conds
   02_06_delete
   02_07_display_settings
