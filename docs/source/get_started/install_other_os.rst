.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_other_os:

Ubuntu / Kali Linux / RetroPie のインストール
==============================================

このセクションでは、Raspberry Pi Imagerを使用して、**Ubuntu、Kali Linux、またはRetroPie** をRaspberry Piにインストールする手順を説明します。

必要なもの
------------------------------

* PC（Windows、macOS、またはLinux）
* microSDカード（16GB以上推奨、SanDiskまたはSamsung推奨）
* microSDカードリーダー


対応オペレーティングシステム
-------------------------------

.. warning::

   * 本ガイドは、以下に記載されたOSのみに対応しています。
   * 異なるOSバージョンを使用した場合、ドライバーインストール後に3.5インチIPSスクリーンが正常に動作しない可能性があります。

* **Ubuntu**

  - |link_ubuntu_2404| （Raspberry Pi 4のみ対応）

* **Kali Linux**

  - |link_kali_202503|

* **RetroPie**

  - |link_retropie| （Raspberry Pi 4のみ対応）

-------------------

1. Raspberry Pi Imagerのインストール
-------------------------------------------

#. 公式のRaspberry Pi Imagerダウンロードページ（|link_rpi_imager|）にアクセスし、お使いのOSに対応するバージョンをダウンロードします。

   .. image:: img/imager_download.png
      :width: 70%

#. インストール手順（言語、インストール先、確認など）に従ってインストールし、完了後に **Raspberry Pi Imager** を起動します。

   .. image:: img/imager_install.png
      :width: 90%

--------------------------------------

2. microSDカードへのOS書き込み
------------------------------------------------

#. microSDカードをカードリーダーでPCに接続します。事前に重要なデータはバックアップしてください。

   .. image:: img/insert_sd.png
      :width: 90%

#. Raspberry Pi Imagerを開き、使用するデバイス（例：Raspberry Pi 5 または Raspberry Pi 4）を選択します。

   .. image:: img/imager_device.png
      :width: 90%

#. **OS** をクリックします：

   * 一番下までスクロールし、**Use Custom** を選択します。

     .. image:: img/imager_use_custom.png
        :width: 90%

   * ダウンロードしたOSイメージの保存先フォルダを開き、該当するイメージファイルを選択します。

     .. image:: img/imager_custom_os.png
        :width: 90%

#. **Storage** でmicroSDカードを選択します。

   .. image:: img/imager_storage.png
      :width: 90%

#. 設定内容を確認し、**WRITE** をクリックします。

   .. image:: img/imager_writing_ubuntu.png
      :width: 90%

#. すでにデータがある場合、全データが消去される旨の警告が表示されます。  
   正しいドライブであることを確認し、**I UNDERSTAND, ERASE AND WRITE** をクリックします。

   .. image:: img/imager_erase.png
      :width: 90%

#. 書き込みおよび検証が完了するまで待ちます。完了すると **Write complete!** と表示され、ストレージは自動的に安全に取り外されます。

   .. image:: img/imager_finish_ubuntu.png
      :width: 90%

#. microSDカードを取り外し、Raspberry Piに挿入します。  
   これで新しいOSで起動する準備が整いました。

   .. image:: img/os_sd_to_pi.jpg
      :width: 70%