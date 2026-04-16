.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

1. Was wird noch benötigt?
===============================

Bevor wir dieses Display verwenden, bereiten wir zunächst die grundlegende Hardware vor.

Benötigte Komponenten
------------------------------

* **Raspberry Pi**

  * **Kompatible Modelle**: Raspberry Pi 5, Raspberry Pi 4 Model B
  * Andere Raspberry-Pi-Modelle werden nicht unterstützt.

  .. image:: img/need_pi.jpg

* **Netzteil**

  Verschiedene Raspberry-Pi-Modelle benötigen unterschiedliche Netzteile.  
  Für maximale Stabilität wird empfohlen, ein offizielles Netzteil zu verwenden:

  * **Raspberry Pi 5**: Empfohlen: **5V 5A USB-C-Netzteil** (offizielles 27W-Netzteil). Alternativ kann ein USB-C-Power-Delivery-(PD)-Ladegerät verwendet werden, sofern es ausreichend Strom liefert.

  * **Raspberry Pi 4 Model B**: Empfohlen: **5V 3A USB-C-Netzteil** (offizielles 15W-Netzteil). Alternativ kann ein USB-C-PD- oder QC-2.0-Schnellladegerät verwendet werden.

  .. image:: img/need_power.png
    :width: 400

* **MicroSD-Karte**

  Der Raspberry Pi verfügt über keinen internen Speicher. Er startet und speichert alle Daten auf einer **MicroSD-Karte**.

  .. image:: img/need_sd.jpg
    :width: 200

  * Minimum: **16 GB**
  * Empfohlen: **32 GB** oder mehr für bessere Leistung und Stabilität
  * Empfohlene Marken: **SanDisk**, **Samsung**

Optionale Komponenten
------------------------

Diese Komponenten sind nicht zwingend erforderlich, verbessern jedoch Einrichtung und Fehlersuche erheblich:

* **Monitor (HDMI oder Fernseher)**

  Für Einsteiger wird ein Display mit HDMI-Eingang dringend empfohlen. Dadurch wird die Einrichtung des Systems und die Nutzung grafischer Programme deutlich erleichtert.

  .. image:: img/need_screen.png
    :width: 400

* **Micro-HDMI-Kabel**

  * Raspberry Pi 4B und Raspberry Pi 5 benötigen ein **Micro-HDMI-Kabel**, um mit einem Display verbunden zu werden.  
  * Es wird empfohlen, den **HDMI0-Anschluss** (der dem USB-C-Stromanschluss am nächsten liegt) zu verwenden.

  .. image:: img/need_hdmi.png
    :width: 400

* **Tastatur und Maus**

  * Diese sind besonders bei der ersten Einrichtung des Betriebssystems sehr hilfreich.  
  * Später können Sie auf Fernzugriff (SSH/VNC) umsteigen, aber für Einsteiger wird eine einfache USB- oder kabellose Tastatur und Maus dringend empfohlen.

  .. image:: img/need_keyboard_mouse.png
    :width: 500