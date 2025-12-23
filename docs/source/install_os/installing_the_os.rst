.. note::

    Hello, welcome to the SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts Community on Facebook! Dive deeper into Raspberry Pi, Arduino, and ESP32 with fellow enthusiasts.

    **Why Join?**

    - **Expert Support**: Solve post-sale issues and technical challenges with help from our community and team.
    - **Learn & Share**: Exchange tips and tutorials to enhance your skills.
    - **Exclusive Previews**: Get early access to new product announcements and sneak peeks.
    - **Special Discounts**: Enjoy exclusive discounts on our newest products.
    - **Festive Promotions and Giveaways**: Take part in giveaways and holiday promotions.

    👉 Ready to explore and create with us? Click [|link_sf_facebook|] and join today!


.. _install_os_sd:

2. Installing the OS
============================================================

To get your Raspberry Pi ready, you first need to install the Raspberry Pi OS onto a Micro SD card.  
This section will guide you through the process step by step.

.. note::

    * For the **Raspberry Pi OS**: 

      - If you are using a **Raspberry Pi 4 or 5**, please Go to Raspberry Pi Imager to install the latest Trixie system (released:2025-10-1).     
      - If you are using a **Raspberry Pi 3B/3B+ or Zero 2W**, please visit |link_bullseye| to download it.
      - Other Raspberry Pi models are not compatible.
  
    * For **Ubuntu** system, please Go to Raspberry Pi Imager and select either **Ubuntu Desktop 24.04 LTS (64 bit)** or **Ubuntu Server 24.04 LTS (64 bit)**.
    
    * For **Kali Linux** system, please visit |link_kali_linux| to download it.

    * For the **Retropie** system, please download the version for your Raspberry Pi (not Pi 5) from the |link_retropie| .

**Required Components**

* A Personal Computer (Windows, macOS, or Linux)
* A Micro SD card (≥16GB, reliable brand such as Sandisk or Samsung)
* A Micro SD card Reader

----

**1. Install Raspberry Pi Imager**

#. Open the official Raspberry Pi download page: |link_rpi_imager|.  

   Download the correct version for your operating system (Windows, macOS, or Ubuntu).  

   .. image:: img/os_install_imager.png
       :align: center

#. After installation, launch Raspberry Pi Imager by clicking the desktop icon or searching for ``Raspberry Pi Imager`` in your system’s menu.  

   .. image:: img/os_open_imager.png
       :align: center

**2. Install OS to Micro SD Card**

#. Insert your Micro SD card into your computer using a card reader. Make sure the card is empty or that you have backed up any important data.

#. In Imager, first click **Choose Device** and select your Raspberry Pi model. (e.g., Raspberry Pi 5, Raspberry Pi 4B, 3B/3B+ or Zero 2W).  

   .. image:: img/os_choose_device.png
       :align: center

#. Click on the **Operating System** tab to select the operating system.

   .. note::

      * For **Raspberry Pi OS**, Select the corresponding operating system based on your Raspberry Pi model.

        - If you are using a **Raspberry Pi 4 or 5**, please Go to Raspberry Pi Imager to install the latest Trixie system (released:2025-10-1).    
        - If you are using a **Raspberry Pi 3B/3B+ or Zero 2W**, please visit |link_bullseye| to download it.

      * For **Ubuntu** system, you need to click **Other general-purpose OS** -> **Ubuntu**, and select either **Ubuntu Desktop 24.04 LTS (64 bit)** or **Ubuntu Server 24.04 LTS (64 bit)**.
      * For **Kali Linux** system, you need to click **use custom** and then select the corresponding system |link_kali_linux|.
      * For **Retropie** system, you need to click **use custom** and then select the corresponding Retropie system based on your Raspberry Pi model, please download the version for your Raspberry Pi (not Pi 5) from the |link_retropie| .

   .. image:: img/os_choose_os.png
       :align: center

#. Click **Choose Storage** and select your Micro SD card. To avoid mistakes, unplug other USB drives so only the SD card is listed.

   .. note::

      Be very careful when selecting the storage device. Choosing the wrong disk could erase important data.

   .. image:: img/os_choose_sd.png
       :align: center

#. Click **Next**, then choose **EDIT SETTINGS** to configure your Raspberry Pi before writing.  

   .. note::

        * If you plan to use a monitor, keyboard, and mouse directly with your Raspberry Pi, you can skip advanced settings and just click **Yes** to start writing. 
        * For systems that cannot be configured in advance, after clicking **NEXT**, you will be prompted whether to save the data within the device. If you have confirmed that a backup has been made, select **Yes**.
        * For systems where the Hostname, WiFi, and Enable SSH can be configured in advance, a pop-up will appear prompting whether to apply the OS's custom settings. You can choose **Yes** or **No**, or go back to edit further.

   .. image:: img/os_enter_setting.png
       :align: center

----

**3. OS Customization Settings**

* **Set Hostname**:  

  * Choose a unique name for your Pi.  
  * You can later access it in the network as ``<hostname>.local``.  

  .. image:: img/os_set_hostname.png
      :align: center

* **Set Username & Password**: 

  * Create a secure login for your Pi.  
  * Unlike older OS versions, Raspberry Pi no longer provides a default account.

  .. image:: img/os_set_username.png
      :align: center

* **Configure Wi-Fi**:

  * Enter your Wi-Fi **SSID** (network name) and **Password**.  
  * Set the correct **Wireless LAN country** using the |link_iso_code| (e.g., US, UK, CN); otherwise Wi-Fi will not work.

  .. image:: img/os_set_wifi.png
      :align: center

* **Enable SSH (Optional but Recommended)**: 

  This allows remote access from your PC. You can log in using the username/password, or set up public-key authentication.  

  .. image:: img/os_enable_ssh.png
      :align: center

* **Other Options**:  
  
  You may enable "Play sound when finished" or "Eject media when finished" for convenience.  

  .. image:: img/os_options.png
      :align: center

----

**4. Write the OS Image**

#. After customizing, click **Save**, then **Yes** to apply settings.  

   .. image:: img/os_click_yes.png
       :align: center

#. If your card has existing data, confirm by clicking **Yes** to overwrite.  

   .. image:: img/os_continue.png
       :align: center

#. Wait until the writing and verification process is complete. This may take several minutes. Once finished, you will see **Write Successful**.  

   .. image:: img/os_finish.png
       :align: center


#. Finally, remove the SD card from the reader and insert it into the slot on the underside of your Raspberry Pi. Your Raspberry Pi is now ready to boot with the new OS installed!

   .. image:: img/os_sd_to_pi.jpg
      :width: 500
      :align: center

