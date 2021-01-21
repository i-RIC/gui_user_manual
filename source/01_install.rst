インストール
=============

iRIC のインストール方法について説明します。

インストール手順
-----------------

1. iRIC のインストーラを iRIC の webサイトからダウンロードします。 https://i-ric.org/download/ にアクセスして、「Version 3.X」 の中の一番新しいインストーラをダウンロードしてください。
2. ダウンロードしたインストーラを実行します。

.. warning: インストール先フォルダについて

   インストール先フォルダのパスには日本語、スペースが含まれないよう注意してください。

   * 良い例: C:\\Users\\user1\\iRIC
   * 良い例: D:\\iRIC
   * 悪い例1: C:\\Users\\ユーザ1\\iRIC
   * 悪い例2: C:\\Users\\Firstname Lastname\\iRIC

Miniconda のインストールに関する注意点
------------------------------------------

iRIC 3.0 では、Python で開発されたソルバを実行することができます。

Python で開発されたソルバを実行できるようにするため、iRIC の インストーラには、Python 実行環境として Miniconda が含まれています。

Miniconda の詳細については以下をご参照ください。

https://docs.conda.io/en/latest/miniconda.html

iRIC のインストーラを使用して Miniconda をインストールすると、 Miniconda は 指定したインストール先フォルダの下の
「Miniconda3」フォルダ以下にインストールされます。

既に Miniconda がインストールされた環境に iRIC をインストールする場合、 iRIC のインストーラを利用して Miniconda を
追加でインストールすると、先にインストールした環境に悪影響が生じます。そのため、iRIC のインストーラを利用した Miniconda のインストールは行わず、
:ref:`sec_use_existing_miniconda` の手順に従ってください。

もし既に Miniconda がインストールされた環境に誤って Miniconda を追加でインストールしてしまった場合、 :ref:`sec_recover_miniconda3` の手順に従ってください。

.. _sec_use_existing_miniconda:

既存の Miniconda を使った iRICソルバの実行環境の構築
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

既存の Miniconda を使って iRICソルバの実行環境を構築します。
Miniconda でなく Anaconda をインストールしている場合も、この手順をご利用いただけます。

以下の手順で行います。

インストール時の Miniconda の除外
..................................

iRIC のインストーラを実行する時、「コンポーネントの選択」画面で、以下のチェックを外してください。

* Miniconda 
* iriclib for Miniconda

iRIC 用仮想環境の作成
.....................

スタートメニューから 「Anaconda Prompt (miniconda3)」を起動し、以下のコマンドを実行してください。

.. code-block:: text
   :caption: 仮想環境の作成コマンド

   conda create -n iric python=3.8
   conda activate iric
   conda install numpy

これで、「iric」という名前の仮想環境が作成され、Python 3.8, numpy がインストールされます。

例えば、D:\\Miniconda3 に Miniconda をインストールしていた場合、D:\\Miniconda\\Envs\\iric というフォルダが作成されており、
Python.exe があることを確認してください。

Python 用 iriclib のインストール
................................

上記で作成した仮想環境に、iriclib をインストールします。

例えば、D:\\Miniconda3 に Miniconda をインストールしていた場合、D:\\Miniconda\\Envs\\iric\\Lib\\site-packages に以下のファイルをコピーしてください。
以下では、iRIC のインストール先フォルダ (例: 「C:\\Users\\user1\\iRIC」)　を IRICROOT と記載しています。

* IRICROOT\\guis\\prepost\\sdk\\python\\iric.py
* IRICROOT\\guis\\prepost\\sdk\\python\\_iric_python38.pyd --> _iric.pyd に名前を変えてコピーしてください
* IRICROOT\\guis\\prepost\\iriclib.dll
* IRICROOT\\guis\\prepost\\cgnsdll.dll
* IRICROOT\\guis\\prepost\\hdf5.dll
* IRICROOT\\guis\\prepost\\szip.dll
* IRICROOT\\guis\\prepost\\zlib.dll

iriclib の動作確認
..................

スタートメニューから 「Anaconda Prompt (miniconda3)」を起動し、以下のコマンドを実行してください。

.. code-block:: text
   :caption: iriclib の動作確認

   conda activate iric
   python
   import iric

エラーメッセージが表示されなければ、無事に iriclib がインストールされています。

iRIC での Python パスの設定
...............................

iRIC で、ソルバの実行に使用する Python のパスを設定します。以下の手順で行います。

1. デスクトップの iRIC アイコンをダブルクリックして iRIC を起動します。
2. メニューから オプション --> 設定 を選択します。
3. Python パスとして、上記で作成した仮想環境の Python.exe を選択します。上記の例なら 「D:\\Miniconda\\Envs\\iric\\Python.exe」を指定します。

以上で、手順は完了です。

.. _sec_recover_miniconda3:

Miniconda を追加インストールしてしまった場合の対応
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

既に Miniconda がインストールされた環境に、 iRIC のインストーラを利用して追加で Miniconda をインストールしてしまった場合、以下の問題が生じます。

* スタートメニューから起動できる、「Anaconda3 (64bit)」フォルダの下の「Anaconda Prompt (miniconda3)」と「Anaconda Powershell Prompt (miniconda3)」が、新しくインストールした Miniconda の環境を参照するようになってしまう

上記問題については、以下の方法で対応します。

1. スタートメニューの「Anaconda Prompt (miniconda3)」を右クリックし、「その他」 --> 「ファイルの場所を開く」を選択
2. エクスプローラが開き、「Anaconda Prompt (miniconda3)」のリンクが表示されるので、右クリックして「プロパティ」を選択
3. 「リンク先」欄に以下の値が設定されているのを確認する。

   %windir%\System32\cmd.exe "/K" (iRICインストール先)\\Miniconda3\\Scripts\\activate.bat (iRICインストール先)\\Miniconda3

4. (iRICインストール先) の箇所を、先にインストールした Miniconda のインストール先のパスに書き換えて「OK」ボタンを押す。

「Anaconda Powershell Prompt (miniconda3)」 についても同様の方法で対応できます。
