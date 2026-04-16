.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

Hardwarebeschreibung
===========================

**Technische Daten**

.. list-table::
    :header-rows: 1

    * - Parameter
      - Beschreibung
    * - Displaygröße
      - 3,5 Zoll
    * - LCD-Typ
      - IPS
    * - Blickwinkel
      - Voller Betrachtungswinkel
    * - Modulschnittstelle
      - SPI (unterstützt SPI-Eingang bis zu 125 MHz)
    * - Auflösung
      - 320 × 480 (Pixel)
    * - Anzahl der Pins
      - 40-polig (wie beim Raspberry Pi)
    * - Farben
      - 65K
    * - Touchscreen-Controller
      - XPT2046
    * - LCD-Treiber-IC
      - ST7796U
    * - Hintergrundbeleuchtung
      - LED
    * - Leistungsaufnahme
      - 0,16 A × 5 V
    * - Betriebstemperatur (℃)
      - -20 bis 60
    * - Aktive Fläche
      - 48,96 × 73,44 (mm)
    * - PCB-Größe des Moduls
      - 85,42 × 55,60 (mm)
    * - Verpackungsgröße
      - 132 × 96 × 40 (mm)
    * - Produktgewicht (inklusive Verpackung)
      - 93,8 g

**Schnittstellenbelegung**

Hier sehen Sie das Pinbelegungsdiagramm des 3,5-Zoll-IPS-Displays. Tatsächlich sind nur die ersten 26 Pins verbunden. Die Pins 27–40 sind nicht belegt; sie dienen lediglich der Kompatibilität mit den aktuellen 40-poligen Raspberry-Pi-Modellen und verringern das Risiko eines falschen Aufsteckens.

.. image:: img/3.5_ips_pins.png
  :width: 500
  :align: center

.. list-table:: 
    :header-rows: 1

    * - PIN-Nr.
      - Symbol
      - Beschreibung
    * - 1, 17
      - 3.3V
      - Versorgungsspannungseingang (3,3 V)
    * - 2, 4
      - 5V
      - Versorgungsspannungseingang (5 V)
    * - 3, 5, 7, 8, 10, 12, 13, 15, 16, 27~40
      - NC
      - Nicht verbunden
    * - 6, 9, 14, 20, 25
      - GND
      - Masse
    * - 11
      - TP_IRQ
      - Interruptsignal des Touchpanels, aktiv low bei Berührung
    * - 18
      - LCD_RS
      - Registerauswahlsignal des LCD (low: Befehl, high: Daten)
    * - 19
      - LCD_SI / TP_SI
      - SPI-Dateneingang für LCD-Display / Touchpanel
    * - 21
      - TP_SO
      - SPI-Datenausgang des Touchpanels
    * - 22
      - RST
      - Reset-Signal, aktiv low
    * - 23
      - LCD_SCK / TP_SCK
      - SPI-Taktsignal für LCD-Display / Touchpanel
    * - 24
      - LCD_CS
      - Chip-Select-Signal des LCD, aktiv low
    * - 26
      - TP_CS
      - Chip-Select-Signal des Touchpanels, aktiv low


**Lüfter-Pins**

Auf der Rückseite des Displays befinden sich zwei Lüfter-Pins, an die ein externer Lüfter angeschlossen werden kann. Sobald der Lüfter angeschlossen ist, läuft er jedoch dauerhaft und kann nicht per Software gesteuert werden.

.. image:: img/3.5_ips_fan_pins.png
  :width: 400
  :align: center