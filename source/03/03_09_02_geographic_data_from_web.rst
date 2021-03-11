.. _sec_file_import_geo_data_from_web:

地理情報 (webから)
================================

Web サービスからデータをダウンロードして、地理情報をインポートします。

「地理情報 (webから) を選択すると、インポート可能な地理情報のリストが
サブメニューとして表示されます。今のところ、Webからは標高データのみインポート
できます。

インポートは以下の手順で行います。

1. インポートしたい地理情報を選択して下さい。

2. もしまだプロジェクトで使用する座標系を指定していなかった場合、
   「座標系の選択」ダイアログ
   (:numref:`image_select_coordsystem_dialog` 参照)
   が表示されます。座標系を選択して「OK」ボタンを押して下さい。

3. 「領域の選択」ダイアログ (:numref:`image_geo_web_select_region_dialog`) が表示されます。
   以下の操作によって領域を選択し、「次へ」ボタンを押して下さい。

   * Ctrlキー + 左ドラッグで、地図を移動します。
   * Ctrl + 中ドラッグで、地図を拡大・縮小します。「拡大 (I)」「縮小 (O)」ボタンを
     使用することもできます。
   * 左ドラッグで、領域を選択します。選択された領域は、黒線の四角で表示されます。

4. 「次へ」ボタンをクリックすると、「ズームレベル設定」ダイアログが表示されます。
   このダイアログでは、以下のように設定を変更できます。

   * 「ズームレベル」を選択できます。設定を変更すると、ダウンロードされるデータの
     大体の解像度とサイズが「解像度」と「データサイズ」の横に表示されます。
     「ズームレベル」のデフォルト値は、ユーザが通常最も高い解像度のデータを使う
     ようにするため、最大値に設定されています。

   * 「ソース」を選択できます。通常は、USGS が配布している SRTM データが使用されますが、
     例えば日本なら国土地理院が配布している基盤地図情報数値標高モデルを利用することも
     できます。

5. 設定が完了したら、「OK」ボタンを押します。すると、ダウンロードが始まり、
   「お待ちください」ダイアログ (:numref:`image_geo_web_pleasewait_dialog` 参照)
   が表示されます。

6. ダウンロードが完了するとダイアログが消え、ダウンロードされた地理情報が
   :numref:`image_geo_web_example` のように表示されます。

.. _image_geo_web_select_region_dialog:

.. figure:: images/geo_web_select_region_dialog.png
   :width: 340pt

   「領域の選択」ダイアログ

.. _image_geo_web_select_zoomlevel_dialog:

.. figure:: images/geo_web_select_zoomlevel_dialog.png
   :width: 260pt

   「ズームレベル設定」ダイアログ

.. _image_geo_web_pleasewait_dialog:

.. figure:: images/geo_web_pleasewait_dialog.png
   :width: 160pt

   「お待ちください」ダイアログ

.. _image_geo_web_example:

.. figure:: images/geo_web_example.png
   :width: 360pt

   インポートされた地理情報の例
