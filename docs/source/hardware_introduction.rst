.. note::

    こんにちは、Facebook の SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts コミュニティへようこそ！  
    他の愛好者と一緒に Raspberry Pi、Arduino、ESP32 の世界をさらに深く探求しましょう。  

    **Why Join?**

    - **Expert Support**: 購入後の問題や技術的なトラブルを、コミュニティやチームのサポートで解決できます。  
    - **Learn & Share**: ヒントやチュートリアルを共有してスキルを磨きましょう。  
    - **Exclusive Previews**: 新製品の発表や先行情報をいち早く入手できます。  
    - **Special Discounts**: 最新製品を特別割引で購入できます。  
    - **Festive Promotions and Giveaways**: キャンペーンやプレゼント企画に参加できます。  

    👉 さあ、一緒に学び、創造を楽しみましょう！ [|link_sf_facebook|] をクリックして今すぐ参加してください！

Hardware Description
===========================

**Parameters**

.. list-table::
    :header-rows: 1

    * - Parameter
      - Description
    * - Screen Size
      - 3.5 インチ
    * - LCD Type
      - IPS
    * - Viewing Angle
      - 全視野角
    * - Module Interface
      - SPI（最大 125MHz SPI 入力対応）
    * - Resolution
      - 320×480（ピクセル）
    * - Number of Pins
      - 40 ピン（Raspberry Pi と同じ）
    * - Colors
      - 65K
    * - Touch Screen Controller
      - XPT2046
    * - LCD Driver IC
      - ST7796U
    * - Backlight
      - LED
    * - Power Consumption
      - 0.16A × 5V
    * - Working Temperature (℃)
      - -20 ～ 60
    * - Active Area
      - 48.96 × 73.44 (mm)
    * - Module PCB Size
      - 85.42 × 55.60 (mm)
    * - Package Size
      - 132 × 96 × 40 (mm)
    * - Product Weight (Including Package)
      - 93.8 g

**Interface Definition**

以下は 3.5 インチ IPS スクリーンのピン配置図です。実際に接続されているのは最初の 26 ピンのみで、27〜40 ピンは未接続です。これらは最新の 40 ピン Raspberry Pi モデルとの互換性を保つため、また誤挿入を防ぐために用意されています。

.. image:: img/3.5_ips_pins.png
  :width: 500
  :align: center

.. list-table:: 
    :header-rows: 1

    * - PIN NO.
      - SYMBOL
      - DESCRIPTION
    * - 1, 17
      - 3.3V
      - 電源入力（3.3V）
    * - 2, 4
      - 5V
      - 電源入力（5V）
    * - 3, 5, 7, 8, 10, 12, 13, 15, 16, 27~40
      - NC
      - 未接続
    * - 6, 9, 14, 20, 25
      - GND
      - グランド
    * - 11
      - TP_IRQ
      - タッチパネル割り込み信号、押下時に Low
    * - 18
      - LCD_RS
      - LCD レジスタ選択信号（Low: コマンド、High: データ）
    * - 19
      - LCD_SI / TP_SI
      - LCD 表示/タッチパネル用 SPI データ入力
    * - 21
      - TP_SO
      - タッチパネルからの SPI データ出力
    * - 22
      - RST
      - リセット信号、Low で有効
    * - 23
      - LCD_SCK / TP_SCK
      - LCD 表示/タッチパネル用 SPI クロック信号
    * - 24
      - LCD_CS
      - LCD チップセレクト信号、Low で有効
    * - 26
      - TP_CS
      - タッチパネルチップセレクト信号、Low で有効


**Fan Pins**

スクリーン背面には外部ファンを接続できる 2 つのファン用ピンが搭載されています。ただし、一度接続するとファンは常時回転し、コードによる制御はできません。

.. image:: img/3.5_ips_fan_pins.png
  :width: 400
  :align: center
  
