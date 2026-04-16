.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_driver_retropie:

Installation des 3,5'' IPS-Displaytreibers unter RetroPie
===============================================================

In diesem Abschnitt wird erläutert, wie Sie den Treiber für das 3,5''-IPS-Display im **RetroPie**-System installieren.  
Zunächst greifen Sie per SSH auf Ihren Raspberry Pi zu und installieren anschließend den Treiber, sodass die RetroPie-Oberfläche sowohl auf dem HDMI-Monitor als auch auf dem 3,5''-Display angezeigt werden kann.

Installation des 3,5'' IPS-Displaytreibers (Wichtig)
----------------------------------------------------------------------

#. Schließen Sie Ihren Raspberry Pi an einen Monitor an und schalten Sie ihn ein. Stellen Sie sicher, dass auch ein Ethernet-Kabel angeschlossen ist, damit das Gerät auf das Netzwerk zugreifen kann.

   .. image:: img/connect_all_retropie.jpg
      :width: 90%

#. Sobald die RetroPie-Oberfläche erscheint, drücken Sie **F4** auf der Tastatur, um diese zu verlassen und zur Kommandozeile zu wechseln.

#. Um SSH zu aktivieren, führen Sie folgenden Befehl aus:

   .. code-block:: shell
   
       sudo raspi-config
   
   Navigieren Sie im Menü zu: **Interface Options** → **SSH** → **Enable**.

#. (Optional) Wenn Sie sich über eine IP-Adresse verbinden möchten, können Sie diese mit folgendem Befehl ermitteln:

   .. code-block:: shell

       hostname -I

   Die Ausgabe sieht beispielsweise so aus:

   .. code-block:: text

       192.168.100.119 xxxx.xxx

#. Öffnen Sie auf Ihrem Computer ein Terminal und verbinden Sie sich per SSH mit dem Raspberry Pi, indem Sie eine der folgenden Methoden verwenden:

   * **Mit Hostnamen (empfohlen):**

     .. code-block:: shell

         ssh pi@retropie.local

   * **Mit IP-Adresse:**

     .. code-block:: shell

         ssh pi@IP_ADDRESS

     Beispiel:

     .. code-block:: shell

         ssh pi@192.168.100.119

   Beim ersten Verbindungsaufbau geben Sie ``yes`` ein, um zu bestätigen, und anschließend das Standardpasswort:

   .. code-block:: text

       raspberry

#. Nach erfolgreicher Anmeldung führen Sie die folgenden Befehle aus, um den Treiber für das 3,5''-IPS-Display zu installieren:

   .. note::
   
       * Für das **RetroPie**-System stellen Sie sicher, dass Sie die Version aus |link_retropie| verwenden (nur für Raspberry Pi 4).

   .. code-block:: shell
   
       sudo rm -rf LCD-show-retropie
       git clone https://github.com/sunfounder/LCD-show-retropie.git
       chmod -R 755 LCD-show-retropie
       cd LCD-show-retropie/
       sudo ./MHS35IPS-show

#. Nach Abschluss der Installation wird der Raspberry Pi automatisch neu gestartet.

   * Nach dem Neustart wird die RetroPie-Oberfläche sowohl auf dem HDMI-Monitor als auch auf dem 3,5''-IPS-Display angezeigt.
   * Der Startvorgang kann 1–2 Minuten dauern – bitte haben Sie etwas Geduld.

Display drehen
-----------------------------

Sie können die Ausrichtung von Bildschirm und Touchfunktion mit folgendem Befehl ändern:

.. code-block:: shell

    cd LCD-show-retropie/
    sudo ./rotate.sh 90

Das System wird automatisch neu gestartet. Nach dem Neustart sind Anzeige und Touchfunktion auf **90°** gedreht.  
Sie können ``90`` durch ``0``, ``180`` oder ``270`` ersetzen, um die gewünschte Ausrichtung einzustellen.