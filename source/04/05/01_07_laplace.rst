.. _sec_grid_creation_laplace:

ラプラス方程式を解いて格子を生成
=================================

格子を生成する領域を、定義して、
囲まれた領域内について、ラプラス方程式を解いて格子点の位置を収束計算により求めることによって格子を生成します。

ラプラス方程式を解くことにより、生成される格子のセルの形状は、どれも正方形に近い
ものとなり、ソルバによる計算が安定しやすくなります。

また、このアルゴリズムでは、流れ方向、横断方向に定義する分割線の数に制限がありません。
そのため、自由に分割線を定義することにより、低水敷の境界線を格子線としたり、合流点の格子を
生成したりすることができます。

このアルゴリズムによって生成される格子の例を
:numref:`image_laplace_example_grid1` ～ :numref:`image_laplace_example_grid4`
に示します。

.. _image_poisson_example_grid1:

.. figure:: images/poisson_example_grid1.png
   :width: 300pt

   ポアソン方程式を解いて生成する格子の形状例(1)

.. _image_poisson_example_grid2:

.. figure:: images/poisson_example_grid2.png
   :width: 300pt

   ポアソン方程式を解いて生成する格子の形状例(2)

.. _image_poisson_example_grid3:

.. figure:: images/poisson_example_grid3.png
   :width: 300pt

   ポアソン方程式を解いて生成する格子の形状例(3)

.. _image_poisson_example_grid4:

.. figure:: images/poisson_example_grid4.png
   :width: 300pt

   ポアソン方程式を解いて生成する格子の形状例(4)

このアルゴリズムを選択したら、もし河川測量データがインポートされていた場合は、
コントロール断面数の指定ダイアログ
(:numref:`image_laplace_select_control_xsec_dialog` 参照)が表示されます。
コントロール断面数を指定して「OK」ボタンを押すと、
:numref:`image_laplace_centerline_example` に示すように、河川測量データの
河川中心点をつなぐ形で中心線が定義された状態になります。

.. _image_laplace_select_control_xsec_dialog:

.. figure:: images/laplace_select_control_xsec_dialog.png
   :width: 220pt

   コントロール断面数の指定ダイアログ

.. _image_laplace_centerline_example:

.. figure:: images/laplace_centerline_example.png
   :width: 360pt

   中心線の定義例

次に、左岸線と右岸線を生成します。メニューから「左岸線・右岸線の生成」を選択します。
すると、:numref:`image_laplace_banks_dialog` に示す岸線の生成ダイアログが
表示されます。ここで、左岸線、右岸線を中心線からどれだけ距離を離したところに生成するか
を指定して「OK」ボタンを押すと、 :numref:`image_laplace_banks_example` に
示すように左岸線、右岸線が生成されます。

.. _image_laplace_banks_dialog:

.. figure:: images/laplace_banks_dialog.png
   :width: 200pt

   岸線の生成ダイアログ

.. _image_laplace_banks_example:

.. figure:: images/laplace_banks_example.png
   :width: 340pt

   左岸線・右岸線の生成例

左岸線、右岸線ができた後は、必要に応じて、線を構成する点を移動したり、
領域を分割したりします。

格子を生成したい領域を定義できたら、以下を選択します。

**メニュー**: モードの切替 --> 分割設定モード

:numref:`image_laplace_dividesetting_example` に
示すように、領域の縁に格子分割の位置が表示されます。

.. _image_laplace_dividesetting_example:

.. figure:: images/laplace_dividesetting_example.png
   :width: 340pt

   分割設定モード 表示例

以下を選択することで、領域全体の分割数を設定することができます。

**メニュー**: 格子 (G) --> 格子生成条件 (G) --> 領域全体の分割設定 (W)

:numref:`image_laplace_divisionsetting_wholeregion_dialog` に示す
ダイアログが表示されますので、分割数を指定して「OK」ボタンを押すと、
領域全体の分割数が設定されます。

最後に、メニューから「格子生成」を選択します。すると、作成した格子生成条件
に基づいて、格子が生成されます。

.. _image_laplace_divisionsetting_wholeregion_dialog:

.. figure:: images/image_laplace_divisionsetting_wholeregion_dialog.png
   :width: 240pt

   領域全体の分割設定ダイアログ

.. _image_laplace_grid_example:

.. figure:: images/laplace_grid_example.png
   :width: 360pt

   生成される格子の例

メニュー構成
--------------------

ラプラス方程式を解いて生成するアルゴリズムを選択している時の、
格子 (G) --> 格子生成条件 (C) サブメニューの構成を
:numref:`laplace_menuitems_table_centeronly` 、
:numref:`laplace_menuitems_table_regiondefined` 、
:numref:`laplace_menuitems_table_divisionsetting` 
に示します。

.. _laplace_menuitems_table_centeronly:

.. list-table:: メニューの構成 (左右岸定義前)
   :header-rows: 1

   * - メニュー
     - 説明
   * - 左岸線・右岸線の生成
     - 左岸線・右岸線を生成します
   * - 点の追加 (A)
     - 中心線に頂点を追加します
   * - 点の削除 (R)
     - 中心線から頂点を削除します
   * - 座標の編集 (E)
     - 中心線の頂点座標を編集します

.. list-table:: メニューの構成 (形状編集モード)
   :header-rows: 1

   * - メニュー
     - 説明
   * - 左岸線・右岸線の生成
     - 左岸線・右岸線を生成します
   * - モードの切替 (S)
     - 形状編集モード・分割設定モードの間でモードを切り替えます
   * - 領域の分割 (D)
     - 領域内に線を追加し、領域を分割します
   * - 領域の結合 (J)
     - 現在選択されている線を削除し、線で区切られた2つの領域を結合します
   * - 補間モード
     - 現在選択されている線の補間モードを、スプライン補間と線形補間の間で切り替えます
   * - 点の追加 (A)
     - 中心線に頂点を追加します
   * - 点の削除 (R)
     - 中心線から頂点を削除します
   * - 座標の編集 (E)
     - 中心線の頂点座標を編集します

.. list-table:: メニューの構成 (分割設定モード)
   :header-rows: 1

   * - メニュー
     - 説明
   * - モードの切替 (S)
     - 形状編集モード・分割設定モードの間でモードを切り替えます
   * - 領域全体の分割設定 (W)
     - 領域全体の分割数を設定します
   * - 分割設定 (S)
     - 現在選択されている線の分割数を設定します
   * - 点の配置設定 (P)
     - 現在選択されている線上での点の配置方法を設定します

左岸線・右岸線の生成
---------------------------

左岸線・右岸線を生成します。

:numref:`image_laplace_banks_dialog` に示すダイアログが表示されますので、
中心線から左岸線・右岸線までの距離を入力して「OK」ボタンを押します。

生成される左岸線と右岸線の例を :numref:`image_laplace_banks_example` に示します。

生成した左岸線と右岸線は、頂点をマウスカーソルでドラッグすることにより、変形することができます。

点の追加 (A)
----------------

中心線もしくは領域を定義する線に頂点を追加します。

このメニューを選択した後、中心線もしくは左右岸線の上に
カーソルを移動すると、
:numref:`image_laplace_add_vertex_cursor`
で示すカーソルに変化します。この状態でマウスの左ボタンを押してドラッグすると、
新しい頂点が追加できます。マウスの左ボタンを離すと、頂点の位置が確定します。

.. _image_laplace_add_vertex_cursor:

.. figure:: images/laplace_add_vertex_cursor.png
   :width: 20pt

   頂点の追加が可能な時のマウスカーソル

点の削除 (R)
-------------------

中心線もしくは領域を定義する線から頂点を削除します。

このメニューを選択した後、中心線もしくは領域を定義する線の上に
ある点の上にカーソルを移動すると、
:numref:`image_laplace_remove_vertex_cursor`
で示すカーソルに変化します。この状態でマウスの左ボタンを押すと、
頂点が削除されます。

.. _image_laplace_remove_vertex_cursor:

.. figure:: images/laplace_remove_vertex_cursor.png
   :width: 20pt

   頂点の削除が可能な時のマウスカーソル

.. _subsec_laplace_editcoords:

座標の編集 (T)
----------------------

中心線もしくは現在選択されている線の頂点座標を編集します。

頂点座標を編集するダイアログ
(:numref:`image_laplace_coordinates_dialog` 参照)
が表示されますので、座標を編集して「OK」ボタンを押します。

.. _image_laplace_coordinates_dialog:

.. figure:: images/laplace_coordinates_dialog.png
   :width: 160pt

   頂点の座標編集ダイアログ

初期状態に戻す(R)
----------------------

格子生成条件を破棄し、初期状態に戻します。

.. _subsec_poisson_center_import:

中心線のインポート (E)
------------------------

中心線を、ShapeファイルもしくはCSVファイルからインポートします

:numref:`image_poisson_center_import_dialog` に示すダイアログが
表示されますので、インポートしたいファイルを選択して「開く」ボタンを押します。

.. _image_poisson_center_import_dialog:

.. figure:: images/poisson_center_import_dialog.png
   :width: 380pt

   中心線のインポートダイアログ

左岸線のインポート (L)
------------------------

左岸線を、ShapeファイルもしくはCSVファイルからインポートします

操作手順は :ref:`subsec_poisson_center_import` と同じです。

右岸線のインポート (I)
------------------------

右岸線を、ShapeファイルもしくはCSVファイルからインポートします

操作手順は :ref:`subsec_poisson_center_import` と同じです。

.. _subsec_poisson_center_export:

中心線のエクスポート (N)
------------------------

中心線を、ShapeファイルもしくはCSVファイルにエクスポートします

:numref:`image_poisson_center_export_dialog` に示すダイアログが
表示されますので、エクスポートするファイルの名前を指定して「保存」ボタンを押します。

.. _image_poisson_center_export_dialog:

.. figure:: images/poisson_center_export_dialog.png
   :width: 380pt

   中心線のエクスポートダイアログ

左岸線のエクスポート (F)
------------------------

左岸線を、ShapeファイルもしくはCSVファイルにエクスポートします

操作手順は :ref:`subsec_poisson_center_export` と同じです。

右岸線のエクスポート (G)
------------------------

右岸線を、ShapeファイルもしくはCSVファイルにエクスポートします

操作手順は :ref:`subsec_poisson_center_export` と同じです。
