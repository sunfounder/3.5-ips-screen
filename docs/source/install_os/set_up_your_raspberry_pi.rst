.. note::

    Hallo und willkommen in der SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasten-Community auf Facebook! Tauche gemeinsam mit anderen Technikbegeisterten tiefer in die Welt von Raspberry Pi, Arduino und ESP32 ein.  

    **Why Join?**

    - **Expert Support**: Erhalte Unterstützung bei Supportanfragen nach dem Kauf sowie bei technischen Herausforderungen – mit Hilfe unserer Community und unseres Teams.  
    - **Learn & Share**: Teile Tipps und Anleitungen und erweitere so deine Kenntnisse.  
    - **Exclusive Previews**: Profitiere von frühem Zugang zu neuen Produktankündigungen und exklusiven Einblicken.  
    - **Special Discounts**: Sichere dir exklusive Rabatte auf unsere neuesten Produkte.  
    - **Festive Promotions and Giveaways**: Nimm an Gewinnspielen und saisonalen Aktionen teil.  

    👉 Bereit, gemeinsam mit uns Neues zu entdecken und Projekte umzusetzen? Klicke auf [|link_sf_facebook|] und tritt noch heute bei!  

.. _setup_pi:

3. Richte dein Raspberry Pi ein
===================================

Um mit dem Programmieren und Steuern zu beginnen, musst du zuerst Zugriff auf dein Raspberry Pi erhalten.  
In diesem Abschnitt zeigen wir dir zwei gängige Methoden: die Nutzung von Monitor, Tastatur und Maus oder das Einrichten einer **Headless-Verbindung**, um dich von einem anderen Computer aus einzuloggen.  

Wenn du einen Bildschirm hast
---------------------------------

**Benötigte Komponenten**

* Raspberry Pi  
* Netzteil  
* microSD-Karte  
* HDMI-Kabel  
* Bildschirm  
* Maus  
* Tastatur  

#. Stecke die microSD-Karte in dein Raspberry Pi.  
#. Verbinde Maus, Tastatur und Bildschirm (bei Pi 4/5 verwende **HDMI0**, den Port neben dem Stromanschluss).  
#. Schalte das Raspberry Pi ein.  
#. Nach kurzer Zeit erscheint der Desktop von Raspberry Pi OS, und du kannst ein Terminal öffnen, um Befehle einzugeben.  

    .. image:: img/bookwarm.png
        :align: center


Wenn du keinen Bildschirm hast (Headless Setup)
-----------------------------------------------------

Ohne Monitor kannst du dein Raspberry Pi remote einrichten und darauf zugreifen. Dies ist die bequemste Methode für den Einstieg.  

**Benötigte Komponenten**

* Raspberry Pi  
* Netzteil  
* microSD-Karte  
* Ein Computer im selben Netzwerk  

**Tipps**
 
* Stelle das **Wireless-LAN-Land** korrekt mit dem ISO/IEC-Alpha-2-Code ein (z. B. ``US``, ``UK``, ``CN``); andernfalls funktioniert WLAN nicht.  
* Stelle sicher, dass sich Raspberry Pi und Computer im selben lokalen Netzwerk befinden.  
* Für eine stabilere Verbindung verwende wenn möglich ein Netzwerkkabel (Ethernet).  


**Verbindung per SSH**

1. Öffne auf deinem Computer ein Terminal (Windows: **PowerShell**, macOS/Linux: **Terminal**) und gib ein:  

   .. code-block::

      ssh <username>@<hostname>.local
      # Example:
      ssh daisy@pi.local

#. Alternativ kannst du in der DHCP-/Client-Liste deines Routers nach der IP deines Raspberry Pi suchen und dich mit dieser verbinden:  

   .. code-block::

      ssh <username>@<IP>
      
      # Example:

      ssh daisy@192.xxx.xx.xx

#. Beim ersten Login erscheint eine Sicherheitsabfrage. Gib ``yes`` ein, um fortzufahren.  

#. Gib das Passwort ein, das du im Raspberry Pi Imager festgelegt hast. (Beim Tippen werden keine Zeichen angezeigt – das ist normal.)  

   .. note::  
      Dass beim Eingeben des Passworts keine Zeichen erscheinen, ist ein übliches Sicherheitsfeature. Tippe das Passwort einfach sorgfältig ein.  

#. Sobald die Verbindung steht, ist dein Raspberry Pi bereit für den Remote-Zugriff.  

   .. image:: img/ssh_login.png
      :align: center

**Fehlerbehebung**

* **ssh: Could not resolve hostname ...**  

  * Überprüfe, ob der Hostname korrekt ist.  
  * Falls es trotzdem nicht funktioniert, verwende die IP-Adresse deines Raspberry Pi anstelle von ``<hostname>.local``.  

* **The term 'ssh' is not recognized... (Windows)**  

  * Dein System hat kein OpenSSH installiert. Installiere OpenSSH manuell (siehe :ref:`openssh_powershell`) oder nutze einen SSH-Client eines Drittanbieters (siehe :ref:`login_windows`).  

* **Permission denied (publickey,password)**  

  * Stelle sicher, dass du den Benutzernamen und das Passwort verwendest, die du im Raspberry Pi Imager eingerichtet hast.  

* **Connection refused**  

  * Warte 1–2 Minuten nach dem Einschalten.  
  * Prüfe, ob SSH im Raspberry Pi Imager aktiviert wurde.  

**Optionen für grafischen Zugriff**

Falls du lieber mit einer grafischen Oberfläche statt nur mit der Kommandozeile arbeiten möchtest, hast du zwei Möglichkeiten:  

    .. image:: img/bookwarm.png
        :align: center

* :ref:`remote_desktop`: Aktiviere **VNC (Virtual Network Computing)** für ein vollständiges Desktop-Erlebnis auf deinem Pi.  
* |link_rpi_connect|: Verwende **Raspberry Pi Connect** für sicheren Fernzugriff von überall – direkt im Browser.  

Jetzt kannst du dein Raspberry Pi auch ohne Monitor steuern – entweder über SSH für die Kommandozeile oder mit VNC / Raspberry Pi Connect für eine Desktop-Oberfläche.  
