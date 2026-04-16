.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_driver_kali:

Installation des 3,5'' IPS-Displaytreibers unter Kali
===============================================================

In diesem Abschnitt wird erläutert, wie Sie den Treiber für das 3,5''-IPS-Display unter **Kali Linux** installieren.  
Sie melden sich im System an, öffnen ein Terminal und installieren den Treiber, um die Anzeige auf dem 3,5''-IPS-Display zu aktivieren.

Installation des 3,5'' IPS-Displaytreibers (Wichtig)
----------------------------------------------------------------------

#. Schließen Sie Ihren Raspberry Pi an einen Monitor an und schalten Sie ihn ein. Stellen Sie sicher, dass ein Ethernet-Kabel für den Netzwerkzugang angeschlossen ist.

   .. image:: img/connect_all_kali.jpg
      :width: 90%

#. Melden Sie sich mit den Standard-Zugangsdaten von Kali an:

   * Benutzername: ``kali``
   * Passwort: ``kali``

   Öffnen Sie nach der Anmeldung das **Terminal**.

#. Öffnen Sie den integrierten Firefox-Browser und rufen Sie folgende Adresse auf:

   ``35-ips-screen.rtfd.io``

#. Kopieren Sie die folgenden Befehle und führen Sie sie nacheinander im Terminal aus, um den Treiber zu installieren:

   .. code-block:: shell
   
      sudo rm -rf LCD-show-kali
      git clone https://github.com/sunfounder/LCD-show-kali.git
      chmod -R 755 LCD-show-kali
      cd LCD-show-kali/
      sudo ./MHS35IPS-show

#. Nach Abschluss der Installation:

   * Trennen Sie den HDMI-Monitor.
   * Der Raspberry Pi wird automatisch neu gestartet.
   * Nach dem Neustart wird das System auf dem 3,5''-IPS-Display angezeigt.

Display drehen
-----------------------------

Sie können die Ausrichtung von Bildschirm und Touchfunktion mit folgendem Befehl ändern:

.. code-block:: shell

    cd LCD-show-kali/
    sudo ./rotate.sh 90

Das System wird automatisch neu gestartet. Nach dem Neustart sind Anzeige und Touchfunktion auf **90°** gedreht.  
Sie können ``90`` durch ``0``, ``180`` oder ``270`` ersetzen, um die gewünschte Ausrichtung einzustellen.