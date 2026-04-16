.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_driver_retropie:

RetroPieでの3.5インチIPSスクリーンドライバーのインストール
==================================================================

このセクションでは、**RetroPie** システムに3.5インチIPSスクリーンドライバーをインストールする方法を説明します。  
まずSSHでRaspberry Piに接続し、その後ドライバーをインストールすることで、RetroPieの画面をHDMIモニターと3.5インチスクリーンの両方に表示できるようになります。

3.5インチIPSスクリーンドライバーのインストール（重要）
--------------------------------------------------------------------

#. Raspberry Piをモニターに接続して電源を入れます。ネットワーク接続のため、Ethernetケーブルも接続されていることを確認してください。

   .. image:: img/connect_all_retropie.jpg
      :width: 90%

#. RetroPieの画面が表示されたら、キーボードの **F4** キーを押して終了し、コマンドライン画面に入ります。

#. SSHを有効にするには、以下のコマンドを実行します：

   .. code-block:: shell
   
       sudo raspi-config
   
   メニューで **Interface Options** → **SSH** → **Enable** を選択します。

#. （任意）IPアドレスで接続する場合は、以下のコマンドで確認できます：

   .. code-block:: shell

       hostname -I

   出力例：

   .. code-block:: text

       192.168.100.119 xxxx.xxx

#. PC側でターミナルを開き、以下のいずれかの方法でSSH接続します：

   * **ホスト名を使用（推奨）：**

     .. code-block:: shell

         ssh pi@retropie.local

   * **IPアドレスを使用：**

     .. code-block:: shell

         ssh pi@IP_ADDRESS

     例：

     .. code-block:: shell

         ssh pi@192.168.100.119

   初回接続時は ``yes`` と入力して確認し、その後デフォルトパスワードを入力します：

   .. code-block:: text

       raspberry

#. ログイン後、以下のコマンドを実行して3.5インチIPSスクリーンドライバーをインストールします：

   .. note::
   
       * **RetroPie** では、|link_retropie| で提供されているバージョン（Raspberry Pi 4専用）を使用してください。

   .. code-block:: shell
   
       sudo rm -rf LCD-show-retropie
       git clone https://github.com/sunfounder/LCD-show-retropie.git
       chmod -R 755 LCD-show-retropie
       cd LCD-show-retropie/
       sudo ./MHS35IPS-show

#. インストールが完了すると、Raspberry Piは自動的に再起動します。

   * 再起動後、HDMIモニターと3.5インチIPSスクリーンの両方にRetroPieの画面が表示されます。
   * 起動には1～2分かかる場合がありますので、しばらくお待ちください。

画面の回転
-----------------------------

以下のコマンドを実行することで、画面およびタッチの向きを変更できます：

.. code-block:: shell

    cd LCD-show-retropie/
    sudo ./rotate.sh 90

システムは自動的に再起動します。再起動後、画面とタッチの向きは **90°** に回転します。  
``90`` の代わりに ``0``、 ``180``、 ``270`` を指定することで、任意の向きに設定できます。