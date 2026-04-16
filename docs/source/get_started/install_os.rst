.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_os:

2. Installation des Betriebssystems
===========================================

In diesem Abschnitt wird erläutert, wie Sie ein kompatibles Betriebssystem auf Ihrem Raspberry Pi installieren.  
Je nach Raspberry-Pi-Modell und Anwendungsfall werden unterschiedliche Systeme unterstützt.

.. note::

    Derzeit ist das 3,5-Zoll-Display nur mit Raspberry Pi 4 und Raspberry Pi 5 kompatibel. Für Raspberry Pi 3B, 3B+ und Zero 2W wird die Verwendung mit diesem Display nicht empfohlen, da die Installation des Touchscreen-Treibers zu Fehlfunktionen führen kann.

    * Für **Raspberry Pi OS**:

      - Trixie Desktop (64-bit) (veröffentlicht: 04.12.2025)
      - Bookworm Desktop (64-bit) (veröffentlicht: 24.11.2025, 13.05.2025, 06.05.2025)

        Nach der Treiberinstallation unter Bookworm müssen Sie ``startx`` ausführen, um die Desktop-Oberfläche zu starten.

    * Für **Ubuntu**:

      - |link_ubuntu_2404| (nur für Raspberry Pi 4)

    * Für **Kali Linux**:

      - |link_kali_202503|

    * Für **RetroPie**:

      - |link_retropie| (nur für Raspberry Pi 4)

.. toctree::
    :maxdepth: 1

    install_rpi_os
    install_other_os