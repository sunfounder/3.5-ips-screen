.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message
   
.. _install_os:

Installing Raspberry Pi OS
===================================

Before using your Raspberry Pi, you need to install **Raspberry Pi OS** onto a microSD card.  
This section provides a simple, step-by-step guide using **Raspberry Pi Imager**, suitable for beginners.

Supported Models and OS Versions
-------------------------------------

.. warning::

   * This guide applies only to the models and OS versions listed below.
   * Using other versions may cause the 3.5'' IPS screen to not work properly after driver installation.

* **Supported models**:

  - Raspberry Pi 5
  - Raspberry Pi 4 Model B

* **Verified compatible OS versions**:

  - **Trixie Desktop (64-bit)** (released: 2025-12-04)
  - **Bookworm Desktop (64-bit)** (released: 2025-11-24, |link_bookwarm_250513|)

    After installing the driver on Bookworm, you need to run ``startx`` to enter the desktop environment.

Required Components
------------------------------

* A computer (Windows, macOS, or Linux)
* A microSD card (16GB or larger; recommended: SanDisk, Samsung)
* A microSD card reader

-------------------

1. Install Raspberry Pi Imager
-------------------------------------------

#. Visit the official Raspberry Pi Imager download page: |link_rpi_imager| and download the version for your operating system.

   .. image:: img/imager_download.png
      :width: 70%

#. Follow the installation instructions (language, installation path, confirmation). After installation, launch **Raspberry Pi Imager**.

   .. image:: img/imager_install.png
      :width: 90%

--------------------------------------

2. Flash the OS to the microSD Card
------------------------------------------------

#. Insert the microSD card into your computer using a card reader. Back up any important data before proceeding.

   .. image:: img/insert_sd.png
      :width: 90%

#. Open Raspberry Pi Imager and select your device (e.g., Raspberry Pi 5 or Raspberry Pi 4).

   .. image:: img/imager_device.png
      :width: 90%

#. Click **OS** and choose the system:

   * For **Trixie**, simply select the recommended version.
   * For **Bookworm**, go to: **Raspberry Pi OS (Other) → Raspberry Pi OS (Legacy, 64-bit)**

   .. image:: img/imager_os.png
      :width: 90%

4. In the **Storage** section, select your microSD card. 

   .. image:: img/imager_storage.png
      :width: 90%

5. Click **Next** to continue to the customization step.

   .. note::

      * If you will connect a monitor, keyboard, and mouse directly to your Raspberry Pi, you may click **SKIP CUSTOMISATION**.  
      * If you plan to set up the Raspberry Pi *headless* (Wi-Fi remote access), you must complete the customization settings.

   .. image:: img/imager_custom_skip.png
      :width: 90%

-------------------

.. _imager_custom:

3. OS Customization Settings
------------------------------------------

#. **Set Hostname**

   * Give your Raspberry Pi a unique hostname.  
   * You can connect to it later using ``hostname.local``.

   .. image:: img/imager_custom_hostname.png
      :width: 90%

#. **Set Localisation**

   * Choose your capital city.
   * Imager will auto-complete the time zone and keyboard layout based on your selection, though you can adjust them if needed. Select Next.
   
   .. image:: img/imager_custom_local.png
      :width: 90%

#. **Set Username & Password**

   Create a user account for your Raspberry Pi.
   
   .. image:: img/imager_custom_user.png
      :width: 90%

#. **Configure Wi-Fi**

   * Enter your Wi-Fi **SSID** (network name) and **password**.  
   * Your Raspberry Pi will automatically connect on first boot.
   
   .. image:: img/imager_custom_wifi.png
      :width: 90%

#. **Enable SSH (Optional but Recommended)**

   * Enabling SSH allows you to remotely log in from your computer.  
   * You may log in using your username/password or configure SSH keys.
   
   .. image:: img/imager_custom_ssh.png
      :width: 90%

#. **Enable Raspberry Pi Connect (Optional)**

   Raspberry Pi Connect allows you to access your Raspberry Pi desktop from a web browser.
   
   * Turn on **Raspberry Pi Connect**, then click **OPEN RASPBERRY PI CONNECT**.
   
     .. image:: img/imager_custom_connect.png
        :width: 90%

   * The Raspberry Pi Connect website will open in your default browser. Log in to your Raspberry Pi ID account, or sign up if you don’t have one yet.

     .. image:: img/imager_custom_open.png
        :width: 90%

   * On the **New auth key** page, create your one-time auth key. 
      
      * If your Raspberry Pi ID account isn’t part of any organisation, select **Create auth key and launch Raspberry Pi Imager**.
      * If you belong to one or more organisations, choose one, then create the key and launch Imager.
      * Make sure to power on your Raspberry Pi and connect it to the internet before the key expires.
   
     .. image:: img/imager_custom_authkey.png
        :width: 90%
   
   * Your browser may ask to open Raspberry Pi Imager — allow it.

     * Imager will open on the Raspberry Pi Connect tab, showing the authentication token.
     * If the token doesn’t transfer automatically, open the **Having trouble?** section on the Raspberry Pi Connect page, copy the token, and paste it into Imager manually.

     .. image:: img/imager_custom_connect_token.png
        :width: 90%

-------------------


4. Write the OS Image
-----------------------------


#. Review all settings and click **WRITE**.

   .. image:: img/imager_writing.png
      :width: 90%

#. If the card already contains data, Raspberry Pi Imager will show a warning that all data on the device will be erased. Double-check that you selected the correct drive, then click **I UNDERSTAND, ERASE AND WRITE** to continue.

   .. image:: img/imager_erase.png
      :width: 90%

#. Wait for the writing and verification to finish. When it is done, Raspberry Pi Imager will show **Write complete!** and a summary of your choices. The storage device will be ejected automatically so you can remove it safely.


   .. image:: img/imager_finish.png
        :width: 90%

#. Remove the microSD card and insert it into the slot on the underside of your Raspberry Pi. Your Raspberry Pi is now ready to boot with the new OS!

   .. image:: img/os_sd_to_pi.jpg
        :width: 70%

