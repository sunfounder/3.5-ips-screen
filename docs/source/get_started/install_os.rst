.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_os:

2. オペレーティングシステムのインストール
===========================================

このセクションでは、Raspberry Piに対応するオペレーティングシステムをインストールする手順を説明します。  
使用するRaspberry Piのモデルや用途に応じて、対応するシステムを選択してください。

.. note::

    現在、この3.5インチディスプレイはRaspberry Pi 4およびRaspberry Pi 5のみに対応しています。Raspberry Pi 3B、3B+、およびZero 2Wでの使用は推奨されていません。タッチスクリーンドライバーのインストールにより、正常に動作しなくなる可能性があります。

    * **Raspberry Pi OS** の場合：

      - Trixie Desktop（64-bit）（リリース日：2025-12-04）
      - Bookworm Desktop（64-bit）（リリース日：2025-11-24、2025-05-13、2025-05-06）

        Bookwormにドライバーをインストールした後は、``startx`` を実行してデスクトップ環境を起動する必要があります。

    * **Ubuntu** の場合：

      - |link_ubuntu_2404| （Raspberry Pi 4のみ対応）

    * **Kali Linux** の場合：

      - |link_kali_202503|

    * **RetroPie** の場合：

      - |link_retropie| （Raspberry Pi 4のみ対応）

.. toctree::
    :maxdepth: 1

    install_rpi_os
    install_other_os