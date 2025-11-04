.. note::

    Hallo und willkommen in der SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasten-Community auf Facebook! Tauche gemeinsam mit anderen Technikbegeisterten tiefer in die Welt von Raspberry Pi, Arduino und ESP32 ein.  

    **Warum beitreten?**

    - **Expertenunterstützung**: Erhalte Unterstützung bei Problemen nach dem Kauf und bei technischen Herausforderungen – direkt von unserer Community und unserem Team.  
    - **Lernen & Teilen**: Teile Tipps und Anleitungen und erweitere so deine Kenntnisse.  
    - **Exklusive Vorschauen**: Profitiere von frühzeitigen Einblicken in neue Produktankündigungen und Vorschauen.  
    - **Sonderrabatte**: Nutze exklusive Rabatte auf unsere neuesten Produkte.  
    - **Festliche Aktionen und Gewinnspiele**: Nimm an Verlosungen und saisonalen Aktionen teil.  

    👉 Bereit, gemeinsam mit uns Neues zu entdecken und Projekte umzusetzen? Klicke auf [|link_sf_facebook|] und tritt noch heute bei!  

.. _remote_desktop:

Remote-Desktop-Zugriff für Raspberry Pi
==================================================

Für alle, die eine grafische Benutzeroberfläche (GUI) der Kommandozeile vorziehen, bietet der Raspberry Pi die Möglichkeit zum Remote-Desktop-Zugriff. In dieser Anleitung erfährst du Schritt für Schritt, wie du VNC (Virtual Network Computing) einrichtest und verwendest.  

Wir empfehlen dafür den Einsatz von `VNC® Viewer <https://www.realvnc.com/en/connect/download/viewer/>`_.  

**VNC-Dienst auf dem Raspberry Pi aktivieren**

Der VNC-Dienst ist in Raspberry Pi OS bereits vorinstalliert, jedoch standardmäßig deaktiviert. So aktivierst du ihn:  

#. Gib folgenden Befehl im Terminal des Raspberry Pi ein:

    .. raw:: html

        <run></run>

    .. code-block:: 

        sudo raspi-config

#. Navigiere mit den Pfeiltasten zu **Schnittstellenoptionen(Interfacing Options)** und bestätige mit **Eingabetaste(Enter)**.  

    .. image:: img/config_interface.png
        :align: center

#. Wähle **VNC** aus der Liste der Optionen.  

    .. image:: img/vnc.png
        :align: center

#. Verwende die Pfeiltasten, um **<Yes>** -> **<OK>** -> **<Finish>** auszuwählen und die Aktivierung des VNC-Dienstes abzuschließen.  

    .. image:: img/vnc_yes.png
        :align: center

**Anmeldung über VNC Viewer**

#. Lade `VNC Viewer <https://www.realvnc.com/en/connect/download/viewer/>`_ auf deinem Computer herunter und installiere es.  

#. Starte anschließend den VNC Viewer. Gib den Hostnamen oder die IP-Adresse deines Raspberry Pi ein und drücke Enter.  

    .. image:: img/vnc_viewer1.png
        :align: center

#. Gib bei Aufforderung den Benutzernamen und das Passwort deines Raspberry Pi ein und bestätige mit **OK**.  

    .. image:: img/vnc_viewer2.png
        :align: center

#. Nach wenigen Sekunden erscheint der Raspberry Pi OS Desktop. Nun kannst du ein Terminal öffnen und Befehle eingeben.  

    .. image:: img/bookwarm.png
        :align: center
