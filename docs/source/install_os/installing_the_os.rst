.. note::

    こんにちは、Facebook の SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts コミュニティへようこそ！  
    他の愛好者と一緒に、Raspberry Pi・Arduino・ESP32 の世界をさらに深く探求しましょう。  

    **Why Join?**

    - **Expert Support**: コミュニティやチームのサポートを受けて、購入後の問題や技術的な課題を解決できます。  
    - **Learn & Share**: ヒントやチュートリアルを共有し、スキルを高めましょう。  
    - **Exclusive Previews**: 新製品の発表や先行情報をいち早く入手できます。  
    - **Special Discounts**: 最新製品を特別価格で手に入れられます。  
    - **Festive Promotions and Giveaways**: プレゼント企画やシーズン限定キャンペーンに参加できます。  

    👉 探索と創造を始めませんか？ [|link_sf_facebook|] をクリックして今すぐ参加しましょう！


.. _install_os_sd:

2. OS のインストール
============================================================

Raspberry Pi を利用するには、まず Raspberry Pi OS を Micro SD カードにインストールする必要があります。  
このセクションでは、その手順をステップごとに解説します。  

**必要なコンポーネント**

* パーソナルコンピュータ（Windows、macOS、または Linux）  
* Micro SD カード（16GB 以上、Sandisk や Samsung など信頼できるブランド推奨）  
* Micro SD カードリーダー  

----

**1. Raspberry Pi Imager のインストール**

#. 公式 Raspberry Pi ダウンロードページを開きます: |link_rpi_imager|  

   お使いの OS（Windows、macOS、または Ubuntu）に合ったバージョンをダウンロードしてください。  

   .. image:: img/os_install_imager.png
       :align: center

#. インストール後、デスクトップアイコンをクリックするか、システムメニューで ``Raspberry Pi Imager`` を検索して起動します。  

   .. image:: img/os_open_imager.png
       :align: center

**2. OS を Micro SD カードに書き込む**

#. Micro SD カードをカードリーダーに挿入してコンピュータに接続します。重要なデータがある場合は必ずバックアップを取ってください。  

#. Imager でまず **Choose Device** をクリックし、使用する Raspberry Pi のモデルを選択します（例: Raspberry Pi 5、Raspberry Pi 4B、3B/3B+、Zero 2W）。  

   .. image:: img/os_choose_device.png
       :align: center

#. **Operating System** タブをクリックし、OS を選択します。  

   .. note::

      * **Raspberry Pi OS** の場合は、推奨されるシステムをそのまま選びます。  
      * **Ubuntu** を使う場合は、 **Other general-purpose OS** -> **Ubuntu** を選び、 **Ubuntu Desktop 24.04 LTS (64 bit)** または **Ubuntu Server 24.04 LTS (64 bit)** を選択します。  
      * **Kali Linux** を使う場合は、 **Other specific-purpose OS** を選び、対応するシステムを選択します。  
      * **Retropie** を使う場合は、 **Emulation and game OS** を選び、対応するシステムを選択します。  

   .. image:: img/os_choose_os.png
       :align: center

#. **Choose Storage** をクリックし、Micro SD カードを選択します。誤操作を防ぐため、他の USB ドライブは外しておきましょう。  

   .. note::

      ストレージデバイスの選択は慎重に行ってください。誤ったディスクを選ぶと重要なデータが消去される恐れがあります。  

   .. image:: img/os_choose_sd.png
       :align: center

#. **Next** をクリックし、続いて **EDIT SETTINGS** を選んで Raspberry Pi の設定を行います。  

   .. note::

        * モニター、キーボード、マウスを直接使用する場合は、高度な設定をスキップして **Yes** をクリックし、そのまま書き込みを開始できます。  
        * 事前設定できないシステムでは、**NEXT** をクリック後に「デバイス内にデータを保存するかどうか」が表示されます。バックアップを確認済みなら **Yes** を選択してください。  
        * ホスト名、WiFi、SSH の有効化を事前設定できるシステムでは、カスタム設定を適用するかどうかのポップアップが表示されます。**Yes** または **No** を選択するか、編集に戻ることもできます。  

   .. image:: img/os_enter_setting.png
       :align: center

----

**3. OS カスタマイズ設定**

* **Set Hostname**:  

  * 任意のホスト名を設定します。  
  * ネットワーク上では ``<hostname>.local`` としてアクセス可能です。  

  .. image:: img/os_set_hostname.png
      :align: center

* **Set Username & Password**:  

  * Pi にログインするためのユーザー名とパスワードを設定します。  
  * 旧バージョンと異なり、デフォルトのアカウントは用意されていません。  

  .. image:: img/os_set_username.png
      :align: center

* **Wi-Fi の設定**:  

  * Wi-Fi の **SSID（ネットワーク名）** と **パスワード** を入力します。  
  * **Wireless LAN country** を正しく設定してください。 |link_iso_code| （例: US, UK, CN）を使用し、間違えると Wi-Fi が動作しません。  

  .. image:: img/os_set_wifi.png
      :align: center

* **Enable SSH（任意だが推奨）**:  

  リモートから PC 経由でアクセスできるようになります。ユーザー名とパスワードでログインするか、公開鍵認証を設定することも可能です。  

  .. image:: img/os_enable_ssh.png
      :align: center

* **その他のオプション**:  

  「完了時に音を鳴らす」や「書き込み完了後にメディアを取り外す」などを有効にできます。  

  .. image:: img/os_options.png
      :align: center

----

**4. OS イメージの書き込み**

#. 設定が完了したら **Save** をクリックし、続けて **Yes** を押して適用します。  

   .. image:: img/os_click_yes.png
       :align: center

#. 既存データがある場合は、**Yes** をクリックして上書きを確認します。  

   .. image:: img/os_continue.png
       :align: center

#. 書き込みと検証が完了するまで数分待ちます。終了すると **Write Successful** が表示されます。  

   .. image:: img/os_finish.png
       :align: center


#. 最後に SD カードをリーダーから取り外し、Raspberry Pi 本体裏面のスロットに挿入します。これで Raspberry Pi は新しい OS で起動できるようになります。  

   .. image:: img/os_sd_to_pi.jpg
      :width: 500
      :align: center

