.. _sec_label_func:

ラベル表示機能
===============

ラベル表示機能は、格子点、格子セル、格子エッジなどで定義された
計算結果を、文字列として可視化ウィンドウに表示する機能です。

可視化ウィンドウ (2D), 可視化ウィンドウ (3D) で使用することができます。

右クリックメニューから「プロパティ」を選択すると、
:numref:`image_post_label_dialog` に示すダイアログが表示されます。

.. _image_post_label_dialog:

.. figure:: images/post_label_dialog.png
   :width: 280pt

   ラベル設定 ダイアログ

ラベルの定義は、以下の流れで行います。

1. 入力として使う計算結果の追加
2. 出力の定義
3. 位置、サイズ、フォントなどの設定

詳細は、以下で示します。

入力として使う計算結果の追加と編集
-----------------------------------

「ラベル設定」ダイアログで、「入力として使う計算結果」の枠の中の
「追加 (A)」もしくは「編集 (E)」ボタンを押すと、
:numref:`image_post_label_arg_edit_dialog` に示す
ダイアログが表示され、入力として使う計算結果を追加もしくは編集できます。

各項目の設定項目の詳細を :numref:`table_label_arg_input` に示します。

.. _image_post_label_arg_edit_dialog:

.. figure:: images/post_label_arg_edit_dialog.png
   :width: 200pt

   ラベルの引数の編集 ダイアログ

.. list-table:: ラベルの引数 設定項目
   :name: table_label_arg_input
   :header-rows: 1

   * - 項目名
     - 説明

   * - 位置
     - 引数にする計算結果名の定義位置。グローバル、格子点などから選択する

   * - 計算結果名
     - 入力とする計算結果の名前。コンボボックスから選択する

   * - 変数名
     - 出力の定義の中でこの引数を参照するための変数の名前

   * - I, J, K, インデックス
     - 位置が「グローバル」以外の時に有効。どの格子点(もしくは格子セルなど) の値を表示するか指定する

   * - テスト用の値
     - 「ラベル設定」ダイアログで「テスト」ボタンを押した時、ラベル文字列の生成時にこの変数に代入される値

出力の定義
------------

「出力の定義」には、ラベル文字列を生成するための処理内容を記述します。
処理内容は、 JavaScript 言語で定義できます。例は
:ref:`sec_label_example` を参照してください。

「入力として使う計算結果の追加と編集」の「変数名」で定義した変数を入力と
定義してください。

「テスト」ボタンを押すと、「出力の定義」と「入力として使う計算結果」の
「テスト用の値」によってラベルの文字列が計算され、表示されます。
もし「出力の定義」の内容に問題があれば、エラーメッセージが表示されます。

「出力の定義」には、最終的に文字列が return 文で返されるよう、定義を記述
する必要があります。

位置、サイズ、フォントなどの設定
---------------------------------

位置、サイズ、フォントなどは、ダイアログの「位置とサイズ」、「フォントと色」
の枠内の設定を変更することで設定できます。

また、ラベルの位置とサイズは、オブジェクトブラウザで「ラベル」を選択した
状態で、可視化ウィンドウでラベルをドラッグすることによっても変更することができます。

.. _sec_label_example:

出力の定義例
-------------

ここでは、ラベルの出力のための基本的な情報と例を示します。

改行文字
~~~~~~~~~~~~

複数行の文字列をラベルに表示したい時は、 "\\n" を使用します。"\\n" は改行文字
と呼ばれています。改行文字の使用例を :numref:`label_example_multilines`
に、出力例を :numref:`label_example_multilines_result`
に示します。

.. code-block:: JavaScript
   :name: label_example_multilines
   :caption: 出力の定義例 (改行文字の使用)

   var line1 = "This is the label at first line";
   var line2 = "This is the label at second line";
   return line1 + "\n" + line2;

.. code-block:: none
   :name: label_example_multilines_result
   :caption: 出力の出力例 (改行文字の使用)

   This is the label at first line
   This is the label at second line

数値を書式を指定して出力
~~~~~~~~~~~~~~~~~~~~~~~~~

数値の計算結果について、書式を指定して出力する際は、以下に示す関数を使用します。

* 固定小数点表記: toFixed()
* 指数表記: toExponential()

いずれも、引数として小数点以下の桁数を指定します。

toFixed の使用例と出力例を :numref:`label_example_tofixed`,
:numref:`label_example_tofixed_result` に、

toExponential の使用例と出力例を :numref:`label_example_toexponential`,
:numref:`label_example_toexponential_result` にそれぞれ示します。
ただし、いずれの例でも「入力として使う計算結果」
で Discharge が定義されているものとします。

.. code-block:: JavaScript
   :name: label_example_tofixed
   :caption: 出力の定義例 (toFixedの使用)

   return "Discharge: " + Discharge.toFixed(3);

.. code-block:: none
   :name: label_example_tofixed_result
   :caption: 出力の出力例 (toFixedの使用)

   Discharge: 23.321

.. code-block:: JavaScript
   :name: label_example_toexponential
   :caption: 出力の定義例 (toExponentialの使用)

   return "Discharge: " + Discharge.toExponential(3);

.. code-block:: none
   :name: label_example_toexponential_result
   :caption: 出力の出力例 (toExponentialの使用)

   Discharge: 2.332e+1

制御構文を使用して出力
~~~~~~~~~~~~~~~~~~~~~~

JavaScript 言語では、 if 文、 for 文などが使用できます。
ラベルの文字列の生成には、これらの制御構文も使用できます。

if 文の使用例を :numref:`label_example_if` に、出力例を
:numref:`label_example_if_result` に示します。

.. code-block:: JavaScript
   :name: label_example_if
   :caption: 出力の定義例 (if 文の使用)

   var title = "Flood simulation";
   var wl = "Normal";
   if (Discharge > 2000) {
      wl = "Over Limit";
   }
   return title + "\n" + "Discharge: " + Discharge.toFixed(3) + " (" + wl + ")";

.. code-block:: none
   :name: label_example_if_result
   :caption: 出力の出力例 (if 文の使用)

   Flood simulation
   Discharge: 23.321 (Normal)
