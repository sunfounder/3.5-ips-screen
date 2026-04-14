.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_os:

2. Install the Operating System
===========================================

This section guides you through installing a compatible operating system on your Raspberry Pi.  
Different systems are supported depending on your Raspberry Pi model and use case.

.. note::

    Currently, the 3.5-inch display is only compatible with Raspberry Pi 4 and Raspberry Pi 5. For Raspberry Pi 3B, 3B+, and Zero 2W, it is not recommended to use them with the 3.5-inch display, as installing the touchscreen driver may cause it to malfunction.

    * For **Raspberry Pi OS**:

      - Trixie Desktop (64-bit) (released: 2025-12-04)
      - Bookworm Desktop (64-bit) (released: 2025-11-24, 2025-05-13, 2025-05-06)

        After installing the driver on Bookworm, you need to run ``startx`` to enter the desktop environment.

    * For **Ubuntu**:

      - |link_ubuntu_2404| (Raspberry Pi 4 only)

    * For **Kali Linux**:

      - |link_kali_202503|

    * For **RetroPie**:

      - |link_retropie| (Raspberry Pi 4 only)

.. toctree::
    :maxdepth: 1

    install_rpi_os
    install_other_os