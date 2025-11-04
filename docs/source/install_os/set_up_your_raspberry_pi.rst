.. note::

    こんにちは、Facebook の SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts コミュニティへようこそ！  
    他の愛好者と一緒に、Raspberry Pi・Arduino・ESP32 の世界をさらに深く探求しましょう。  

    **なぜ参加するのか？**  

    - **専門的なサポート**: コミュニティやチームのサポートを受けて、購入後のトラブルや技術的な課題を解決できます。  
    - **学び＆共有**: ヒントやチュートリアルを共有し、スキルを磨きましょう。  
    - **限定プレビュー**: 新製品の発表や先行プレビューを誰よりも早くチェックできます。  
    - **特別割引**: 最新製品を特別割引価格で入手できます。  
    - **季節限定プロモーションとプレゼント企画**: 季節ごとのキャンペーンやプレゼント企画に参加できます。  

    👉 探索と創造を始めませんか？ [|link_sf_facebook|] をクリックして、今すぐ参加しましょう！

.. _setup_pi:

3. Raspberry Pi のセットアップ
===============================

プログラミングや制御を始めるには、まず Raspberry Pi にアクセスする必要があります。  
このセクションでは、画面・キーボード・マウスを使う方法と、モニターなしでリモート接続する「ヘッドレス」方式の 2 つの一般的な方法を紹介します。  

画面がある場合
-------------------------

**必要なコンポーネント**

* Raspberry Pi  
* 電源アダプター  
* Micro SD カード  
* HDMI ケーブル  
* ディスプレイ  
* マウス  
* キーボード  

#. microSD カードを Raspberry Pi に挿入します。  
#. マウス、キーボード、ディスプレイを接続します（Pi 4/5 の場合は電源入力に最も近い **HDMI0** を使用してください）。  
#. Raspberry Pi の電源を入れます。  
#. しばらくすると Raspberry Pi OS のデスクトップが表示され、ターミナルを開いてコマンドを入力できるようになります。  

    .. image:: img/bookwarm.png
        :align: center


画面がない場合（ヘッドレス設定）
-----------------------------------------

モニターを使用せずに、Raspberry Pi をリモートで設定・ログインすることができます。これが最も便利な方法です。  

**必要なコンポーネント**

* Raspberry Pi  
* 電源アダプター  
* Micro SD カード  
* 同じネットワークに接続された PC  

**ヒント**

* **無線LANの国（Wireless LAN country）** を ISO/IEC の 2 文字コード（例: ``US``、 ``UK``、 ``CN``）で正しく設定してください。設定しないと Wi-Fi が機能しません。  
* Raspberry Pi と PC が同じローカルネットワークに接続されていることを確認してください。  
* より安定した接続のため、可能であれば有線接続（Ethernet）を利用してください。  


**SSH で接続**

1. PC でターミナルを開きます（Windows: **PowerShell**、macOS/Linux: **Terminal**）そして以下を入力します:  

   .. code-block::

      ssh <username>@<hostname>.local
      # Example:
      ssh daisy@pi.local

#. あるいは、ルーターの DHCP/クライアントリストから Pi の IP アドレスを確認し、以下のように接続します:  

   .. code-block::

      ssh <username>@<IP>
      
      # Example:

      ssh daisy@192.xxx.xx.xx

#. 初回ログイン時にはセキュリティ警告が表示されます。 ``yes`` と入力して進めてください。  

#. Raspberry Pi Imager で設定したパスワードを入力します。（入力中に文字は表示されませんが、正常な挙動です。）  

   .. note::  
      パスワード入力時に文字が表示されないのはセキュリティ上の仕様です。落ち着いて正確に入力してください。  

#. 接続が完了すれば、Raspberry Pi をリモートで操作する準備が整います。  

   .. image:: img/ssh_login.png
      :align: center

**トラブルシューティング**

* **ssh: ホスト名を解決できません（ssh: Could not resolve hostname ...）**  

  * ホスト名が正しいか確認してください。  
  * それでも接続できない場合は ``<hostname>.local`` の代わりに IP アドレスを使用してください。  

* **sshという用語が認識されませんWindows（The term 'ssh' is not recognized... (Windows)**  

  * OpenSSH がインストールされていません。手動で OpenSSH を導入するか（:ref:`openssh_powershell` 参照）、またはサードパーティ製 SSH クライアントを使用してください（:ref:`login_windows` 参照）。  

* **アクセスが拒否されましたPermission denied (publickey,password)**  

  * Raspberry Pi Imager で設定したユーザー名とパスワードを使用しているか確認してください。  

* **接続が拒否されました（Connection refused）**  

  * 電源投入後、1〜2 分待ってから接続を試してください。  
  * Raspberry Pi Imager で SSH が有効化されているか確認してください。  

**グラフィカルアクセスの選択肢**

コマンドラインではなくグラフィカルインターフェイスを利用したい場合は、次の 2 つの方法があります:  

    .. image:: img/bookwarm.png
        :align: center

* :ref:`remote_desktop`: **VNC (Virtual Network Computing)** を有効にすると、Pi のデスクトップをそのまま操作できます。  
* |link_rpi_connect|: **Raspberry Pi Connect** を使えば、ブラウザから安全にリモートアクセスできます。  

これで、モニターを使わずに SSH でコマンドライン操作を行ったり、VNC や Raspberry Pi Connect でデスクトップ環境を操作したりすることが可能になります。  
