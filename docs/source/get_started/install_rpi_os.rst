.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message
   
.. _install_os:

Raspberry Pi OSのインストール
===================================

Raspberry Piを使用する前に、microSDカードに **Raspberry Pi OS** をインストールする必要があります。  
このセクションでは、初心者向けに **Raspberry Pi Imager** を使用した手順をわかりやすく説明します。

対応モデルおよびOSバージョン
-------------------------------------

.. warning::

   * 本ガイドは、以下に記載されたモデルおよびOSバージョンのみに対応しています。
   * その他のバージョンを使用した場合、ドライバーインストール後に3.5インチIPSスクリーンが正常に動作しない可能性があります。

* **対応モデル**：

  - Raspberry Pi 5
  - Raspberry Pi 4 Model B

* **動作確認済みOSバージョン**：

  - **Trixie Desktop（64-bit）** （リリース日：2025-12-04）
  - **Bookworm Desktop（64-bit）** （リリース日：2025-11-24、|link_bookwarm_250513|）

    Bookwormにドライバーをインストールした後は、``startx`` を実行してデスクトップ環境を起動する必要があります。

必要なもの
------------------------------

* PC（Windows、macOS、またはLinux）
* microSDカード（16GB以上推奨、SanDiskまたはSamsung推奨）
* microSDカードリーダー

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

#. **OS** をクリックし、インストールするシステムを選択します：

   * **Trixie** の場合：推奨バージョンをそのまま選択します。
   * **Bookworm** の場合：  
     **Raspberry Pi OS (Other) → Raspberry Pi OS (Legacy, 64-bit)** を選択します。

   .. image:: img/imager_os.png
      :width: 90%

#. **Storage** でmicroSDカードを選択します。 

   .. image:: img/imager_storage.png
      :width: 90%

#. **Next** をクリックしてカスタマイズ設定に進みます。

   .. note::

      * モニター・キーボード・マウスを直接接続して使用する場合は、**SKIP CUSTOMISATION** を選択して問題ありません。  
      * ヘッドレス（Wi-Fi経由でリモート接続）で使用する場合は、カスタマイズ設定を必ず行ってください。

   .. image:: img/imager_custom_skip.png
      :width: 90%

-------------------

.. _imager_custom:

3. OSカスタマイズ設定
------------------------------------------

#. **ホスト名の設定**

   * Raspberry Piに一意のホスト名を設定します。  
   * 後から ``hostname.local`` で接続できるようになります。

   .. image:: img/imager_custom_hostname.png
      :width: 90%

#. **ローカライズ設定**

   * 居住地域の都市を選択します。
   * 選択に応じてタイムゾーンやキーボードレイアウトが自動設定されます（必要に応じて変更可能）。設定後、Nextをクリックします。
   
   .. image:: img/imager_custom_local.png
      :width: 90%

#. **ユーザー名とパスワードの設定**

   Raspberry Pi用のユーザーアカウントを作成します。
   
   .. image:: img/imager_custom_user.png
      :width: 90%

#. **Wi-Fi設定**

   * Wi-Fiの **SSID（ネットワーク名）** と **パスワード** を入力します。  
   * 初回起動時に自動的に接続されます。
   
   .. image:: img/imager_custom_wifi.png
      :width: 90%

#. **SSHの有効化（任意・推奨）**

   * SSHを有効にすると、PCからリモートログインが可能になります。  
   * ユーザー名とパスワード、またはSSHキーでログインできます。
   
   .. image:: img/imager_custom_ssh.png
      :width: 90%

#. **Raspberry Pi Connectの有効化（任意）**

   Raspberry Pi Connectを使用すると、ブラウザからデスクトップにアクセスできます。
   
   * **Raspberry Pi Connect** を有効にし、**OPEN RASPBERRY PI CONNECT** をクリックします。
   
     .. image:: img/imager_custom_connect.png
        :width: 90%

   * デフォルトブラウザでRaspberry Pi Connectのサイトが開きます。Raspberry Pi IDでログインするか、新規登録してください。

     .. image:: img/imager_custom_open.png
        :width: 90%

   * **New auth key** ページでワンタイム認証キーを作成します。
      
      * 組織に所属していない場合は、**Create auth key and launch Raspberry Pi Imager** を選択します。
      * 組織に所属している場合は、対象の組織を選択してからキーを作成し、Imagerを起動します。
      * キーの有効期限内にRaspberry Piの電源を入れ、インターネットに接続してください。
   
     .. image:: img/imager_custom_authkey.png
        :width: 90%
   
   * ブラウザからRaspberry Pi Imagerを開く確認が表示された場合は許可してください。

     * ImagerがRaspberry Pi Connectタブで開き、認証トークンが表示されます。
     * 自動でトークンが反映されない場合は、Raspberry Pi Connectページの **Having trouble?** セクションからトークンをコピーし、Imagerに手動で貼り付けます。

     .. image:: img/imager_custom_connect_token.png
        :width: 90%

-------------------

4. OSイメージの書き込み
-----------------------------

#. 設定内容を確認し、**WRITE** をクリックします。

   .. image:: img/imager_writing.png
      :width: 90%

#. すでにデータが存在する場合、デバイス内のすべてのデータが消去される旨の警告が表示されます。  
   正しいドライブであることを確認し、**I UNDERSTAND, ERASE AND WRITE** をクリックして続行します。

   .. image:: img/imager_erase.png
      :width: 90%

#. 書き込みおよび検証が完了するまで待ちます。完了すると **Write complete!** が表示され、設定内容の概要が表示されます。ストレージは自動的に取り外され、安全に抜き取ることができます。

   .. image:: img/imager_finish.png
        :width: 90%

#. microSDカードを取り外し、Raspberry Pi本体裏面のスロットに挿入します。これで新しいOSで起動する準備が整いました。

   .. image:: img/os_sd_to_pi.jpg
        :width: 70%