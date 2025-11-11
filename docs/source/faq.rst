.. note::

    Hallo und willkommen in der SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasten-Community auf Facebook! Tauche gemeinsam mit anderen Technikbegeisterten tiefer in die Welt von Raspberry Pi, Arduino und ESP32 ein.  

    **Warum beitreten?**

    - **Expertenunterstützung**: Erhalte Unterstützung bei Problemen nach dem Kauf und bei technischen Herausforderungen – direkt von unserer Community und unserem Team.  
    - **Lernen & Teilen**: Teile Tipps und Anleitungen und erweitere so deine Kenntnisse.  
    - **Exklusive Vorschauen**: Profitiere von frühzeitigen Einblicken in neue Produktankündigungen und Vorschauen.  
    - **Sonderrabatte**: Nutze exklusive Rabatte auf unsere neuesten Produkte.  
    - **Festliche Aktionen und Gewinnspiele**: Nimm an Verlosungen und saisonalen Aktionen teil.  

    👉 Bereit, mit uns Neues zu entdecken und Projekte umzusetzen? Klicke auf [|link_sf_facebook|] und tritt noch heute bei!  

FAQ
===========================

Wird der 3,5''-Touchscreen vom Raspberry Pi Trixie-System unterstützt?  
------------------------------------------------------------------------------------

Der 3,5''-Touchscreen wird im **Trixie**-System derzeit noch nicht unterstützt. Wir aktualisieren den Treiber in Kürze.  

- Wenn Sie einen **Raspberry Pi 4 oder 5** verwenden, installieren Sie bitte das ältere **Bookworm**-System.  
- Wenn Sie einen **Raspberry Pi 3B/3B+ oder Zero 2W** verwenden, müssen Sie das **|link_bullseye|**-System installieren.  
- Führen Sie nach der Installation **nicht** den Befehl ``sudo apt update`` oder ``sudo apt upgrade`` aus, da dies den Kernel aktualisieren und den Displaytreiber beschädigen kann.

Warum kann ich mich nach der Installation des 3,5-Zoll-Displaytreibers nicht anmelden?  
---------------------------------------------------------------------------------------------------

Dieses Problem wird in der Regel durch ein **Kernel-Update** verursacht.  
Ein Systemupdate nach der Installation kann den Kernel aktualisieren und den Displaytreiber inkompatibel machen.  
Vermeiden Sie es, ``sudo apt update`` oder ``sudo apt upgrade`` auszuführen, um Anmeldeprobleme zu verhindern.


Warum bleibt mein 3,5-Zoll-Bildschirm nach dem Einschalten schwarz oder weiß?
------------------------------------------------------------------------------------

* Stelle sicher, dass der richtige Treiber installiert ist. Detaillierte Anleitungen findest du unter :ref:`install_driver`.  
* Wenn du **Raspberry Pi OS** auf einem Raspberry Pi 3B/3B+ oder Zero 2W verwendest, musst du **Bullseye** statt **Bookworm** installieren, um die Kompatibilität sicherzustellen.  
* Überprüfe, ob das Display fest und korrekt mit den GPIO-Pins verbunden ist.  

Kann der 3,5-Zoll-IPS-Touchscreen gleichzeitig mit einem HDMI-Monitor genutzt werden?
------------------------------------------------------------------------------------------

Der 3,5-Zoll-Touchscreen kann nicht gleichzeitig mit einem HDMI-Monitor betrieben werden.  

Nach der Installation des Treibers für das 3,5"-IPS-Display schaltet das System automatisch auf HDMI-Ausgabe, wenn sowohl das 3,5"-IPS-Display als auch ein HDMI-Monitor angeschlossen sind.  

Um die Ausgabe auf dem 3,5"-IPS-Touchscreen zu sehen, muss der HDMI-Monitor getrennt (abgesteckt) werden.  

Die Bildschirmausrichtung ist falsch?
-----------------------------------------------------------------------------------

Führe das Rotationsskript aus, um das Problem zu beheben:  

* ``cd LCD-show/``   # Pfad entsprechend deinem Betriebssystem anpassen  
* ``sudo ./rotate.sh 90``  

Ersetze ``90`` durch ``0``, ``180`` oder ``270``, um die gewünschte Ausrichtung einzustellen.  

Kann ich das Display ohne Treiberinstallation verwenden?
--------------------------------------------------------------

Nein. Dieses Display verwendet eine SPI-Schnittstelle und benötigt einen speziellen Treiber, um korrekt zu funktionieren.  

Detaillierte Anleitungen findest du unter :ref:`install_driver`.  

Warum läuft der Lüfter nach dem Anschließen dauerhaft? Kann er per Code gesteuert werden?
----------------------------------------------------------------------------------------------

Der Lüfteranschluss auf der Rückseite liefert direkt 5V und lässt sich nicht per Software steuern. Der Lüfter läuft permanent, sobald er angeschlossen ist.  

Was tun, wenn während der Treiberinstallation ``git not found`` oder Netzwerkfehler auftreten?
------------------------------------------------------------------------------------------------------

Stelle sicher, dass der Raspberry Pi mit dem Internet verbunden ist.  

Wenn git fehlt, führe Folgendes aus:  

* ``sudo apt update``  
* ``sudo apt install git``  

Starte danach die Installation erneut.  

Funktioniert dieses Display auch mit Ubuntu, Kali oder RetroPie?
--------------------------------------------------------------------

Ja, allerdings müssen spezifische Treiber installiert werden.  

Detaillierte Anleitungen findest du unter :ref:`install_driver`.  


Kann das Display auch bei extremen Temperaturen betrieben werden?
-----------------------------------------------------------------------

Der Betriebstemperaturbereich liegt zwischen -20 °C und 60 °C. Überschreite diesen Bereich nicht, um Schäden oder eine verkürzte Lebensdauer zu vermeiden.  

Was tun, wenn es zu Farbstörungen auf dem Display kommt?
-------------------------------------------------------------

Unter Systemen wie Kali Linux sollte der ``MHS35IPS-show``-Treiber verwendet oder auf eine aktuelle getestete Version (z. B. 2025.8.04) aktualisiert werden, um die Kompatibilität zu verbessern.  
