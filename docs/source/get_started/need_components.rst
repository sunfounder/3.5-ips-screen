.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

1. そのほかに必要なもの
===============================

本スクリーンを使用する前に、必要なハードウェアを準備しましょう。

必須コンポーネント
------------------------------

* **Raspberry Pi**

  * **対応モデル**：Raspberry Pi 5、Raspberry Pi 4 Model B
  * 上記以外のモデルは対応していません。

  .. image:: img/need_pi.jpg

* **電源アダプター**

  Raspberry Piのモデルによって必要な電源仕様が異なります。  
  安定した動作のため、公式電源アダプターの使用を推奨します。

  * **Raspberry Pi 5**：推奨：**5V 5A USB-C電源（公式27W PSU）**  
    USB-C Power Delivery（PD）対応充電器でも、十分な電流を供給できるものであれば使用可能です。

  * **Raspberry Pi 4 Model B**：推奨：**5V 3A USB-C電源（公式15W PSU）**  
    USB-C PDまたはQC 2.0対応の急速充電器も使用可能です。

  .. image:: img/need_power.png
    :width: 400

* **microSDカード**

  Raspberry Piには内蔵ストレージがありません。  
  **microSDカード** にOSとデータを保存して起動します。

  .. image:: img/need_sd.jpg
    :width: 200

  * 最小容量： **16GB**
  * 推奨容量： **32GB以上** （パフォーマンスと安定性向上のため）
  * 推奨ブランド： **SanDisk**、 **Samsung**

オプションコンポーネント
------------------------

必須ではありませんが、以下の周辺機器があるとセットアップやトラブルシューティングが容易になります：

* **モニター（HDMI対応ディスプレイまたはテレビ）**

  初心者の方には、HDMI入力に対応したディスプレイの使用を強く推奨します。  
  システム設定やGUI操作が簡単になります。

  .. image:: img/need_screen.png
    :width: 400

* **Micro HDMIケーブル**

  * Raspberry Pi 4BおよびRaspberry Pi 5は、ディスプレイ接続に **Micro HDMIケーブル** が必要です。  
  * **HDMI0ポート** （USB-C電源端子に最も近いポート）の使用を推奨します。

  .. image:: img/need_hdmi.png
    :width: 400

* **キーボードとマウス**

  * 初期セットアップ時に非常に便利です。  
  * 後からSSHやVNCでのリモート操作に切り替えることも可能ですが、初心者にはUSBまたはワイヤレスのキーボードとマウスの使用を推奨します。

  .. image:: img/need_keyboard_mouse.png
    :width: 500