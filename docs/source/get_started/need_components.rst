.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

1. What Else Do You Need?
===============================

Before we start using this screen, let’s prepare the essential hardware.

Required Components
------------------------------

* **Raspberry Pi**

  * **Compatible models**: Raspberry Pi 5, Raspberry Pi 4 Model B
  * Other Raspberry Pi models are not supported.

  .. image:: img/need_pi.jpg

* **Power Adapter**

  Different Raspberry Pi models require different power supplies.  
  For best stability, it is recommended to use the official power adapter:

  * **Raspberry Pi 5**: Recommended: **5V 5A USB-C power supply** (Official 27W PSU). You may also use a USB-C Power Delivery (PD) charger, as long as it provides sufficient current.

  * **Raspberry Pi 4 Model B**: Recommended: **5V 3A USB-C power supply** (Official 15W PSU). You may also use a USB-C PD or QC 2.0 fast charger.

  .. image:: img/need_power.png
    :width: 400

* **Micro SD Card**

  The Raspberry Pi does not include built-in storage. It boots and stores all data on a **Micro SD card**.

  .. image:: img/need_sd.jpg
    :width: 200

  * Minimum: **16GB**
  * Recommended: **32GB** or higher for better performance and stability
  * Recommended brands: **SanDisk**, **Samsung**

Optional Components
------------------------

Although not strictly required, the following peripherals will significantly improve your setup and debugging experience:

* **Monitor (HDMI or TV)**

  For beginners, we strongly recommend using a display with an HDMI input. This makes it easier to configure the system and run graphical programs.

  .. image:: img/need_screen.png
    :width: 400

* **Micro HDMI Cable**

  * The Raspberry Pi 4B and Raspberry Pi 5 require a **Micro HDMI cable** to connect to a display.  
  * It is recommended to use the **HDMI0 port** (the one closest to the USB-C power port).

  .. image:: img/need_hdmi.png
    :width: 400

* **Keyboard & Mouse**

  * These are very useful during the initial OS setup.  
  * You can switch to remote access (SSH/VNC) later, but for beginners, a basic USB or wireless keyboard and mouse are highly recommended.

  .. image:: img/need_keyboard_mouse.png
    :width: 500