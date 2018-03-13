iRIC の機能
============

iRIC の機能を大きく以下の8つのグループに分け、各機能の概要について説明します。

-  地理情報の編集
-  格子の生成
-  格子の編集
-  実測値の読み込み
-  計算条件の設定
-  ソルバーの起動
-  計算結果の可視化・グラフの描画

.. _sec_abst_edit_geo_data:

地理情報編集機能
----------------

地理情報とは、標高、植生種類、植生密度、土地の利用目的など、
地図上での座標とそこでの属性値を持つデータです。iRIC
は地理情報をインポートし、編集する機能を持ちます。

地理情報は、格子の格子点もしくはセルごとの属性の値を補間して決定するために
利用されます。また、河川測量データについては、格子生成に利用することもできます。

どのような属性を入力する必要があるかは、利用するソルバーによって異なります。

iRIC では、以下の3つのデータ型の地理情報を取り扱い、編集することができます。

-  河川測量データ
-  地勢データ
-  ポリゴン

河川測量データの表示例を :numref:`image_geodata_riversurvey` に、
地勢データの表示例を :numref:`image_geodata_pointset` に、
ポリゴンの表示例を :numref:`image_geodata_polygon` にそれぞれ示します。

.. _image_geodata_riversurvey:

.. figure:: images/geodata_riversurvey.png

   河川測量データ表示例

.. _image_geodata_pointset:

.. figure:: images/geodata_pointset.png

   地勢データ表示例

.. _image_geodata_polygon:

.. figure:: images/geodata_polygon.png

   ポリゴン表示例

詳細については、:ref:`sec_pre_geodata` を参照してください。

.. _sec_abst_create_grid:

格子生成機能
-----------------

ソルバーが計算を実行する時に利用する格子を作成します。格子生成は内部で、
以下の2つの段階に分けて行われます。

1. 格子の形状 (各格子点の座標) を決定します。
2. 格子点、格子セルごとにもつ属性の値を、
   地理情報に基づいて補間して決定します。

1. については、ユーザはソルバーが必要とする種類の格子を生成できるアルゴリズム
から1つ選択し、格子を生成することができます。

一方、2. は地理情報のデータ型によって、自動的に行われます。

iRIC では以下の種類の格子を生成することができます。

-  二次元構造格子
-  二次元非構造格子
-  一次元構造格子 (格子点ごとに断面情報を保持)

詳細については、 :ref:`sec_pre_grid_creating_func` を参照してください。

格子編集機能
-------------------

格子を編集します。ユーザは以下を行えます。

-  格子の形状 (格子点の座標) の編集
-  格子点もしくは格子セルごとにもつ属性の編集

詳細については、 :ref:`sec_pre_editing_grid` を参照してください。

.. _sec_abst_load_measured_data:

実測値の読み込み機能
---------------------

実測値を読み込み、格子生成の際の参考情報として利用したり、
計算結果と比較したりします。ユーザは以下を行えます。

-  実測値のインポート
-  スカラー量の実測値、ベクトル量の実測値の表示設定

詳細については、 :ref:`sec_pre_measured_data` を参照してください。

計算条件設定機能
-------------------

計算条件を設定します。設定する計算条件の内容は、ソルバーによって異なります。

詳細については :ref:`sec_calc_cond` を参照してください。

ソルバー起動機能
---------------------

ソルバーを起動して計算を実行し、ソルバーコンソールを使ってソルバーの実行状態を
監視します。開始した計算を途中で終了することもできます。
ソルバー起動時の、ソルバーコンソールの表示例を
:numref:`image_solver_console_window_func` に示します。

.. _image_solver_console_window_func:

.. figure:: images/solver_console_window.png

   ソルバーコンソール

詳細については、 :ref:`sec_simulation` を参照してください。

可視化機能
-----------

ソルバーの計算結果について可視化します。可視化ウィンドウ (2D)
(:numref:`image_2d_post_window_func` 参照) 、
鳥瞰図可視化ウィンドウ (2D)
(:numref:`image_birdseye_2d_post_window_func` 参照)、
可視化ウィンドウ (3D)
(:numref:`image_3d_post_window_func` 参照) を利用して行います。

詳細については、 :ref:`sec_vis_funcs` を参照してください。

.. _image_2d_post_window_func:

.. figure:: images/2d_post_window.png

   可視化ウィンドウ (2D)

.. _image_birdseye_2d_post_window_func:

.. figure:: images/birdseye_2d_post_window.png

   鳥瞰図可視化ウィンドウ (2D)

.. _image_3d_post_window_func:

.. figure:: images/3d_post_window.png

   可視化ウィンドウ (3D)

グラフ描画機能
----------------

ソルバーの計算結果について、グラフを描画します。グラフウィンドウ
(:numref:`image_graph_window_func` 参照) 、散布図ウィンドウ
(:numref:`image_scattered_chart_window_func` 参照) を利用して
行います。

詳細については、 :ref:`sec_making_graph` を参照してください。

.. _image_graph_window_func:

.. figure:: images/graph_window.png

   グラフウィンドウ

.. _image_scattered_chart_window_func:

.. figure:: images/scattered_chart_window.png

   散布図ウィンドウ
