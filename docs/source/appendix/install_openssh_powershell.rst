.. note::

    こんにちは、Facebook の SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts コミュニティへようこそ！  
    他の愛好者と共に、Raspberry Pi・Arduino・ESP32 の世界をさらに深く探求しましょう。  

    **Why Join?**

    - **Expert Support**: コミュニティやチームのサポートを受けて、購入後のトラブルや技術的な課題を解決できます。  
    - **Learn & Share**: ヒントやチュートリアルを共有し、スキルを向上させましょう。  
    - **Exclusive Previews**: 新製品の発表や先行プレビューを誰よりも早く確認できます。  
    - **Special Discounts**: 最新製品を特別価格で入手できます。  
    - **Festive Promotions and Giveaways**: 季節ごとのキャンペーンやプレゼント企画に参加できます。  

    👉 探索と創造を始めませんか？ [|link_sf_facebook|] をクリックして今すぐ参加しましょう！

.. _openssh_powershell:

Install OpenSSH via Powershell
===================================

``ssh <username>@<hostname>.local`` （または ``ssh <username>@<IP address>``）を使用して Raspberry Pi に接続しようとした際、次のエラーメッセージが表示される場合があります。

    .. code-block::

        ssh: The term 'ssh' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the
        spelling of the name, or if a path was included, verify that the path is correct and try again.


これは、使用しているコンピュータのシステムが古く、 `OpenSSH <https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui>`_ がプリインストールされていないことを意味します。以下の手順に従って手動でインストールしてください。

#. Windows デスクトップの検索ボックスに ``powershell`` と入力し、 ``Windows PowerShell`` を右クリックして表示されるメニューから ``管理者として実行`` を選択します。

    .. image:: img/powershell_ssh.png
        :align: center

#. 次のコマンドを入力して ``OpenSSH.Client`` をインストールします。

    .. code-block::

        Add-WindowsCapability -Online -Name OpenSSH.Client~~~~0.0.1.0

#. インストール完了後、以下の出力が表示されます。

    .. code-block::

        Path          :
        Online        : True
        RestartNeeded : False

#. 続いて、次のコマンドを使用してインストールが正しく行われたかを確認します。

    .. code-block::

        Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'

#. これで ``OpenSSH.Client`` が正常にインストールされたことが確認できます。

    .. code-block::

        Name  : OpenSSH.Client~~~~0.0.1.0
        State : Installed

        Name  : OpenSSH.Server~~~~0.0.1.0
        State : NotPresent

    .. warning:: 
        上記の表示が出ない場合は、Windows システムが依然として古いため、:ref:`login_windows` のようなサードパーティ製 SSH ツールの使用を推奨します。

#. PowerShell を再起動し、再度管理者として実行してください。これで ``ssh`` コマンドを使って Raspberry Pi にログインできるようになります。プロンプトが表示されたら、事前に設定したパスワードを入力してください。

    .. image:: img/powershell_login.png