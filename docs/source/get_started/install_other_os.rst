.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_other_os:

Installation von Ubuntu / Kali Linux / RetroPie
================================================================

In diesem Abschnitt wird erläutert, wie Sie **Ubuntu, Kali Linux oder RetroPie** mithilfe des Raspberry Pi Imager auf Ihrem Raspberry Pi installieren.

Benötigte Komponenten
------------------------------

* Ein Computer (Windows, macOS oder Linux)
* Eine microSD-Karte (16 GB oder größer; empfohlen: SanDisk, Samsung)
* Ein microSD-Kartenleser


Unterstützte Betriebssysteme
-----------------------------------------

.. warning::

   * Diese Anleitung gilt nur für die unten aufgeführten Betriebssysteme.
   * Wenn Sie eine andere OS-Version verwenden, funktioniert das 3,5''-IPS-Display nach der Treiberinstallation möglicherweise NICHT korrekt.

* **Ubuntu**

  - |link_ubuntu_2404| (nur für Raspberry Pi 4)

* **Kali Linux**

  - |link_kali_202503|

* **RetroPie**

  - |link_retropie| (nur für Raspberry Pi 4)

-------------------

1. Raspberry Pi Imager installieren
-------------------------------------------

#. Besuchen Sie die offizielle Download-Seite des Raspberry Pi Imager: |link_rpi_imager| und laden Sie die passende Version für Ihr Betriebssystem herunter.

   .. image:: img/imager_download.png
      :width: 70%

#. Folgen Sie den Installationsanweisungen (Sprache, Installationspfad, Bestätigung). Starten Sie anschließend den **Raspberry Pi Imager**.

   .. image:: img/imager_install.png
      :width: 90%

--------------------------------------

2. Betriebssystem auf die microSD-Karte schreiben
------------------------------------------------------------------

#. Stecken Sie die microSD-Karte mit einem Kartenleser in Ihren Computer. Sichern Sie zuvor alle wichtigen Daten.

   .. image:: img/insert_sd.png
      :width: 90%

#. Öffnen Sie den Raspberry Pi Imager und wählen Sie Ihr Gerät aus (z. B. Raspberry Pi 5 oder Raspberry Pi 4).

   .. image:: img/imager_device.png
      :width: 90%

#. Klicken Sie auf **OS**:

   * Scrollen Sie nach unten und wählen Sie **Use Custom**.

     .. image:: img/imager_use_custom.png
        :width: 90%

   * Navigieren Sie zu dem Ordner, in dem Sie das OS-Image gespeichert haben, und wählen Sie die Image-Datei aus.

     .. image:: img/imager_custom_os.png
        :width: 90%

#. Wählen Sie im Bereich **Storage** Ihre microSD-Karte aus.

   .. image:: img/imager_storage.png
      :width: 90%

#. Überprüfen Sie alle Einstellungen und klicken Sie auf **WRITE**.

   .. image:: img/imager_writing_ubuntu.png
      :width: 90%

#. Falls sich bereits Daten auf der Karte befinden, zeigt der Raspberry Pi Imager eine Warnung an, dass alle Daten gelöscht werden.  
   Stellen Sie sicher, dass Sie das richtige Laufwerk ausgewählt haben, und klicken Sie dann auf **I UNDERSTAND, ERASE AND WRITE**.

   .. image:: img/imager_erase.png
      :width: 90%

#. Warten Sie, bis der Schreib- und Verifizierungsprozess abgeschlossen ist. Anschließend wird **Write complete!** angezeigt.  
   Das Speichermedium wird automatisch sicher ausgeworfen.

   .. image:: img/imager_finish_ubuntu.png
      :width: 90%

#. Entfernen Sie die microSD-Karte und setzen Sie sie in Ihren Raspberry Pi ein.  
   Ihr Raspberry Pi ist nun bereit, mit dem neuen Betriebssystem zu starten.

   .. image:: img/os_sd_to_pi.jpg
      :width: 70%