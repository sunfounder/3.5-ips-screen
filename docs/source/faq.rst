.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

FAQ
===========================

Compatible Raspberry Pi Models
-------------------------------------------

Currently, the 3.5-inch display is only compatible with Raspberry Pi 4 and Raspberry Pi 5. For Raspberry Pi 3B, 3B+, and Zero 2W, it is not recommended to use them with the 3.5-inch display, as installing the touchscreen driver may cause it to malfunction.

Can this screen work on Ubuntu, Kali Linux, or RetroPie?
-----------------------------------------------------------------

Yes, but only with specific OS versions.  
If you install an unsupported version, the screen may not work after installing the driver.

Supported systems:

* **Raspberry Pi OS**

  - Trixie Desktop (64-bit) (released: 2025-12-04)
  - Bookworm Desktop (64-bit) (released: 2025-11-24, 2025-05-13, 2025-05-06)

    After installing the driver on Bookworm, run ``startx`` to enter the desktop environment.

* **Ubuntu**

  - |link_ubuntu_2404| (Raspberry Pi 4 only)

* **Kali Linux**

  - |link_kali_202503|

* **RetroPie**

  - |link_retropie| (Raspberry Pi 4 only)

Why does my screen stay black or white after powering on?
--------------------------------------------------------------------

* Make sure the correct driver is installed. See :ref:`install_driver`.
* Ensure your operating system is compatible. See :ref:`install_os`.
* Check that the screen is properly connected to the GPIO pins.

Can I use the 3.5'' IPS screen together with an HDMI monitor?
--------------------------------------------------------------------------------

No. After installing the 3.5'' IPS screen driver, it is recommended to disconnect the HDMI monitor.

If the HDMI monitor remains connected, it may show a black screen or no display output.

Restore Display to HDMI
--------------------------

#. If you only installed the 3.5'' display driver and did not make other changes to the config.txt file, you can run the following command to restore:

   .. code-block:: bash

      cd LCD-show
      sudo ./system_restore.sh

   After restoration, the 3.5'' display will no longer work and the driver will need to be reinstalled. This method applies when your system is relatively clean or freshly set up.

#. If you have also modified the config.txt file, the safest method is to manually edit it:

   * Run the following command to open the config.txt file:

     .. code-block:: bash

        sudo nano /boot/config.txt

   * Scroll to the bottom and comment out the changes added by the 3.5'' display driver:

     .. code-block:: bash

        [all]
        hdmi_force_hotplug=1
        dtparam=i2c_arm=on
        dtparam=spi=on
        enable_uart=1
        dtoverlay=mhs35ips:rotate=90
        hdmi_group=2
        hdmi_mode=1
        hdmi_mode=87
        hdmi_cvt 480 320 60 6 0 0 0
        hdmi_drive=2

   * Press Ctrl+X, then Y, and Enter to save the file and exit.

   * Then reboot the Raspberry Pi. The HDMI display will work again.

   * If you want to restore the 3.5'' display, simply uncomment the lines above.
   
What if I get ``git not found`` or network errors during installation?
--------------------------------------------------------------------------------------

Make sure your Raspberry Pi is connected to the internet.

If Git is not installed, run:

* ``sudo apt update``
* ``sudo apt install git``

Then retry the installation.

Why is the screen orientation incorrect?
--------------------------------------------------------

You can fix the screen and touch orientation by running:

* ``cd LCD-show/``   (adjust the path depending on your OS)
* ``sudo ./rotate.sh 90``

Replace ``90`` with ``0``, ``180``, or ``270`` as needed.



Why does the fan keep spinning? Can it be controlled by software?
------------------------------------------------------------------------------------------

The fan header provides constant 5V power and does not support software control.  
The fan will always spin when connected.

What is the operating temperature range?
--------------------------------------------------------

The supported operating temperature is **-20°C to 60°C**.  
Avoid exceeding this range to prevent damage or reduced lifespan.

Remote Access Issues
---------------------

* **ssh: Could not resolve hostname ...**

  * Check that the hostname is correct.
  * If it still fails, use the Raspberry Pi’s IP address instead of ``<hostname>.local``.

* **The term 'ssh' is not recognized... (Windows)**

  * OpenSSH is not installed. Install it manually (see :ref:`openssh_powershell`),  
    or use a third-party SSH client (see :ref:`login_windows`).

* **Permission denied (publickey,password)**

  * Make sure you are using the correct username and password configured in Raspberry Pi Imager.

* **Connection refused**

  * Wait 1–2 minutes after powering on.
  * Confirm that SSH is enabled in Raspberry Pi Imager.
