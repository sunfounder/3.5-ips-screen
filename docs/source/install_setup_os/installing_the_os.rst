.. note::

    Hello, welcome to the SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts Community on Facebook! Dive deeper into Raspberry Pi, Arduino, and ESP32 with fellow enthusiasts.

    **Why Join?**

    - **Expert Support**: Solve post-sale issues and technical challenges with help from our community and team.
    - **Learn & Share**: Exchange tips and tutorials to enhance your skills.
    - **Exclusive Previews**: Get early access to new product announcements and sneak peeks.
    - **Special Discounts**: Enjoy exclusive discounts on our newest products.
    - **Festive Promotions and Giveaways**: Take part in giveaways and holiday promotions.

    👉 Ready to explore and create with us? Click [|link_sf_facebook|] and join today!

.. _install_os:

Installing the OS
=======================

**Required Components**

* Raspberry Pi 5
* A Personal Computer
* A Micro SD card 

**Installation Steps**

#. Visit the Raspberry Pi software download page at `Raspberry Pi Imager <https://www.raspberrypi.org/software/>`_. Choose the Imager version compatible with your operating system. Download and open the file to initiate installation.

    .. image:: img/os_install_imager.png

#. A security prompt may appear during installation, depending on your operating system. For example, Windows might display a warning message. In such cases, select **More info** and then **Run anyway**. Follow the on-screen guidance to complete the installation of the Raspberry Pi Imager.

    .. image:: img/os_info.png

#. Insert your SD card into your computer or laptop's SD card slot.

#. Within the **Raspberry Pi Imager**, click **Raspberry Pi Device** and select the Raspberry Pi model from the dropdown list.

   .. image:: img/os_choose_device.png
      :width: 90%
      

#. Click on the **Operating System** tab.

   .. image:: img/os_choose_os.png
      :width: 90%

#. Scroll down to the bottom of the page and select the your operating system.

   .. note::

      * For **Ubuntu** system, you need to click **Other general-purpose OS** -> **Ubuntu**, and select either **Ubuntu Desktop 24.04 LTS (64 bit)** or **Ubuntu Server 24.04 LTS (64 bit)**.
      * For **Kali Linux** system, you need to click **Other specific-purpose OS** and then select the corresponding system.
      * For **Retropie** system, you need to click **Emulation and game OS** and then select the corresponding system.

   .. image:: img/os_other_os.png
      :width: 90%

#. In the **Storage** option, select the appropriate storage device for the installation.

   .. image:: img/os_choose_sd.png
      :width: 90%
      

#. Click **NEXT**.

   .. note::

      * For systems that cannot be configured in advance, after clicking **NEXT**, you will be prompted whether to save the data within the device. If you have confirmed that a backup has been made, select **Yes**.

      * For systems where the Hostname, WiFi, and Enable SSH can be configured in advance, a pop-up will appear prompting whether to apply the OS's custom settings. You can choose **Yes** or **No**, or go back to edit further.

   .. image:: img/os_enter_setting.png
      :width: 90%
      

   * Define a **hostname** for your Raspberry Pi. The hostname is your Raspberry Pi's network identifier. You can access your Pi using ``<hostname>.local`` or ``<hostname>.lan``.

     .. image:: img/os_set_hostname.png  

   * Create a **Username** and **Password** for the Raspberry Pi's administrator account. Establishing a unique username and password is vital for securing your Raspberry Pi, which lacks a default password.

     .. image:: img/os_set_username.png
         
   * Configure the wireless LAN by providing your network's **SSID** and **Password**.

     .. note::

       Set the ``Wireless LAN country`` to the two-letter `ISO/IEC alpha2 code <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements>`_ corresponding to your location.

     .. image:: img/os_set_wifi.png
         
   * To remotely connect to your Raspberry Pi, enable SSH in the Services tab.

     * For **password authentication**, use the username and password from the General tab.
     * For public-key authentication, choose "Allow public-key authentication only". If you have an RSA key, it will be used. If not, click "Run SSH-keygen" to generate a new key pair.

     .. image:: img/os_enable_ssh.png
         
   * The **Options** menu lets you configure Imager's behavior during a write, including playing sound when finished, ejecting media when finished, and enabling telemetry.

     .. image:: img/os_options.png
           
#. When you've finished entering OS customisation settings, click **Save** to save your customisation. Then, click **Yes** to apply them when writing the image.

   .. image:: img/os_click_yes.png
      :width: 90%
      

#. If the SD card contains existing data, ensure you back it up to prevent data loss. Proceed by clicking **Yes** if no backup is needed.

   .. image:: img/os_continue.png
      :width: 90%
      

#. When you see the "Write Successful" popup, your image has been completely written and verified. You're now ready to boot a Raspberry Pi from the Micro SD Card!

