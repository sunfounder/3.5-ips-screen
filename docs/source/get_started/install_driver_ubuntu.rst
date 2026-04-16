.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_driver_ubuntu:

Installation des 3,5'' IPS-Displaytreibers unter Ubuntu
===============================================================

In diesem Abschnitt wird erläutert, wie Sie den Treiber für das 3,5''-IPS-Display unter **Ubuntu** installieren.  
Sie führen zunächst die grundlegende Systemeinrichtung durch, installieren die erforderlichen Tools und anschließend den Treiber, um die Anzeige auf dem 3,5''-IPS-Display zu aktivieren.

Installation des 3,5'' IPS-Displaytreibers (Wichtig)
------------------------------------------------------------------

#. Schließen Sie Ihren Raspberry Pi an einen Monitor an und schalten Sie ihn ein. Stellen Sie sicher, dass ein Ethernet-Kabel für den Netzwerkzugang angeschlossen ist.

   .. image:: img/connect_all_ubuntu.jpg
      :width: 90%

#. Folgen Sie den Anweisungen auf dem Bildschirm, um die Ersteinrichtung abzuschließen, einschließlich Sprache, Tastaturlayout, Region, Benutzername und Passwort.

#. Nach Abschluss der Einrichtung melden Sie sich mit Ihrem Benutzernamen und Passwort an und öffnen das **Terminal**.

#. Installieren Sie Git, das zum Herunterladen des Treibers benötigt wird:

   .. code-block:: shell

        sudo apt install git

#. Öffnen Sie den integrierten Firefox-Browser und rufen Sie folgende Adresse auf:

   ``35-ips-screen.rtfd.io``

#. Kopieren Sie die folgenden Befehle und führen Sie sie nacheinander im Terminal aus, um den Treiber zu installieren:

   .. code-block:: shell
   
        sudo rm -rf LCD-show-ubuntu
        git clone https://github.com/sunfounder/LCD-show-ubuntu.git
        chmod -R 755 LCD-show-ubuntu
        cd LCD-show-ubuntu/
        sudo ./MHS35IPS-show

#. Nach Abschluss der Installation:

   * Trennen Sie den HDMI-Monitor.
   * Der Raspberry Pi wird automatisch neu gestartet.
   * Nach dem Neustart wird das System auf dem 3,5''-IPS-Display angezeigt.

Display drehen
-----------------------------

Sie können die Ausrichtung von Bildschirm und Touchfunktion mit folgendem Befehl ändern:

.. code-block:: shell

    cd LCD-show-ubuntu/
    sudo ./rotate.sh 90

Das System wird automatisch neu gestartet. Nach dem Neustart sind Anzeige und Touchfunktion auf **90°** gedreht.  
Sie können ``90`` durch ``0``, ``180`` oder ``270`` ersetzen, um die gewünschte Ausrichtung einzustellen.