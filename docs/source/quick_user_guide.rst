.. note:: 

    Hallo und willkommen in der SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasten-Community auf Facebook! Tauche gemeinsam mit anderen Technikfans tiefer in die Welt von Raspberry Pi, Arduino und ESP32 ein.  

    **Why Join?**

    - **Expert Support**: Löse Probleme nach dem Kauf und technische Herausforderungen mit Unterstützung unserer Community und unseres Teams.  
    - **Learn & Share**: Teile Tipps und Tutorials, um deine Kenntnisse zu erweitern.  
    - **Exclusive Previews**: Erhalte frühen Zugang zu neuen Produktankündigungen und exklusiven Einblicken.  
    - **Special Discounts**: Profitiere von exklusiven Rabatten auf unsere neuesten Produkte.  
    - **Festive Promotions and Giveaways**: Nimm an Gewinnspielen und saisonalen Aktionen teil.  

    👉 Bereit, mit uns zu entdecken und zu kreieren? Klicke auf [|link_sf_facebook|] und werde noch heute Mitglied!  

Quick User Guide
===========================

1. Install the Operating System
--------------------------------------

Verwende **Raspberry Pi Imager**, um das Betriebssystem zu installieren, das zu deinem Raspberry Pi Board-Modell passt.  

Detaillierte Anleitungen findest du unter :ref:`install_os`.  

.. note::

    * **Raspberry Pi OS**: Wenn du einen Raspberry Pi 3B/3B+ oder Zero 2W verwendest, musst du **Bullseye** anstelle von Bookworm installieren, damit der Bildschirm korrekt funktioniert.  
    * **Other Operating Systems**: Folge den Anweisungen im Raspberry Pi Imager, um das für dein spezifisches Raspberry Pi Modell empfohlene Betriebssystem zu installieren.  

2. Connect the Display to the Raspberry Pi
-----------------------------------------------

Dieses 3,5-Zoll-IPS-Display verwendet denselben Pinout wie der Raspberry Pi.  

**Steps**:  

1. Schalte den Raspberry Pi aus und trenne das Netzkabel.  
2. Richte das Display am GPIO-Header aus (Pin 1 beachten) und drücke es fest auf die Pins.  
3. Setze die vorbereitete MicroSD-Karte ein und starte den Raspberry Pi.  

.. image:: img/3.5_ips_plugin_pi.jpg
    :width: 400
    :align: center  

.. _install_driver:  

3. Driver Installation
-------------------------------

Das 3,5-Zoll-IPS-Display benötigt Treiber, bevor es funktionieren kann. Je nach Betriebssystem befolge die folgenden Anweisungen.  

.. note::  

    Du musst dich entweder per Remote in deinen Raspberry Pi einloggen oder einen zusätzlichen Plug-and-Play-Monitor anschließen, um die Treiber zu installieren. Erst nach der Installation funktioniert das 3,5-Zoll-Display korrekt.  

    Detaillierte Anleitungen findest du unter :ref:`setup_pi`.  

**General tips**:  

* Prüfe zuerst :ref:`compatible_os`.  
* Stelle sicher, dass ``git`` installiert ist (``sudo apt install git``).  
* Die Treiberinstallation kann 1–3 Minuten dauern.  
* Das System startet automatisch neu.  

**For Raspberry Pi OS**  

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

    * Wenn du einen Raspberry Pi 3B/3B+ oder Zero 2W nutzt, musst du das **Bullseye**-System installieren, um dieses 3,5-Zoll-IPS-Display zu verwenden.  
    * Wenn während der Installation ein HDMI-Monitor angeschlossen ist, wird der Desktop nach dem Neustart weiterhin auf dem HDMI-Monitor angezeigt.  
    * Um den 3,5-Zoll-IPS-Bildschirm zu verwenden, trenne den HDMI-Monitor und starte den Raspberry Pi neu.  

**For Ubuntu Desktop/Server**  

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


**For Kali Linux**  

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

**For RetroPie**  

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

4.Rotate the Display
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
