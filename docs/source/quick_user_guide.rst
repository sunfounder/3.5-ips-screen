.. note::

    こんにちは、Facebook の SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts コミュニティへようこそ！  
    他の愛好者たちと一緒に Raspberry Pi、Arduino、ESP32 の世界をさらに深く探求しましょう。

    **なぜ参加するのか？**  

    - **専門的なサポート**: コミュニティやチームのサポートを受けて、購入後のトラブルや技術的な課題を解決できます。  
    - **学び＆共有**: ヒントやチュートリアルを共有し、スキルを磨きましょう。  
    - **限定プレビュー**: 新製品の発表や先行プレビューを誰よりも早くチェックできます。  
    - **特別割引**: 最新製品を特別割引価格で入手できます。  
    - **季節限定プロモーションとプレゼント企画**: 季節ごとのキャンペーンやプレゼント企画に参加できます。  

    👉 さあ、一緒に発見と創作を楽しみましょう！ [|link_sf_facebook|] をクリックして今すぐ参加してください！

クイックユーザーガイド
===========================

1. オペレーティングシステムをインストールする
--------------------------------------------------

**Raspberry Pi Imager** を使って、お使いの Raspberry Pi ボードモデルに対応するオペレーティングシステムをインストールしてください。  

詳しい手順は :ref:`install_os` をご覧ください。

.. note::

    * **Raspberry Pi OS** の場合:

      - **Raspberry Pi 4 または 5** を使用している場合は、Raspberry Pi Imager にアクセスして最新の Trixie システム（リリース日: 2025-10-1）をインストールしてください。    
      - **Raspberry Pi 3B/3B+ または Zero 2W** を使用している場合は、|link_bullseye| を訪れてダウンロードしてください。
      - 他の Raspberry Pi モデルは互換性がありません。

    * **Ubuntu** システムの場合は、Raspberry Pi Imager にアクセスし、**Ubuntu Desktop 24.04 LTS（64 bit）** または **Ubuntu Server 24.04 LTS（64 bit）** を選択してください。

    * **Kali Linux** システムの場合は、|link_kali_linux| を訪れてダウンロードしてください。

    * **Retropie** システムの場合は、|link_retropie| からお使いの Raspberry Pi（Pi 5 以外）用のバージョンをダウンロードしてください。

2. ディスプレイを Raspberry Pi に接続する
-----------------------------------------------

この 3.5 インチ IPS ディスプレイは Raspberry Pi と同じピン配置を使用します。

**手順**:

1. Raspberry Pi の電源を切り、電源ケーブルを外します。  
2. ディスプレイを GPIO ヘッダー（Pin 1 に合わせて）に揃え、しっかりと差し込みます。  
3. 準備した MicroSD カードを挿入し、Raspberry Pi の電源を入れます。

.. image:: img/3.5_ips_plugin_pi.jpg
    :width: 400
    :align: center

.. _install_driver:

3. ドライバーのインストール
-------------------------------

3.5 インチ IPS ディスプレイは、動作させるためにドライバーのインストールが必要です。使用するオペレーティングシステムに応じて、以下の手順に従ってください。

.. 
    .. warning::

..     * 新しくインストールされた未設定のシステム（新しいイメージ、工場出荷時の状態）でのみインストールしてください。
..     * 設定済みのシステムにインストールすると、ログイン問題が発生したり、デバイスが使用不能になる可能性があります。
..     * ディスプレイはカーネルレベルのドライバを使用しているため、カーネルを更新しないでください。


**一般的な注意点**:

* まず :ref:`compatible_os` を確認してください。  
* ``git`` がインストールされていることを確認します（ ``sudo apt install git`` ）。  
* ドライバーのインストールには 1〜3 分ほどかかります。  
* インストール完了後、システムは自動的に再起動します。  


**Raspberry Pi OS 用**

.. warning::

    * **Raspberry Pi OS**: 

      - **Raspberry Pi 4 または 5** を使用している場合は、Raspberry Pi Imager にアクセスして最新の Trixie システム（リリース日: 2025-10-1）をインストールしてください。    
      - **Raspberry Pi 3B/3B+ または Zero 2W** を使用している場合は、|link_bullseye| を訪れてダウンロードしてください。
    
    * インストール後に ``sudo apt update`` または ``sudo apt upgrade`` を実行しないでください。これらを実行するとカーネルが更新され、ディスプレイドライバーが動作しなくなる可能性があります。

以下のコマンドでドライバーをインストールできます:

.. raw:: html

   <run></run>

.. code-block:: shell


    sudo rm -rf LCD-show
    git clone https://github.com/sunfounder/LCD-show.git
    chmod -R 755 LCD-show
    cd LCD-show/
    sudo ./MHS35IPS-show

ドライバーが正常にインストールされると 2〜3 分後に再起動が行われ、3.5 インチ IPS 画面に Raspberry Pi デスクトップが表示されます。

.. note::

    * Raspberry Pi 3B/3B+ または Zero 2W を使用する場合、この画面を使うには **Bullseye** OS をインストールする必要があります。  
    * インストール中に HDMI モニターが接続されていると、再起動後もデスクトップは HDMI モニターに表示されます。  
    * 3.5 インチ IPS 画面を使用する場合は、HDMI モニターを外して Raspberry Pi を再起動してください。  

**Ubuntu Desktop/Server 用**

以下のコマンドでドライバーをインストールできます:

.. raw:: html

   <run></run>

.. code-block:: shell

    sudo rm -rf LCD-show-ubuntu
    git clone https://github.com/sunfounder/LCD-show-ubuntu.git
    chmod -R 755 LCD-show-ubuntu
    cd LCD-show-ubuntu/
    sudo ./MHS35IPS-show

ドライバーが正常にインストールされると、システムは自動的に再起動し、3.5 インチ IPS 画面にデスクトップが表示されます。

.. note::

    * HDMI モニターが接続されている場合、デフォルトで HDMI 出力が優先されます。  
    * 3.5 インチ IPS 画面を使う場合は、HDMI モニターを外してデバイスを再起動してください。  


**Kali Linux 用**

以下のコマンドでドライバーをインストールできます:

.. raw:: html

   <run></run>

.. code-block:: shell

    sudo rm -rf LCD-show-kali
    git clone https://github.com/sunfounder/LCD-show-kali.git
    chmod -R 755 LCD-show-kali
    cd LCD-show-kali/
    sudo ./MHS35IPS-show

ドライバーが正常にインストールされると、システムは再起動し、3.5 インチ IPS 画面にデスクトップが表示されます。

.. note::

    * HDMI モニターが接続されている場合、再起動後も HDMI 出力が優先されます。  
    * 3.5 インチ IPS 画面を使用するには、HDMI モニターを外して Kali Linux を再起動してください。  

**RetroPie 用**

.. note::

    * **Retropie** を使用する場合は、 |link_retropie| からお使いの Raspberry Pi（Pi 5 を除く）に対応したバージョンをダウンロードしてください。

以下のコマンドでドライバーをインストールできます:

.. raw:: html

   <run></run>

.. code-block:: shell

    sudo rm -rf LCD-show-retropie
    git clone https://github.com/sunfounder/LCD-show-retropie.git
    chmod -R 755 LCD-show-retropie
    cd LCD-show-retropie/
    sudo ./MIS35-show

ドライバーが正常にインストールされると、システムは再起動し、3.5 インチ IPS 画面に RetroPie のインターフェースが表示されます。

.. note::

    * HDMI モニターが接続されている場合、インターフェースは HDMI 出力に表示され続けます。  
    * 3.5 インチ IPS 画面を使用するには、HDMI モニターを外して Raspberry Pi を再起動してください。  

4. ディスプレイを回転させる
-----------------------------

以下のコマンドを実行すると、画面とタッチ操作の向きを回転させることができます。

.. note::

    使用するシステムに応じてディレクトリを変更してください:  
    
    * Raspberry Pi OS → ``cd LCD-show/``  
    * Ubuntu → ``cd LCD-show-ubuntu/``  
    * Kali → ``cd LCD-show-kali/``  
    * RetroPie → ``cd LCD-show-retropie/``

.. raw:: html

   <run></run>

.. code-block:: shell

    cd LCD-show/
    sudo ./rotate.sh 90

システムは自動的に再起動します。再起動後、画面とタッチ操作は **90°** 回転します。  
``90`` を ``0``、 ``180``、 ``270`` に置き換えることで、希望の角度に変更できます。
