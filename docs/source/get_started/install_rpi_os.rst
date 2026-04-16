.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message
   
.. _install_os:

Installation von Raspberry Pi OS
===================================

Bevor Sie Ihren Raspberry Pi verwenden können, müssen Sie **Raspberry Pi OS** auf eine microSD-Karte installieren.  
Dieser Abschnitt bietet eine einfache Schritt-für-Schritt-Anleitung mit dem **Raspberry Pi Imager**, die besonders für Einsteiger geeignet ist.

Unterstützte Modelle und OS-Versionen
-------------------------------------

.. warning::

   * Diese Anleitung gilt nur für die unten aufgeführten Modelle und OS-Versionen.
   * Die Verwendung anderer Versionen kann dazu führen, dass das 3,5''-IPS-Display nach der Treiberinstallation nicht korrekt funktioniert.

* **Unterstützte Modelle**:

  - Raspberry Pi 5
  - Raspberry Pi 4 Model B

* **Getestete kompatible OS-Versionen**:

  - **Trixie Desktop (64-bit)** (veröffentlicht: 04.12.2025)
  - **Bookworm Desktop (64-bit)** (veröffentlicht: 24.11.2025, |link_bookwarm_250513|)

    Nach der Treiberinstallation unter Bookworm müssen Sie ``startx`` ausführen, um die Desktop-Oberfläche zu starten.

Benötigte Komponenten
------------------------------

* Ein Computer (Windows, macOS oder Linux)
* Eine microSD-Karte (16 GB oder größer; empfohlen: SanDisk, Samsung)
* Ein microSD-Kartenleser

-------------------

1. Raspberry Pi Imager installieren
-------------------------------------------

#. Besuchen Sie die offizielle Download-Seite des Raspberry Pi Imager: |link_rpi_imager| und laden Sie die passende Version für Ihr Betriebssystem herunter.

   .. image:: img/imager_download.png
      :width: 70%

#. Folgen Sie den Installationsanweisungen (Sprache, Installationspfad, Bestätigung). Starten Sie anschließend den **Raspberry Pi Imager**.

   .. image:: img/imager_install.png
      :width: 90%

--------------------------------------

2. Betriebssystem auf die microSD-Karte schreiben
------------------------------------------------------------------

#. Stecken Sie die microSD-Karte mit einem Kartenleser in Ihren Computer. Sichern Sie zuvor alle wichtigen Daten.

   .. image:: img/insert_sd.png
      :width: 90%

#. Öffnen Sie den Raspberry Pi Imager und wählen Sie Ihr Gerät aus (z. B. Raspberry Pi 5 oder Raspberry Pi 4).

   .. image:: img/imager_device.png
      :width: 90%

#. Klicken Sie auf **OS** und wählen Sie das System:

   * Für **Trixie** wählen Sie einfach die empfohlene Version aus.
   * Für **Bookworm** gehen Sie zu: **Raspberry Pi OS (Other) → Raspberry Pi OS (Legacy, 64-bit)**

   .. image:: img/imager_os.png
      :width: 90%

4. Wählen Sie im Bereich **Storage** Ihre microSD-Karte aus. 

   .. image:: img/imager_storage.png
      :width: 90%

5. Klicken Sie auf **Next**, um mit dem Anpassungsschritt fortzufahren.

   .. note::

      * Wenn Sie Monitor, Tastatur und Maus direkt an den Raspberry Pi anschließen, können Sie **SKIP CUSTOMISATION** wählen.  
      * Wenn Sie den Raspberry Pi *headless* einrichten möchten (Fernzugriff über WLAN), müssen Sie die Anpassungseinstellungen durchführen.

   .. image:: img/imager_custom_skip.png
      :width: 90%

-------------------

.. _imager_custom:

3. Anpassung der Betriebssystemeinstellungen
--------------------------------------------------------------

#. **Hostname festlegen**

   * Geben Sie Ihrem Raspberry Pi einen eindeutigen Hostnamen.  
   * Sie können später über ``hostname.local`` darauf zugreifen.

   .. image:: img/imager_custom_hostname.png
      :width: 90%

#. **Regionale Einstellungen festlegen**

   * Wählen Sie Ihre Hauptstadt aus.
   * Der Imager ergänzt automatisch Zeitzone und Tastaturlayout basierend auf Ihrer Auswahl. Sie können diese bei Bedarf anpassen. Klicken Sie anschließend auf **Next**.
   
   .. image:: img/imager_custom_local.png
      :width: 90%

#. **Benutzername und Passwort festlegen**

   Erstellen Sie ein Benutzerkonto für Ihren Raspberry Pi.
   
   .. image:: img/imager_custom_user.png
      :width: 90%

#. **WLAN konfigurieren**

   * Geben Sie Ihre WLAN-**SSID** (Netzwerkname) und das **Passwort** ein.  
   * Ihr Raspberry Pi verbindet sich beim ersten Start automatisch mit dem Netzwerk.
   
   .. image:: img/imager_custom_wifi.png
      :width: 90%

#. **SSH aktivieren (Optional, empfohlen)**

   * Mit aktiviertem SSH können Sie sich remote von Ihrem Computer aus anmelden.  
   * Sie können sich mit Benutzername/Passwort anmelden oder SSH-Schlüssel verwenden.
   
   .. image:: img/imager_custom_ssh.png
      :width: 90%

#. **Raspberry Pi Connect aktivieren (Optional)**

   Mit Raspberry Pi Connect können Sie über einen Webbrowser auf die Desktop-Oberfläche Ihres Raspberry Pi zugreifen.
   
   * Aktivieren Sie **Raspberry Pi Connect** und klicken Sie anschließend auf **OPEN RASPBERRY PI CONNECT**.
   
     .. image:: img/imager_custom_connect.png
        :width: 90%

   * Die Raspberry Pi Connect-Website öffnet sich in Ihrem Standardbrowser. Melden Sie sich mit Ihrem Raspberry Pi ID-Konto an oder registrieren Sie sich, falls Sie noch keines haben.

     .. image:: img/imager_custom_open.png
        :width: 90%

   * Auf der Seite **New auth key** erstellen Sie einen einmaligen Authentifizierungsschlüssel. 
      
      * Wenn Ihr Raspberry Pi ID-Konto keiner Organisation angehört, wählen Sie **Create auth key and launch Raspberry Pi Imager**.
      * Wenn Sie zu einer oder mehreren Organisationen gehören, wählen Sie eine aus und erstellen Sie anschließend den Schlüssel.
      * Stellen Sie sicher, dass Ihr Raspberry Pi eingeschaltet und mit dem Internet verbunden ist, bevor der Schlüssel abläuft.
   
     .. image:: img/imager_custom_authkey.png
        :width: 90%
   
   * Ihr Browser fragt möglicherweise, ob der Raspberry Pi Imager geöffnet werden soll – erlauben Sie dies.

     * Der Imager wird im Tab für Raspberry Pi Connect geöffnet und zeigt das Authentifizierungstoken an.
     * Falls das Token nicht automatisch übernommen wird, öffnen Sie den Abschnitt **Having trouble?** auf der Raspberry Pi Connect-Seite, kopieren Sie das Token und fügen Sie es manuell in den Imager ein.

     .. image:: img/imager_custom_connect_token.png
        :width: 90%

-------------------

4. OS-Image schreiben
-----------------------------

#. Überprüfen Sie alle Einstellungen und klicken Sie auf **WRITE**.

   .. image:: img/imager_writing.png
      :width: 90%

#. Falls sich bereits Daten auf der Karte befinden, zeigt der Raspberry Pi Imager eine Warnung an, dass alle Daten gelöscht werden. Vergewissern Sie sich, dass Sie das richtige Laufwerk ausgewählt haben, und klicken Sie dann auf **I UNDERSTAND, ERASE AND WRITE**, um fortzufahren.

   .. image:: img/imager_erase.png
      :width: 90%

#. Warten Sie, bis der Schreib- und Verifizierungsprozess abgeschlossen ist. Anschließend zeigt der Raspberry Pi Imager **Write complete!** sowie eine Zusammenfassung Ihrer Einstellungen an. Das Speichermedium wird automatisch ausgeworfen, sodass Sie es sicher entfernen können.

   .. image:: img/imager_finish.png
        :width: 90%

#. Entfernen Sie die microSD-Karte und setzen Sie sie in den Steckplatz auf der Unterseite Ihres Raspberry Pi ein.  
   Ihr Raspberry Pi ist nun bereit, mit dem neuen Betriebssystem zu starten!

   .. image:: img/os_sd_to_pi.jpg
        :width: 70%
