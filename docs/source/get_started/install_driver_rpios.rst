.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_driver_rapios:

Installation des 3,5'' IPS-Displaytreibers unter Raspberry Pi OS
==============================================================================

In diesem Abschnitt wird erläutert, wie Sie den Treiber für das 3,5''-IPS-Display unter **Raspberry Pi OS** installieren.  
Sie können Ihren Raspberry Pi entweder mit Monitor oder per SSH (headless) verwenden und anschließend den Treiber installieren, um das Display zu aktivieren.

Wenn ein Bildschirm vorhanden ist
---------------------------------

**Benötigte Komponenten**

* Raspberry Pi
* Offizielles Netzteil
* MicroSD-Karte
* HDMI-Kabel  
  (Bei Raspberry Pi 4/5 verwenden Sie **HDMI0**, den Anschluss nahe der Stromversorgung.)
* Monitor
* Tastatur und Maus

**Schritte**

#. Stecken Sie die MicroSD-Karte in Ihren Raspberry Pi.
#. Schließen Sie Tastatur, Maus und Monitor an.
#. Schalten Sie den Raspberry Pi ein.
#. Nach dem Start erscheint die Desktop-Oberfläche von Raspberry Pi OS. 

   .. image:: img/connect_all_rpios.jpg
      :width: 90%

#. Öffnen Sie ein **Terminal**, um Befehle einzugeben.

   .. image:: img/open_terminal.png
      :width: 80%
      :align: center


Wenn kein Bildschirm vorhanden ist (Headless)
----------------------------------------------

Ohne Monitor können Sie Ihren Raspberry Pi remote konfigurieren und sich anmelden.  
Dies ist für die meisten Benutzer die bequemste Methode.

**Benötigte Komponenten**

* Raspberry Pi
* Offizielles Netzteil
* MicroSD-Karte
* Ein Computer im selben Netzwerk

**Hinweise**

* Stellen Sie sicher, dass Sie alle Einstellungen gemäß :ref:`imager_custom` beim Installieren des Systems mit Raspberry Pi Imager vorgenommen haben.
* Achten Sie darauf, dass sich Ihr Raspberry Pi und Ihr Computer im selben lokalen Netzwerk befinden.
* Für eine stabile Verbindung wird, wenn möglich, Ethernet empfohlen.


**Verbindung per SSH**

#. Öffnen Sie ein Terminal auf Ihrem Computer (Windows: **PowerShell**; macOS/Linux: **Terminal**) und verbinden Sie sich mit Ihrem Raspberry Pi:

   .. code-block:: bash

      ssh <Benutzername>@<Hostname>.local
      # Beispiel:
      ssh daisy@pi.local

2. Alternativ können Sie die IP-Adresse Ihres Raspberry Pi in der DHCP-Liste Ihres Routers ermitteln und sich wie folgt verbinden:

   .. code-block:: bash

      ssh <Benutzername>@<IP-Adresse>
      # Beispiel:
      ssh daisy@192.168.1.42

3. Beim ersten Login geben Sie ``yes`` ein, um das SSH-Zertifikat zu bestätigen.

4. Geben Sie das Passwort ein, das Sie im Raspberry Pi Imager festgelegt haben.  
   (Während der Eingabe wird nichts angezeigt – das ist normal.)

5. Nach der Anmeldung haben Sie vollständigen Zugriff auf die Kommandozeile.

   .. image:: img/ssh_login.png
      :align: center


--------------------------------------

Grafischer Fernzugriff (Optional)
----------------------------------------

Wenn Sie eine grafische Oberfläche bevorzugen:

.. image:: img/desktop_trixie.png
   :align: center

* :ref:`remote_desktop` — Verwenden Sie **VNC** für den vollständigen Desktopzugriff
* |link_rpi_connect| — Verwenden Sie **Raspberry Pi Connect** über den Browser


--------------------------------------

Installation des 3,5'' IPS-Displaytreibers (Wichtig)
------------------------------------------------------------------

Dies ist der entscheidende Schritt, um das 3,5''-IPS-Display zu aktivieren.

Führen Sie die folgenden Befehle aus:

.. code-block:: shell

   sudo rm -rf LCD-show
   git clone https://github.com/sunfounder/LCD-show.git
   chmod -R 755 LCD-show
   cd LCD-show/
   sudo ./MHS35IPS-show

Nach der Installation:

* Trennen Sie den HDMI-Monitor. 
* Nach dem Neustart wird das System auf dem 3,5''-IPS-Display angezeigt.

Display drehen
-----------------------------

Sie können die Ausrichtung von Bildschirm und Touchfunktion mit folgendem Befehl ändern:

.. code-block:: shell

    cd LCD-show/
    sudo ./rotate.sh 90

Das System wird automatisch neu gestartet. Nach dem Neustart sind Anzeige und Touchfunktion auf **90°** gedreht.  
Sie können ``90`` durch ``0``, ``180`` oder ``270`` ersetzen, um die gewünschte Ausrichtung einzustellen.