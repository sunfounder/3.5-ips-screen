.. note::

    Hello, welcome to the SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts Community on Facebook! Dive deeper into Raspberry Pi, Arduino, and ESP32 with fellow enthusiasts.

    **Why Join?**

    - **Expert Support**: Solve post-sale issues and technical challenges with help from our community and team.
    - **Learn & Share**: Exchange tips and tutorials to enhance your skills.
    - **Exclusive Previews**: Get early access to new product announcements and sneak peeks.
    - **Special Discounts**: Enjoy exclusive discounts on our newest products.
    - **Festive Promotions and Giveaways**: Take part in giveaways and holiday promotions.

    👉 Ready to explore and create with us? Click [|link_sf_facebook|] and join today!

Quick User Guide
===========================

1. Install the Operating System
--------------------------------------

Use **Raspberry Pi Imager** to install the operating system that matches your Raspberry Pi board model.

For detailed instructions, please refer to :ref:`install_os`.

.. note::

    * For the **Raspberry Pi OS**: 

      - If you are using a **Raspberry Pi 4 or 5**, please Go to Raspberry Pi Imager to install the latest Trixie system (released:2025-10-1).     
      - If you are using a **Raspberry Pi 3B/3B+ or Zero 2W**, please visit |link_bullseye| to download it.

    * For **Ubuntu** system, please Go to Raspberry Pi Imager and select either **Ubuntu Desktop 24.04 LTS (64 bit)** or **Ubuntu Server 24.04 LTS (64 bit)**.
    
    * For **Kali Linux** system, please visit |link_kali_linux| to download it.

    * For the **Retropie** system, please download the version for your Raspberry Pi (not Pi 5) from the |link_retropie| .

2. Connect the Display to the Raspberry Pi
-----------------------------------------------

This 3.5-inch IPS display shares the same pinout as the Raspberry Pi.

**Steps**: 

1. Power off your Raspberry Pi and unplug the power cable.  
2. Align the display with the GPIO header (Pin 1 alignment) and firmly press it onto the pins.  
3. Insert the prepared MicroSD card and power on the Raspberry Pi.

.. image:: img/3.5_ips_plugin_pi.jpg
    :width: 400
    :align: center

.. _install_driver:

3. Driver Installation
-------------------------------

The 3.5-inch IPS display requires drivers before it can function. Depending on your operating system, follow the instructions below.

**General tips**: 

* First, check :ref:`compatible_os`.
* Ensure ``git`` is installed (``sudo apt install git``).  
* Driver installation may take 1–3 minutes.  
* The system will reboot automatically.

**For Raspberry Pi OS**

.. warning::

      - If you are using a **Raspberry Pi 4 or 5**, please Go to Raspberry Pi Imager to install the latest Trixie system (released:2025-10-1).  
      - If you are using a **Raspberry Pi 3B/3B+ or Zero 2W**, please visit |link_bullseye| to download it.

    * Do not run `sudo apt update` or `sudo apt upgrade` after installation, as this may update the kernel and break the display driver.


You can use the following command to install the driver:

.. raw:: html

   <run></run>

.. code-block:: shell


    sudo rm -rf LCD-show
    git clone https://github.com/sunfounder/LCD-show.git
    chmod -R 755 LCD-show
    cd LCD-show/
    sudo ./MHS35IPS-show

After the driver is successfully installed, it will take 2–3 minutes to reboot. Then you will be able to see the Raspberry Pi desktop on the 3.5-inch IPS screen.

.. note::

    * If you have an HDMI monitor connected during installation, the desktop will still appear on the HDMI monitor after reboot.
    * To use the 3.5-inch IPS screen, disconnect the HDMI monitor and reboot the Raspberry Pi.

**For Ubuntu Desktop/Server**

You can use the following command to install the driver:

.. raw:: html

   <run></run>

.. code-block:: shell

    sudo rm -rf LCD-show-ubuntu
    git clone https://github.com/sunfounder/LCD-show-ubuntu.git
    chmod -R 755 LCD-show-ubuntu
    cd LCD-show-ubuntu/
    sudo ./MHS35IPS-show

After the driver is successfully installed, the system will automatically reboot, and the desktop will be displayed on the 3.5-inch IPS screen.

.. note::

    * If an HDMI monitor is connected, the desktop will still default to the HDMI output.
    * Please unplug the HDMI monitor and reboot your device to switch the display to the 3.5-inch IPS screen.


**For Kali Linux**

You can use the following command to install the driver:

.. raw:: html

   <run></run>

.. code-block:: shell

    sudo rm -rf LCD-show-kali
    git clone https://github.com/sunfounder/LCD-show-kali.git
    chmod -R 755 LCD-show-kali
    cd LCD-show-kali/
    sudo ./MHS35IPS-show

After the driver is successfully installed, the system will reboot and show the desktop on the 3.5-inch IPS screen.

.. note::

    * When an HDMI monitor is connected, the desktop will continue to display on HDMI after reboot.
    * Please disconnect the HDMI monitor and reboot Kali Linux to use the 3.5-inch IPS screen.

**For RetroPie**

.. note::

    * For the **Retropie** system, please download the version for your Raspberry Pi (not Pi 5) from the |link_retropie|.

You can use the following command to install the driver:

.. raw:: html

   <run></run>

.. code-block:: shell

    sudo rm -rf LCD-show-retropie
    git clone https://github.com/sunfounder/LCD-show-retropie.git
    chmod -R 755 LCD-show-retropie
    cd LCD-show-retropie/
    sudo ./MIS35-show

After the driver is successfully installed, the system will reboot, and you will see the RetroPie interface on the 3.5-inch IPS screen.

.. note::

    * If an HDMI monitor is connected, the interface will remain on HDMI output.
    * Unplug the HDMI monitor and reboot your Raspberry Pi to switch the display to the 3.5-inch IPS screen.

4.Rotate the Display
-----------------------------

You can rotate the display and touch orientation by running:

.. note::

    Change the directory according to the system used:  
    
    * Raspberry Pi OS → ``cd LCD-show/``  
    * Ubuntu → ``cd LCD-show-ubuntu/``  
    * Kali → ``cd LCD-show-kali/``  
    * RetroPie → ``cd LCD-show-retropie/``

.. raw:: html

   <run></run>

.. code-block:: shell

    cd LCD-show/
    sudo ./rotate.sh 90

The system will reboot automatically. After restart, the screen and touch orientation will be rotated to **90°**.  
You can replace ``90`` with ``0``, ``180``, or ``270`` to set the desired rotation.
