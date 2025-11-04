.. note::

    Hallo und willkommen in der SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasten-Community auf Facebook! Tauche gemeinsam mit anderen Technikbegeisterten tiefer in die Welt von Raspberry Pi, Arduino und ESP32 ein.  

    **Warum beitreten?**

    - **Expertenunterstützung**: Erhalte Unterstützung bei Problemen nach dem Kauf und bei technischen Herausforderungen – direkt von unserer Community und unserem Team.  
    - **Lernen & Teilen**: Teile Tipps und Anleitungen und erweitere so deine Kenntnisse.  
    - **Exklusive Vorschauen**: Profitiere von frühzeitigen Einblicken in neue Produktankündigungen und Vorschauen.  
    - **Sonderrabatte**: Nutze exklusive Rabatte auf unsere neuesten Produkte.  
    - **Festliche Aktionen und Gewinnspiele**: Nimm an Verlosungen und saisonalen Aktionen teil.  

    👉 Bereit, gemeinsam mit uns Neues zu entdecken und Projekte umzusetzen? Klicke auf [|link_sf_facebook|] und tritt noch heute bei!  


.. _install_os_sd:

2. Installation des Betriebssystems
============================================================

Um deinen Raspberry Pi startklar zu machen, musst du zunächst das Raspberry Pi OS auf eine Micro SD Karte installieren.  
In diesem Abschnitt zeigen wir dir Schritt für Schritt, wie das funktioniert.  

**Benötigte Komponenten**

* Ein Computer (Windows, macOS oder Linux)  
* Eine Micro SD Karte (≥16GB, zuverlässige Marke wie SanDisk oder Samsung)  
* Ein Micro SD Kartenleser  

----

**1. Raspberry Pi Imager installieren**

#. Öffne die offizielle Raspberry Pi Download-Seite: |link_rpi_imager|.  

   Lade die passende Version für dein Betriebssystem herunter (Windows, macOS oder Ubuntu).  

   .. image:: img/os_install_imager.png
       :align: center

#. Nach der Installation starte den Raspberry Pi Imager über das Desktop-Icon oder indem du im Systemmenü nach ``Raspberry Pi Imager`` suchst.  

   .. image:: img/os_open_imager.png
       :align: center

**2. Betriebssystem auf Micro SD Karte installieren**

#. Stecke deine Micro SD Karte über den Kartenleser in den Computer. Achte darauf, dass sie leer ist oder sichere zuvor wichtige Daten.  

#. Im Imager klickst du zunächst auf **Gerät auswählen(Choose Device)** und wählst dein Raspberry Pi Modell aus (z. B. Raspberry Pi 5, Raspberry Pi 4B, 3B/3B+ oder Zero 2W).  

   .. image:: img/os_choose_device.png
       :align: center

#. Klicke auf den Tab **Betriebssystem(Operating System)**, um das gewünschte Betriebssystem auszuwählen.  

   .. note::

        * Für **Raspberry Pi OS**: Wähle einfach das empfohlene System.  
        * Für **Ubuntu**: Klicke auf **Andere universelle Betriebssysteme** -> **Ubuntu** und wähle entweder **Ubuntu Desktop 24.04 LTS (64 Bit)** oder **Ubuntu Server 24.04 LTS (64 Bit)**.  
        * Für **Kali Linux**: Klicke auf **Andere spezialisierte Betriebssysteme** und wähle das passende System.  
        * Für **Retropie**: Klicke auf **Emulations- und Spielebetriebssysteme** und wähle das entsprechende System.  

   .. image:: img/os_choose_os.png
       :align: center

#. Klicke auf **Speicher auswählen(Choose Storage)** und wähle deine Micro SD Karte. Um Fehler zu vermeiden, solltest du andere USB-Laufwerke entfernen, sodass nur die SD Karte angezeigt wird.  

   .. note::

      Achte sehr genau auf die richtige Auswahl des Speichermediums. Wenn du das falsche Laufwerk wählst, könnten wichtige Daten unwiderruflich gelöscht werden.  

   .. image:: img/os_choose_sd.png
       :align: center

#. Klicke auf **Weiter(Next)** und anschließend auf **EINSTELLUNGEN BEARBEITEN(EDIT SETTINGS)**, um dein Raspberry Pi vor dem Schreiben zu konfigurieren.  

   .. note::

        * Wenn du deinen Raspberry Pi direkt mit Monitor, Tastatur und Maus verwenden möchtest, kannst du die erweiterten Einstellungen überspringen und einfach **Yes** klicken, um mit dem Schreiben zu beginnen.  
        * Für Systeme, die nicht im Voraus konfiguriert werden können, erscheint nach **Weiter(Next)** eine Abfrage, ob die Daten auf dem Gerät gespeichert werden sollen. Wenn du ein Backup erstellt hast, wähle **Yes**.  
        * Bei Systemen, bei denen Hostname, WLAN und SSH im Voraus konfiguriert werden können, erscheint ein Pop-up, das fragt, ob die benutzerdefinierten OS-Einstellungen übernommen werden sollen. Du kannst **Yes** oder **No** wählen oder zurückgehen, um weitere Änderungen vorzunehmen.  

   .. image:: img/os_enter_setting.png
       :align: center

----

**3. Betriebssystem-Einstellungen anpassen**

* **Hostname festlegen**:  

  * Vergib einen eindeutigen Namen für deinen Pi.  
  * Später kannst du im Netzwerk mit ``<hostname>.local`` darauf zugreifen.  

  .. image:: img/os_set_hostname.png
      :align: center

* **Benutzername & Passwort festlegen**:  

  * Erstelle ein sicheres Login für deinen Pi.  
  * Anders als bei älteren Versionen gibt es im Raspberry Pi OS kein Standardkonto mehr.  

  .. image:: img/os_set_username.png
      :align: center

* **WLAN konfigurieren**:  

  * Gib deine WLAN-**SSID** (Netzwerkname) und dein **Passwort** ein.  
  * Stelle sicher, dass du das richtige **Wireless LAN country** gemäß |link_iso_code| einstellst (z. B. US, UK, CN); sonst funktioniert das WLAN nicht.  

  .. image:: img/os_set_wifi.png
      :align: center

* **SSH aktivieren (optional, aber empfohlen)**:  

  Damit kannst du von deinem PC aus per Fernzugriff arbeiten. Die Anmeldung erfolgt mit Benutzername/Passwort oder alternativ über Public-Key-Authentifizierung.  

  .. image:: img/os_enable_ssh.png
      :align: center

* **Weitere Optionen**:  

  Du kannst die Optionen "Ton abspielen, wenn fertig" oder "Medium nach Abschluss auswerfen" aktivieren, um den Vorgang komfortabler zu gestalten.  

  .. image:: img/os_options.png
      :align: center

----

**4. OS-Image schreiben**

#. Nach dem Anpassen klicke auf **Save** und dann auf **Yes**, um die Einstellungen zu übernehmen.  

   .. image:: img/os_click_yes.png
       :align: center

#. Falls sich noch Daten auf der Karte befinden, bestätige mit **Yes**, um diese zu überschreiben.  

   .. image:: img/os_continue.png
       :align: center

#. Warte, bis das Schreiben und die Verifizierung abgeschlossen sind. Dies kann einige Minuten dauern. Sobald der Vorgang beendet ist, erscheint **Schreiben erfolgreich(Write Successful)**.  

   .. image:: img/os_finish.png
       :align: center


#. Entferne die SD Karte aus dem Kartenleser und stecke sie in den Slot auf der Unterseite deines Raspberry Pi. Nun ist dein Raspberry Pi bereit zum Booten mit dem neuen Betriebssystem!  

   .. image:: img/os_sd_to_pi.jpg
      :width: 500
      :align: center

