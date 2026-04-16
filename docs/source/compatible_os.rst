.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message


.. _compatible_os:

Compatible Systems and Raspberry Pi Boards
===============================================

.. note::

   * 表格中的 compatibility tests were conducted on **2026.3.17**.  

.. note::

    * For the **Raspberry Pi OS**: 

      - If you are using a **Raspberry Pi 4 or 5**, please Go to Raspberry Pi Imager to install the latest Trixie system (released:2025-10-1).     
      - If you are using a **Raspberry Pi 3B/3B+ or Zero 2W**, please visit |link_bullseye| to download it.
      - Not yet adapted for the Raspberry Pi Zero W. 

    * For **Ubuntu** system, please Go to Raspberry Pi Imager and select either **Ubuntu Desktop 24.04 LTS (64 bit)** or **Ubuntu Server 24.04 LTS (64 bit)**.
    
    * For **Kali Linux** system, please visit |link_kali_202503| to download it.

    * For the **Retropie** system, please download the version for your Raspberry Pi (not Pi 5) from the |link_retropie| .

.. list-table:: 3.5'' IPS Screen Compatibility
   :header-rows: 1
   :widths: 20 35 15 30

   * - Raspberry Pi
     - Operating System
     - IPS Screen
     - Notes
   * - Pi 5
     - Raspberry Pi OS (Trixie 64-bit)
     - ✔
     - Fully compatible; recommended
   * - Pi 5
     - Raspberry Pi OS (Bookworm 64-bit)
     - ✔
     - Works; run ``startx`` after driver install
   * - Pi 4
     - Raspberry Pi OS (Trixie 64-bit)
     - ✔
     - Fully compatible
   * - Pi 4
     - Raspberry Pi OS (Bookworm 64-bit)
     - ✔
     - Stable; dual display supported
   * - Pi 4
     - Ubuntu 24.04 (Desktop)
     - ✔
     - Works with manual driver setup
   * - Pi 4
     - Ubuntu Server 24.04
     - ✘
     - No GUI; screen not supported
   * - Pi 4
     - Kali Linux (2025)
     - ✘
     - Black screen after driver install
   * - Pi 4
     - RetroPie
     - ✔
     - Fully supported


.. .. list-table::
..     :header-rows: 1

..     * - System / Board
..       - Pi 5
..       - Pi 4B
..     * - Raspberry Pi OS
..       - #. Trixie Desktop 64bit (released: 2025-12-04)
..         #. Bookwarm Desktop 64bit(released: 2025-11-24, 2025-05-13, 2025-05-06)
..       - #. Trixie Desktop 64bit (released: 2025-12-04)
..         #. Bookwarm Desktop 64bit(released: 2025-11-24, 2025-05-13, 2025-05-06)

..     * - RetroPie
..       - No related system
..       - Yes (No touch)
..     * - Kali Linux
..       - Yes, kali-linux-2025.3-raspberry-pi-arm64
..       - Yes, kali-linux-2025.3-raspberry-pi-arm64
..     * - Ubuntu
..       - Yes, 
..       - Yes, Ubuntu Desktop 24.04.4 LTS
    

.. .. list-table::
..     :header-rows: 1

..     * - System / Board
..       - Pi 5
..       - Pi 4B
..       - Pi 3B/3B+
..       - Pi Zero 2 W
..     * - Raspberry Pi OS
..       - Yes, Debian Trixie 64bit system (released:2025-10-1)
..       - Yes, Debian Trixie 64bit system (released:2025-10-1)
..       - Yes, Bullseye OS 2022-09-06-raspios-bullseye
..       - Yes, Bullseye OS 2022-09-06-raspios-bullseye
..     * - RetroPie
..       - No related system
..       - Yes (No touch)
..       - Yes (No touch)
..       - Yes (No touch)
..     * - Kali Linux
..       - Yes, kali-linux-2025.3-raspberry-pi-arm64
..       - Yes, kali-linux-2025.3-raspberry-pi-arm64
..       - Yes, kali-linux-2025.3-raspberry-pi-arm64
..       - NO
..     * - Ubuntu
..       - Yes, Ubuntu Desktop/Server 64bit 25.04
..       - Yes, Ubuntu Desktop/Server 64bit 25.04
..       - Yes, Ubuntu Server 64bit 25.04/Ubuntu Server 64bit 24.04.2 LTS
..       - Yes, Ubuntu Server 64bit 25.04/Ubuntu Server 64bit 24.04.2 LTS
 
