.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_driver_kali:

Kaliでの3.5インチIPSスクリーンドライバーのインストール
===========================================================

このセクションでは、**Kali Linux** に3.5インチIPSスクリーンドライバーをインストールする手順を説明します。  
システムにログインし、ターミナルを開いてドライバーをインストールすることで、3.5インチIPSスクリーンに映像が表示されるようになります。

3.5インチIPSスクリーンドライバーのインストール（重要）
-------------------------------------------------------------

#. Raspberry Piをモニターに接続し、電源を入れます。ネットワーク接続のため、Ethernetケーブルが接続されていることを確認してください。

   .. image:: img/connect_all_kali.jpg
      :width: 90%

#. デフォルトのKali認証情報でログインします：

   * ユーザー名： ``kali``
   * パスワード： ``kali``

   ログイン後、**Terminal** を検索して起動します。

#. 内蔵のFirefoxブラウザを開き、以下のサイトにアクセスします：

   ``35-ips-screen.rtfd.io``

#. 以下のコマンドをターミナルに順番にコピー＆実行し、ドライバーをインストールします：

   .. code-block:: shell
   
      sudo rm -rf LCD-show-kali
      git clone https://github.com/sunfounder/LCD-show-kali.git
      chmod -R 755 LCD-show-kali
      cd LCD-show-kali/
      sudo ./MHS35IPS-show

#. インストール完了後：

   * HDMIモニターを取り外します。
   * Raspberry Piは自動的に再起動します。
   * 再起動後、システムは3.5インチIPSスクリーンに表示されます。

画面の回転
-----------------------------

以下のコマンドを実行することで、画面およびタッチの向きを変更できます：

.. code-block:: shell

    cd LCD-show-kali/
    sudo ./rotate.sh 90

システムは自動的に再起動します。再起動後、表示とタッチ方向は **90°** に回転します。  
``90`` の代わりに ``0``、 ``180``、 ``270`` を指定することで、任意の向きに設定できます。