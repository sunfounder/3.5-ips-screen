.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_driver_rapios:

Raspberry Pi OSでの3.5インチIPSスクリーンドライバーのインストール
==========================================================================

このセクションでは、**Raspberry Pi OS** に3.5インチIPSスクリーンドライバーをインストールする方法を説明します。  
モニターを使用する方法と、SSHによるリモート接続（ヘッドレス）のいずれでも操作できます。

モニターがある場合
-------------------------

**必要なもの**

* Raspberry Pi
* 純正電源アダプター
* MicroSDカード
* HDMIケーブル  
  （Raspberry Pi 4/5では、電源端子に最も近い **HDMI0** ポートを使用してください。）
* モニター
* キーボードとマウス

**手順**

#. MicroSDカードをRaspberry Piに挿入します。
#. キーボード、マウス、モニターを接続します。
#. Raspberry Piの電源を入れます。
#. 起動後、Raspberry Pi OSのデスクトップが表示されます。 

   .. image:: img/connect_all_rpios.jpg
      :width: 90%

#. コマンド入力のため、**Terminal** を開きます。

   .. image:: img/open_terminal.png
      :width: 80%
      :align: center


モニターがない場合（ヘッドレス）
----------------------------------

モニターがなくても、リモートで設定・ログインが可能です。  
多くのユーザーにとって最も便利な方法です。

**必要なもの**

* Raspberry Pi
* 純正電源アダプター
* MicroSDカード
* 同一ネットワークに接続されたPC

**ヒント**

* Raspberry Pi ImagerでOSを書き込む際に、:ref:`imager_custom` に記載された設定を事前に完了しておいてください。
* Raspberry PiとPCが同一のローカルネットワークに接続されていることを確認してください。
* 安定性のため、可能であればEthernet接続を推奨します。


**SSHで接続する**

#. PCでターミナルを開き（Windows：**PowerShell**、macOS/Linux：**Terminal**）、以下のコマンドで接続します：

   .. code-block:: bash

      ssh <username>@<hostname>.local
      # 例：
      ssh daisy@pi.local

#. もしくは、ルーターのDHCP一覧からIPアドレスを確認して接続します：

   .. code-block:: bash

      ssh <username>@<IP address>
      # 例：
      ssh daisy@192.168.1.42

#. 初回接続時は ``yes`` と入力してSSH証明書を承認します。

#. Raspberry Pi Imagerで設定したパスワードを入力します。  
   （入力中は画面に表示されませんが正常です。）

#. ログイン後、コマンドラインで操作できるようになります。

   .. image:: img/ssh_login.png
      :align: center


--------------------------------------

リモートGUIアクセス（任意）
----------------------------------------

GUIで操作したい場合：

.. image:: img/desktop_trixie.png
   :align: center

* :ref:`remote_desktop` — **VNC** を使用してデスクトップにアクセス
* |link_rpi_connect| — **Raspberry Pi Connect** をブラウザから利用

--------------------------------------

3.5インチIPSスクリーンドライバーのインストール（重要）
----------------------------------------------------------------

3.5インチIPSスクリーンを有効にするための重要な手順です。

以下のコマンドを実行します：

.. code-block:: shell

   sudo rm -rf LCD-show
   git clone https://github.com/sunfounder/LCD-show.git
   chmod -R 755 LCD-show
   cd LCD-show/
   sudo ./MHS35IPS-show

インストール後：

* HDMIモニターを取り外します。 
* 再起動後、システムは3.5インチIPSスクリーンに表示されます。

画面の回転
-----------------------------

以下のコマンドを実行することで、画面およびタッチの向きを変更できます：

.. code-block:: shell

    cd LCD-show/
    sudo ./rotate.sh 90

システムは自動的に再起動します。再起動後、画面とタッチの向きは **90°** に回転します。  
``90`` の代わりに ``0``、``180``、``270`` を指定することで、任意の向きに設定できます。