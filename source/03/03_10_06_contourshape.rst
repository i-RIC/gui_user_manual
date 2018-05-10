.. _sec_file_export_contourshape:

面塗りコンターをESRIシェープファイルへ (C)
==========================================

二次元可視化ウィンドウで描画した面塗りコンターを、ポリゴンとして
ESRIシェープファイルにエクスポートします。

この機能を利用するには、以下の条件を先に整える必要があります。

* 二次元可視化ウィンドウを開き、アクティブにします。
* 二次元可視化ウィンドウ上で、スカラー (格子点) を描画します。
* スカラー (格子点) のプロパティ設定で、表示設定を「カラーフリンジ」や「コンター」ではなく、「面塗りコンター」にします。

これらの条件を整えた上でメニューから「面塗りコンターをESRIシェープファイルへ」
を起動すると、:numref:`image_export_contourshape_selectvalue`
に示すダイアログが表示されます。

.. _image_export_contourshape_selectvalue:

.. figure:: images/export_contourshape_selectvalue.png

   物理量の選択ダイアログ

面塗りコンターをエクスポートしたい物理量を選択して「OK」ボタンをします。
すると、 :numref:`image_export_contourshape_setting` に示す
ダイアログが表示されます。

.. _image_export_contourshape_setting:

.. figure:: images/export_contourshape_setting.png

面塗りコンターのESRIシェープファイルへのエクスポートダイアログ

「OK」ボタンを押すと、設定に従って各タイムステップごとに面塗りコンター
が ESRIシェープファイルに保存されます。