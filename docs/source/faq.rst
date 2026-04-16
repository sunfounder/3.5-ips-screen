.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

FAQ
===========================

Kompatible Raspberry-Pi-Modelle
-------------------------------------------

Derzeit ist das 3,5-Zoll-Display nur mit Raspberry Pi 4 und Raspberry Pi 5 kompatibel. Für Raspberry Pi 3B, 3B+ und Zero 2W wird die Verwendung mit diesem Display nicht empfohlen, da die Installation des Touchscreen-Treibers zu Fehlfunktionen führen kann.

Funktioniert dieses Display mit Ubuntu, Kali Linux oder RetroPie?
-----------------------------------------------------------------

Ja, jedoch nur mit bestimmten OS-Versionen.  
Wenn Sie eine nicht unterstützte Version installieren, funktioniert das Display möglicherweise nach der Treiberinstallation nicht.

Unterstützte Systeme:

* **Raspberry Pi OS**

  - Trixie Desktop (64-bit) (veröffentlicht: 04.12.2025)
  - Bookworm Desktop (64-bit) (veröffentlicht: 24.11.2025, 13.05.2025, 06.05.2025)

    Nach der Treiberinstallation unter Bookworm müssen Sie ``startx`` ausführen, um die Desktop-Oberfläche zu starten.

* **Ubuntu**

  - |link_ubuntu_2404| (nur für Raspberry Pi 4)

* **Kali Linux**

  - |link_kali_202503|

* **RetroPie**

  - |link_retropie| (nur für Raspberry Pi 4)

Warum bleibt der Bildschirm nach dem Einschalten schwarz oder weiß?
--------------------------------------------------------------------

* Stellen Sie sicher, dass der richtige Treiber installiert ist. Siehe :ref:`install_driver`.
* Prüfen Sie, ob Ihr Betriebssystem kompatibel ist. Siehe :ref:`install_os`.
* Überprüfen Sie, ob das Display korrekt mit den GPIO-Pins verbunden ist.

Kann ich das 3,5'' IPS-Display zusammen mit einem HDMI-Monitor verwenden?
--------------------------------------------------------------------------------

Nein. Nach der Installation des Treibers für das 3,5''-IPS-Display wird empfohlen, den HDMI-Monitor zu trennen.

Wenn der HDMI-Monitor weiterhin angeschlossen bleibt, kann es zu einem schwarzen Bildschirm oder fehlender Anzeige kommen.

Anzeige auf HDMI wiederherstellen
----------------------------------------------

#. Wenn Sie nur den Treiber für das 3,5''-Display installiert und keine weiteren Änderungen an der config.txt vorgenommen haben, können Sie folgenden Befehl ausführen:

   .. code-block:: bash

      cd LCD-show
      sudo ./system_restore.sh

   Nach der Wiederherstellung funktioniert das 3,5''-Display nicht mehr und der Treiber muss erneut installiert werden. Diese Methode eignet sich für ein sauberes oder frisch eingerichtetes System.

#. Wenn Sie zusätzlich Änderungen an der config.txt vorgenommen haben, ist die sicherste Methode die manuelle Bearbeitung:

   * Öffnen Sie die Datei config.txt mit folgendem Befehl:

     .. code-block:: bash

        sudo nano /boot/config.txt

   * Scrollen Sie nach unten und kommentieren Sie die vom 3,5''-Displaytreiber hinzugefügten Einträge aus:

     .. code-block:: bash

        [all]
        hdmi_force_hotplug=1
        dtparam=i2c_arm=on
        dtparam=spi=on
        enable_uart=1
        dtoverlay=mhs35ips:rotate=90
        hdmi_group=2
        hdmi_mode=1
        hdmi_mode=87
        hdmi_cvt 480 320 60 6 0 0 0
        hdmi_drive=2

   * Drücken Sie Ctrl+X, dann Y und Enter, um die Datei zu speichern und zu schließen.

   * Starten Sie anschließend den Raspberry Pi neu. Die HDMI-Anzeige funktioniert wieder.

   * Wenn Sie das 3,5''-Display wieder verwenden möchten, entfernen Sie einfach die Kommentarzeichen vor den oben genannten Zeilen.
   
Was tun bei ``git not found`` oder Netzwerkfehlern während der Installation?
--------------------------------------------------------------------------------------

Stellen Sie sicher, dass Ihr Raspberry Pi mit dem Internet verbunden ist.

Falls Git nicht installiert ist, führen Sie folgende Befehle aus:

* ``sudo apt update``
* ``sudo apt install git``

Versuchen Sie danach die Installation erneut.

Warum ist die Bildschirmausrichtung falsch?
--------------------------------------------------------

Sie können die Ausrichtung von Bildschirm und Touchfunktion mit den folgenden Befehlen korrigieren:

* ``cd LCD-show/``   (passen Sie den Pfad je nach verwendetem Betriebssystem an)
* ``sudo ./rotate.sh 90``

Ersetzen Sie ``90`` bei Bedarf durch ``0``, ``180`` oder ``270``.



Warum läuft der Lüfter ständig? Kann er per Software gesteuert werden?
------------------------------------------------------------------------------------------

Der Lüfteranschluss liefert dauerhaft 5 V und unterstützt keine Softwaresteuerung.  
Der Lüfter läuft daher immer, sobald er angeschlossen ist.

Wie hoch ist der Betriebstemperaturbereich?
--------------------------------------------------------

Der unterstützte Betriebstemperaturbereich liegt bei **-20 °C bis 60 °C**.  
Vermeiden Sie Temperaturen außerhalb dieses Bereichs, um Schäden oder eine verkürzte Lebensdauer zu verhindern.

Probleme beim Fernzugriff
-------------------------

* **ssh: Could not resolve hostname ...**

  * Prüfen Sie, ob der Hostname korrekt ist.
  * Falls es weiterhin nicht funktioniert, verwenden Sie statt ``<hostname>.local`` die IP-Adresse Ihres Raspberry Pi.

* **The term 'ssh' is not recognized... (Windows)**

  * OpenSSH ist nicht installiert. Installieren Sie es manuell (siehe :ref:`openssh_powershell`),  
    oder verwenden Sie einen SSH-Client eines Drittanbieters (siehe :ref:`login_windows`).

* **Permission denied (publickey,password)**

  * Stellen Sie sicher, dass Sie den richtigen Benutzernamen und das richtige Passwort verwenden, die Sie im Raspberry Pi Imager festgelegt haben.

* **Connection refused**

  * Warten Sie nach dem Einschalten 1–2 Minuten.
  * Stellen Sie sicher, dass SSH im Raspberry Pi Imager aktiviert wurde.