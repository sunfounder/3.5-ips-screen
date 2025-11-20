.. note::

    Hallo und willkommen in der SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasten-Community auf Facebook! Tauche gemeinsam mit anderen Technikbegeisterten tiefer in die Welt von Raspberry Pi, Arduino und ESP32 ein.  

    **Warum beitreten?**

    - **Expertenunterstützung**: Erhalte Unterstützung bei Problemen nach dem Kauf und bei technischen Herausforderungen – direkt von unserer Community und unserem Team.  
    - **Lernen & Teilen**: Teile Tipps und Anleitungen und erweitere so deine Kenntnisse.  
    - **Exklusive Vorschauen**: Profitiere von frühzeitigen Einblicken in neue Produktankündigungen und Vorschauen.  
    - **Sonderrabatte**: Nutze exklusive Rabatte auf unsere neuesten Produkte.  
    - **Festliche Aktionen und Gewinnspiele**: Nimm an Verlosungen und saisonalen Aktionen teil.   

    👉 Bereit, mit uns Neues zu entdecken und zu erschaffen? Klicke auf [|link_sf_facebook|] und werde noch heute Mitglied!  


Kurzanleitung
===========================

1. Betriebssystem installieren
--------------------------------------

Verwende **Raspberry Pi Imager**, um das Betriebssystem zu installieren, das zu deinem Raspberry Pi Board-Modell passt.  

Detaillierte Anleitungen findest du unter :ref:`install_os`.  

.. note::

    * Für das **Raspberry Pi OS**:

        - Wenn Sie einen **Raspberry Pi 4 oder 5** verwenden, gehen Sie bitte zum Raspberry Pi Imager, um das neueste Trixie-System zu installieren (Veröffentlichung: 2025-10-1).     
        - Wenn Sie einen **Raspberry Pi 3B/3B+ oder Zero 2W** verwenden, besuchen Sie bitte |link_bullseye|, um es herunterzuladen.

    * Für das **Ubuntu**-System gehen Sie bitte zum Raspberry Pi Imager und wählen entweder **Ubuntu Desktop 24.04 LTS (64-bit)** oder **Ubuntu Server 24.04 LTS (64-bit)** aus.

    * Für das **Kali Linux**-System besuchen Sie bitte |link_kali_linux|, um es herunterzuladen.

    * Für das **Retropie**-System laden Sie bitte die Version für Ihren Raspberry Pi (nicht Pi 5) von |link_retropie| herunter.

2. Display mit dem Raspberry Pi verbinden
-----------------------------------------------

Dieses 3,5-Zoll-IPS-Display verwendet die gleiche Pinbelegung wie der Raspberry Pi.

**Schritte**:  

1. Schalte den Raspberry Pi aus und trenne das Netzkabel.  
2. Richte das Display am GPIO-Header aus (Pin 1 beachten) und drücke es fest auf die Pins.  
3. Setze die vorbereitete MicroSD-Karte ein und starte den Raspberry Pi.

.. image:: img/3.5_ips_plugin_pi.jpg
    :width: 400
    :align: center

.. _install_driver:

3. Treiberinstallation
-------------------------------

Das 3,5-Zoll-IPS-Display benötigt Treiber, bevor es funktionieren kann. Je nach Betriebssystem befolge die folgenden Anweisungen.  

.. 
    .. warning::

..     * Installiere nur auf einem neu installierten, nicht konfigurierten System (neues Image, Werkseinstellungen).
..     * Die Installation auf einem konfigurierten System kann zu Anmeldeproblemen führen oder das Gerät unbrauchbar machen.
..     * Aktualisiere den Kernel nicht, da das Display einen Kernel-Treiber verwendet. 

**Allgemeine Tipps**:  

* Prüfe zuerst :ref:`compatible_os`.  
* Stelle sicher, dass ``git`` installiert ist (``sudo apt install git``).  
* Die Treiberinstallation kann 1–3 Minuten dauern.  
* Das System startet automatisch neu.  

**Für Raspberry Pi OS**  

.. warning::

        - Wenn Sie einen **Raspberry Pi 4 oder 5** verwenden, gehen Sie bitte zum Raspberry Pi Imager, um das neueste Trixie-System zu installieren (Veröffentlichung: 2025-10-1).     
        - Wenn Sie einen **Raspberry Pi 3B/3B+ oder Zero 2W** verwenden, besuchen Sie bitte |link_bullseye|, um es herunterzuladen.

    * Führe nach der Installation kein ``sudo apt update`` oder ``sudo apt upgrade`` aus, da dies den Kernel aktualisieren und den Displaytreiber beschädigen kann.

Du kannst den folgenden Befehl verwenden, um den Treiber zu installieren:  

.. raw:: html

   <run></run>

.. code-block:: shell

    sudo rm -rf LCD-show
    git clone https://github.com/sunfounder/LCD-show.git
    chmod -R 755 LCD-show
    cd LCD-show/
    sudo ./MHS35IPS-show

Nach erfolgreicher Installation des Treibers dauert der Neustart 2–3 Minuten. Danach erscheint der Raspberry Pi Desktop auf dem 3,5-Zoll-IPS-Bildschirm.  

.. note::

    * Wenn während der Installation ein HDMI-Monitor angeschlossen ist, wird der Desktop nach dem Neustart weiterhin auf dem HDMI-Monitor angezeigt.  
    * Um den 3,5-Zoll-IPS-Bildschirm zu verwenden, trenne den HDMI-Monitor und starte den Raspberry Pi neu.

**Für Ubuntu Desktop/Server**  

Du kannst den folgenden Befehl verwenden, um den Treiber zu installieren:  

.. raw:: html

   <run></run>

.. code-block:: shell

    sudo rm -rf LCD-show-ubuntu
    git clone https://github.com/sunfounder/LCD-show-ubuntu.git
    chmod -R 755 LCD-show-ubuntu
    cd LCD-show-ubuntu/
    sudo ./MHS35IPS-show

Nach erfolgreicher Installation startet das System automatisch neu und der Desktop wird auf dem 3,5-Zoll-IPS-Bildschirm angezeigt.

.. note::

    * Wenn ein HDMI-Monitor angeschlossen ist, bleibt die Desktop-Ausgabe standardmäßig auf HDMI.  
    * Bitte trenne den HDMI-Monitor und starte dein Gerät neu, um die Anzeige auf den 3,5-Zoll-IPS-Bildschirm umzuschalten.  

**Für Kali Linux**  

Du kannst den folgenden Befehl verwenden, um den Treiber zu installieren:  

.. raw:: html

   <run></run>

.. code-block:: shell

    sudo rm -rf LCD-show-kali
    git clone https://github.com/sunfounder/LCD-show-kali.git
    chmod -R 755 LCD-show-kali
    cd LCD-show-kali/
    sudo ./MHS35IPS-show

Nach erfolgreicher Installation startet das System neu und zeigt den Desktop auf dem 3,5-Zoll-IPS-Bildschirm an.  

.. note::

    * Wenn ein HDMI-Monitor angeschlossen ist, wird der Desktop nach dem Neustart weiterhin über HDMI angezeigt.  
    * Bitte trenne den HDMI-Monitor und starte Kali Linux neu, um das 3,5-Zoll-IPS-Display zu verwenden.  

**Für RetroPie**  

.. note::

    * Für das **Retropie**-System lade bitte die passende Version für dein Raspberry-Pi-Modell (nicht Pi 5) von |link_retropie| herunter.

Du kannst den folgenden Befehl verwenden, um den Treiber zu installieren:  

.. raw:: html

   <run></run>

.. code-block:: shell

    sudo rm -rf LCD-show-retropie
    git clone https://github.com/sunfounder/LCD-show-retropie.git
    chmod -R 755 LCD-show-retropie
    cd LCD-show-retropie/
    sudo ./MIS35-show

Nach erfolgreicher Installation startet das System neu und du siehst die RetroPie-Oberfläche auf dem 3,5-Zoll-IPS-Bildschirm.  

.. note::

    * Wenn ein HDMI-Monitor angeschlossen ist, bleibt die Oberfläche auf HDMI-Ausgabe bestehen.  
    * Trenne den HDMI-Monitor und starte deinen Raspberry Pi neu, um das 3,5-Zoll-IPS-Display zu verwenden.  

4. Bildschirm drehen
-----------------------------

Du kannst die Anzeige und die Touch-Ausrichtung drehen, indem du folgenden Befehl ausführst:  

.. note::

    Passe das Verzeichnis an das verwendete System an:  

    * Raspberry Pi OS → ``cd LCD-show/``  
    * Ubuntu → ``cd LCD-show-ubuntu/``  
    * Kali → ``cd LCD-show-kali/``  
    * RetroPie → ``cd LCD-show-retropie/``

.. raw:: html

   <run></run>

.. code-block:: shell

    cd LCD-show/
    sudo ./rotate.sh 90

Das System startet automatisch neu. Nach dem Neustart sind Bildschirm und Touch-Ausrichtung auf **90°** eingestellt.  
Du kannst ``90`` durch ``0``, ``180`` oder ``270`` ersetzen, um die gewünschte Rotation festzulegen.  
