.. _sec_polyline_data:

折れ線編集機能
=====================

折れ線として定義された地理情報を設定します。

折れ線の表示例を
:numref:`image_example_polyline_data` に示します。

.. _image_example_polyline_data:

.. figure:: images/example_polyline_data.png
   :width: 100pt

   折れ線 表示例

.. note:: 折れ線が定義できる地理情報

   折れ線は、地理情報グループ「参照情報」に対してだけ追加することができます。

.. note:: 河川横断面ウィンドウでの表示

   河川測量データの河川横断面ウィンドウには、折れ線と河川測量データの横断線の
   交点が表示されます。
   
   この機能を利用することで、プリプロセッサーであらかじめ参照情報として折れ線を
   作成しておくことで、道路などの位置を考慮して河川横断線の編集を行うことができます。

   河川横断面ウィンドウでの折れ線の表示例を :numref:`image_polyline_crosssection_view`
   に示します。

   河川横断面ウィンドウの詳細については :ref:`sec_pre_riv_crosssection_window`
   を参照してください。

   .. _image_polyline_crosssection_view:

   .. figure:: images/polyline_crosssection_view.png
      :width: 400pt

      河川横断面ウィンドウでの折れ線の表示例

メニュー構成
--------------

折れ線編集機能に関連するメニューは、プリプロセッサーがアクティブで、
オブジェクトブラウザーで折れ線が選択されていた時、
以下からアクセスできます。

**メニューバー**: 地理情報 (E) --> 折れ線 (L)

折れ線(L) 以下のサブメニューの構成を
:numref:`geo_polyline_menuitems_table` に示します。

.. _geo_polyline_menuitems_table:

.. list-table:: 折れ線メニューの構成
   :header-rows: 1

   * - メニュー
     - 説明
   * - 新しい折れ線を追加 (A)
     - 新しい折れ線を追加します
   * - 名前の編集 (N)
     - オブジェクトブラウザー上に表示される名前を編集します
   * - 頂点の追加 (A)
     - 頂点を追加します
   * - 頂点の削除 (R)
     - 頂点を削除します
   * - 座標の編集 (C)
     - 頂点の座標を編集します
   * - 表示色設定 (S)
     - 表示色を設定します
   * - 削除 (D)
     - 折れ線を削除します

新しい折れ線を追加
---------------------

新しい折れ線を追加するには、以下の手順を行います。

1. オブジェクトブラウザーで、地理情報「参照情報」を
   選択します (:numref:`image_polyline_object_browser_disp` 参照)。

2. メニューから以下の操作を行います。するとオブジェクトブラウザーで
   新しい折れ線が追加され、選択された状態になります。

**メニューバー**: 地理情報 (E) --> 折れ線(L) --> 新しい折れ線を追加(A)

1. 描画領域で、左クリックによって折れ線の頂点を順に指定します
   (:numref:`image_prewindow_polyline_being_defined` 参照)。

2. ダブルクリックするか改行キーを押して、折れ線の定義を完了します。

.. _image_polyline_object_browser_disp:

.. figure:: images/polyline_object_browser_disp.png
   :width: 150pt

   オブジェクトブラウザー 表示例

.. _image_prewindow_polyline_being_defined:

.. figure:: images/prewindow_polyline_being_defined.png
   :width: 350pt

   折れ線定義中のプリプロセッサー

頂点の追加 (A)
---------------

折れ線に頂点を追加します。

このメニューを選択した後、折れ線の上にカーソルを移動すると、
:numref:`image_polyline_cursor_add_vertex`
で示すカーソルに変化します。この状態でマウスの左ボタンを押してドラッグすると、
新しい頂点が追加できます。マウスの左ボタンを離すと、頂点の位置が確定します。

.. _image_polyline_cursor_add_vertex:

.. figure:: images/polyline_cursor_add_vertex.png
   :width: 20pt

   頂点の追加が可能な時のマウスカーソル

頂点の削除 (R)
----------------

折れ線の頂点を削除します。

このメニューを選択した後、折れ線の頂点の上にカーソルを移動すると、
:numref:`image_polyline_cursor_remove_vertex`
で示すカーソルに変化します。この状態でマウスの左ボタンを押すと、
頂点が削除されます。

.. _image_polyline_cursor_remove_vertex:

.. figure:: images/polyline_cursor_remove_vertex.png
   :width: 20pt

   頂点の削除が可能な時のマウスカーソル

座標の編集 (C)
----------------------

折れ線の頂点の座標を編集します。

折れ線の頂点座標を編集するダイアログ
(:numref:`image_polyline_coordinates_dialog` 参照)
が表示されますので、座標を編集して「OK」ボタンを押します。

.. _image_polyline_coordinates_dialog:

.. figure:: images/polyline_coordinates_dialog.png
   :width: 160pt

   折れ線の頂点座標編集ダイアログ

表示色設定 (S)
----------------

折れ線の表示色を編集します。

折れ線の表示色を設定するダイアログ
((:numref:`image_polyline_color_dialog`) 参照)
が表示されますので、表示色を設定して「OK」ボタンを押します。

.. _image_polyline_color_dialog:

.. figure:: images/polyline_color_dialog.png
   :width: 180pt

   折れ線の表示色設定ダイアログ
