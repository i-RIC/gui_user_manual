.. _sec_project_files:

プロジェクトデータに含まれるファイル
=====================================

プロジェクトのデータは、フォルダに展開された複数のファイルに格納されています。

この節では、プロジェクトデータに含まれるファイルについて説明します。

データの種類
------------------

プロジェクトのデータは、以下の2種類に分類されます。

* メタ情報
* 実データ

それぞれについて以下に示します。

メタ情報
----------------

メタ情報は以下のファイルに格納されています。

* project.xml
* subwindows/preprocessor.xml など

メタ情報はすべて XMLファイルに格納されます。

project.xml
~~~~~~~~~~~~~~

メインのメタデータです。以下のような、プロジェクトに関する基本的な情報を格納します。

* プロジェクトを保存した iRIC GUI のバージョン番号
* プロジェクトで実行されるソルバとそのバージョン
* プロジェクトの座標系

subwindows/preprocessor.xml など
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

subwindows/preprocessor.xml など、 subwindows フォルダ内の XML ファイルは、
プリプロセッサ・可視化ウィンドウなど、ウィンドウごとの情報を格納します。

subwindows フォルダ内の XML ファイルは、project.xml で "ref" 属性で参照されています。

subwindows フォルダ内の XML ファイルでは、以下のような情報を格納します。

* オブジェクトブラウザの各項目のデータの種類と、データを保存している実データのファイルパス
* オブジェクトブラウザでのフォルダの開閉状態
* データの可視化設定

.. _sec_project_files_real:

実データ
------------

実データは、プロジェクトで利用されるデータです。実データに含まれる主なデータを以下に示します。

* 地理情報
* 水理情報
* 格子生成条件
* 境界条件設定
* 格子データ
* 計算条件
* ソルバの出力ログ
* 計算結果
* 実測値
* 背景画像

各データについて以下に説明します。

地理情報
~~~~~~~~~~

地理情報は、以下のファイルに格納されます。

* (格子種類)/geographicdata/(地理情報グループ名)/riversurvey1.dat など

**(格子種類)** の部分は、ソルバ定義ファイルの <GridType> 要素の name 属性です。格子種類が1つしかなく <GridType> 要素が定義されていないソルバでは、ソルバ定義ファイルのルート要素 <SolverDefinition> name 属性で指定された値、つまりソルバの名前 (例: Nays2DH) となります。

**(地理情報グループ名)** の部分は、ソルバ定義ファイルの <GridRelatedCondition /> 要素の name 属性で指定された値となります。

地理情報を格納するファイルの形式は、データの種類 (例: 横断測量データ、点群データ) ごとに異なり、iRIC独自のバイナリ形式です。データによっては、複数のファイルに分けて情報が格納されることもあります (例: 雨量データ)。バイナリ形式の内部表現は非公開です。

水理情報
~~~~~~~~~~

水理情報は、以下のファイルに格納されます。

* (格子種類)/hydraulicdata/(水理情報グループ名)/wse1.dat など

**(格子種類)** の部分は、ソルバ定義ファイルの <GridType> 要素の name 属性です。格子種類が1つしかなく <GridType> 要素が定義されていないソルバでは、ソルバ定義ファイルのルート要素 <SolverDefinition> name 属性で指定された値、つまりソルバの名前 (例: Nays2DH) となります。

**(水理情報グループ名)** の部分は、現在のところ waterelevation の1種類となっています。

格子生成条件
~~~~~~~~~~~~~~~~

格子生成条件は、以下のファイルに格納されます。

* (格子種類)/(領域名)/gridcreatingcondition.dat など

**(格子種類)** の部分は、ソルバ定義ファイルの <GridType> 要素の name 属性です。格子種類が1つしかなく <GridType> 要素が定義されていないソルバでは、ソルバ定義ファイルのルート要素 <SolverDefinition> name 属性で指定された値、つまりソルバの名前 (例: Nays2DH) となります。

**(領域名)** の部分は、ほとんどのソルバでは iRICZone となっています。
複数の格子種類を扱うソルバでは、 <GridType> 要素の name 属性に 1, 2, 3 をつけた文字列になっています。

境界条件設定
~~~~~~~~~~~~~~~~

境界条件設定は、以下のファイルに格納されます。

* **対象領域ポリゴン**: (格子種類)/(領域名)/bcsetting/inflow1.dat など
* **設定内容**: (格子種類)/(領域名)/bc/inflow1.dat など

対象領域ポリゴンを格納するファイルは、iRIC独自のバイナリ形式です。バイナリ形式の内部表現は非公開です。

設定内容を格納するファイルは、CGNSファイル形式です。設定内容は、CGNSファイル内の以下の要素に格納されています。

* **設定内容**: iRIC/iRICZone/ZoneBC

格子データ
~~~~~~~~~~~~~~~~

格子データは、以下のファイルに格納されます。

* Case1_input.cgn

Case1_input.cgn は、CGNSファイル形式です。
格子データは、CGNSファイル内の以下の要素に格納されています。

* **格子の次元**: iRIC/iRICZone/ data
* **格子点座標**: iRIC/iRICZone/GridCoordinates
* **格子属性**: iRIC/iRICZone/GridConditions
* **格子セルの定義**: iRIC/iRICZone/Element/ElementConnectivity (非構造格子のみ)
* **境界条件**: iRIC/iRICZone/ZoneBC

計算条件
~~~~~~~~~~~~~~~~

計算条件データは、以下のファイルに格納されます。

* Case1_input.cgn

Case1_input.cgn は、CGNSファイル形式です。
計算条件は、CGNSファイル内の以下の要素に格納されています。

* **基本的な設定項目**: iRIC/iRICZone/CalculationConditions
* **複合型の設定項目**: iRIC/iRICZone/GridComplexConditions

ソルバの出力ログ
~~~~~~~~~~~~~~~~

ソルバの出力ログは、以下のファイルに格納されます。

* consoleLog.txt

consoleLog.txt はテキスト形式です。
ソルバが標準エラーと標準出力に出力した内容を格納します。

計算結果
~~~~~~~~~~~~~~~~

計算結果が格納されるファイルは、プロジェクトの設定「計算結果をタイムステップごとに別のファイルに出力する」の
設定内容によって異なります。

タイムステップごとに別のファイルに出力する場合
+++++++++++++++++++++++++++++++++++++++++++++++++++++

計算結果は以下のファイルに格納されます。

* result/Solution1.cgn など

Solution1.cgn など は、CGNSファイル形式です。
計算結果は、CGNSファイル内の以下の要素に格納されています。

* **格子点で定義された計算結果**: iRIC/iRICZone/FlowSolution1
* **格子セルで定義された計算結果**: iRIC/iRICZone/FlowCellSolution1
* **格子エッジ (I方向) で定義された計算結果**: iRIC/iRICZone/FlowIFaceSolution1
* **格子エッジ (J方向) で定義された計算結果**: iRIC/iRICZone/FlowJFaceSolution1
* **格子エッジ (K方向) で定義された計算結果**: iRIC/iRICZone/FlowKFaceSolution1
* **パーティクルで定義された計算結果**: iRIC/iRICZone/ParticleSolution1, iRIC/iRICZone/ParticleGroupSolution1
* **パーティクルで定義された計算結果 (画像を表示)**: iRIC/iRICZone/ParticleGroupImageSolution1
* **ポリゴンで定義された計算結果**: iRIC/iRICZone/PolyDataSolution1
* **グローバルに定義された計算結果**: iRIC/BaseIterativeData

タイムステップごとに別のファイルに出力しない場合
+++++++++++++++++++++++++++++++++++++++++++++++++++++

計算結果は以下のファイルに格納されます。

* Case1.cgn

Case1.cgn は、CGNSファイル形式です。
計算結果は、CGNSファイル内の以下の要素に格納されています。

* **格子点で定義された計算結果**: iRIC/iRICZone/FlowSolution1 など
* **格子セルで定義された計算結果**: iRIC/iRICZone/FlowCellSolution1 など
* **格子エッジ (I方向) で定義された計算結果**: iRIC/iRICZone/FlowIFaceSolution1 など
* **格子エッジ (J方向) で定義された計算結果**: iRIC/iRICZone/FlowJFaceSolution1 など
* **格子エッジ (K方向) で定義された計算結果**: iRIC/iRICZone/FlowKFaceSolution1 など
* **パーティクルで定義された計算結果**: iRIC/iRICZone/ParticleSolution1, iRIC/iRICZone/ParticleGroupSolution1 など
* **パーティクルで定義された計算結果 (画像を表示)**: iRIC/iRICZone/ParticleGroupImageSolution1 など
* **ポリゴンで定義された計算結果**: iRIC/iRICZone/PolyDataSolution1 など
* **グローバルに定義された計算結果**: iRIC/BaseIterativeData

実測値
~~~~~~~~

実測値は以下のファイルに格納されます。

* MeasuredData_1.vtk など

MeasuredData_1.vtk などは、VTKバイナリ形式です。フォーマットの詳細は以下を参照してください。

https://docs.vtk.org/en/latest/design_documents/VTKFileFormats.html

背景画像
~~~~~~~~~~

背景画像は以下のファイルに格納されます。

* backgroundimages/image1.png など

image1.png などは PNGファイル形式です。
