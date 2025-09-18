.. note::

    Hallo und willkommen in der SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasten-Community auf Facebook! Tauche gemeinsam mit anderen Technikbegeisterten tiefer in die Welt von Raspberry Pi, Arduino und ESP32 ein.  

    **Why Join?**

    - **Expert Support**: Löse Probleme nach dem Kauf sowie technische Herausforderungen mit Unterstützung unserer Community und unseres Teams.  
    - **Learn & Share**: Teile Tipps und Tutorials, um deine Fähigkeiten zu erweitern.  
    - **Exclusive Previews**: Erhalte frühzeitigen Zugang zu neuen Produktankündigungen und exklusiven Einblicken.  
    - **Special Discounts**: Profitiere von exklusiven Rabatten auf unsere neuesten Produkte.  
    - **Festive Promotions and Giveaways**: Nimm an Gewinnspielen und saisonalen Aktionen teil.  

    👉 Bereit, mit uns Neues zu entdecken und zu erschaffen? Klicke auf [|link_sf_facebook|] und werde noch heute Mitglied!  

Hardware Description
===========================

**Parameters**

.. list-table::
    :header-rows: 1

    * - Parameter
      - Beschreibung
    * - Bildschirmgröße
      - 3,5 Zoll
    * - LCD-Typ
      - IPS
    * - Blickwinkel
      - Voller Betrachtungswinkel
    * - Modulschnittstelle
      - SPI (unterstützt bis zu 125 MHz SPI-Eingang)
    * - Auflösung
      - 320×480 (Pixel)
    * - Anzahl Pins
      - 40-Pin (identisch zum Raspberry Pi)
    * - Farben
      - 65K
    * - Touchscreen-Controller
      - XPT2046
    * - LCD-Treiber-IC
      - ST7796U
    * - Hintergrundbeleuchtung
      - LED
    * - Stromverbrauch
      - 0,16 A × 5 V
    * - Betriebstemperatur (℃)
      - -20 ~ 60
    * - Aktiver Bereich
      - 48,96 × 73,44 (mm)
    * - Modul-PCB-Größe
      - 85,42 × 55,60 (mm)
    * - Verpackungsgröße
      - 132 × 96 × 40 (mm)
    * - Produktgewicht (inkl. Verpackung)
      - 93,8 g

**Interface Definition**

Hier ist das Pinout-Diagramm für den 3,5-Zoll-IPS-Bildschirm. Tatsächlich sind nur die ersten 26 Pins belegt. Pins 27–40 sind nicht verbunden; sie dienen lediglich der Kompatibilität mit aktuellen 40-Pin-Raspberry-Pi-Modellen und verringern die Gefahr einer falschen Ausrichtung beim Einsetzen.

.. image:: img/3.5_ips_pins.png
  :width: 500
  :align: center

.. list-table:: 
    :header-rows: 1

    * - PIN NR.
      - SYMBOL
      - BESCHREIBUNG
    * - 1, 17
      - 3.3V
      - Stromeingang (3,3 V)
    * - 2, 4
      - 5V
      - Stromeingang (5 V)
    * - 3, 5, 7, 8, 10, 12, 13, 15, 16, 27~40
      - NC
      - Nicht verbunden
    * - 6, 9, 14, 20, 25
      - GND
      - Masseanschluss
    * - 11
      - TP_IRQ
      - Touchpanel-Interruptsignal, aktiv low bei Berührung
    * - 18
      - LCD_RS
      - LCD-Registerauswahl (low: Befehl, high: Daten)
    * - 19
      - LCD_SI / TP_SI
      - SPI-Dateneingang für LCD / Touchpanel
    * - 21
      - TP_SO
      - SPI-Datenausgang vom Touchpanel
    * - 22
      - RST
      - Reset-Signal, aktiv low
    * - 23
      - LCD_SCK / TP_SCK
      - SPI-Taktsignal für LCD / Touchpanel
    * - 24
      - LCD_CS
      - LCD-Chip-Select, aktiv low
    * - 26
      - TP_CS
      - Touchpanel-Chip-Select, aktiv low


**Fan Pins**

Auf der Rückseite des Bildschirms befinden sich zwei Lüfterpins, an die ein externer Lüfter angeschlossen werden kann. Sobald der Lüfter angeschlossen ist, läuft er jedoch dauerhaft und lässt sich nicht per Code steuern.

.. image:: img/3.5_ips_fan_pins.png
  :width: 400
  :align: center

