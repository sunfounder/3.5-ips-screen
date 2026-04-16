.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_driver_ubuntu:

Ubuntuでの3.5インチIPSスクリーンドライバーのインストール
===============================================================

このセクションでは、**Ubuntu** に3.5インチIPSスクリーンドライバーをインストールする手順を説明します。  
初期設定を完了し、必要なツールをインストールした後、ドライバーを導入することで、3.5インチIPSスクリーンに映像を表示できるようになります。

3.5インチIPSスクリーンドライバーのインストール（重要）
-----------------------------------------------------------------

#. Raspberry Piをモニターに接続して電源を入れます。ネットワーク接続のため、Ethernetケーブルが接続されていることを確認してください。

   .. image:: img/connect_all_ubuntu.jpg
      :width: 90%

#. 画面の指示に従い、言語、キーボード配列、地域、ユーザー名、パスワードなどの初期設定を完了します。

#. 設定完了後、ユーザー名とパスワードでログインし、**Terminal** を検索して起動します。

#. ドライバーのダウンロードに必要なGitをインストールします：

   .. code-block:: shell

        sudo apt install git

#. 内蔵のFirefoxブラウザを開き、以下のサイトにアクセスします：

   ``35-ips-screen.rtfd.io``

#. 以下のコマンドをターミナルに順番にコピー＆実行し、ドライバーをインストールします：

   .. code-block:: shell
   
        sudo rm -rf LCD-show-ubuntu
        git clone https://github.com/sunfounder/LCD-show-ubuntu.git
        chmod -R 755 LCD-show-ubuntu
        cd LCD-show-ubuntu/
        sudo ./MHS35IPS-show

#. インストール完了後：

   * HDMIモニターを取り外します。
   * Raspberry Piは自動的に再起動します。
   * 再起動後、システムは3.5インチIPSスクリーンに表示されます。

画面の回転
-----------------------------

以下のコマンドを実行することで、画面およびタッチの向きを変更できます：

.. code-block:: shell

    cd LCD-show-ubuntu/
    sudo ./rotate.sh 90

システムは自動的に再起動します。再起動後、表示とタッチの向きは **90°** に回転します。  
``90`` の代わりに ``0``、``180``、``270`` を指定することで、任意の向きに設定できます。