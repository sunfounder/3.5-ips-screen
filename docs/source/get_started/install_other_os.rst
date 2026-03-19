.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_other_os:

Install Ubuntu / Kali Linux / RetroPie
==============================================

This section guides you through installing **Ubuntu, Kali Linux, or RetroPie** on your Raspberry Pi using Raspberry Pi Imager.

Required Components
------------------------------

* A computer (Windows, macOS, or Linux)
* A microSD card (16GB or larger; recommended: SanDisk, Samsung)
* A microSD card reader


Supported Operating Systems
-------------------------------

.. warning::

   * This guide applies only to the operating systems listed below.
   * If you use a different OS version, the 3.5'' IPS screen may NOT work properly after installing the driver.

* **Ubuntu**

  - |link_ubuntu_2404| (Raspberry Pi 4 only)

* **Kali Linux**

  - |link_kali_202503|

* **RetroPie**

  - |link_retropie| (Raspberry Pi 4 only)

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

#. Click **OS**:

   * Scroll to the bottom and select **Use Custom**.

     .. image:: img/imager_use_custom.png
        :width: 90%

   * Navigate to the folder where you downloaded the OS image, then select the image file.

     .. image:: img/imager_custom_os.png
        :width: 90%

#. In the **Storage** section, select your microSD card.

   .. image:: img/imager_storage.png
      :width: 90%

#. Review all settings and click **WRITE**.

   .. image:: img/imager_writing_ubuntu.png
      :width: 90%

#. If the card already contains data, Raspberry Pi Imager will display a warning that all data will be erased.  
   Confirm that you selected the correct drive, then click **I UNDERSTAND, ERASE AND WRITE**.

   .. image:: img/imager_erase.png
      :width: 90%

#. Wait for the writing and verification process to complete. When finished, you will see **Write complete!**  
   The storage device will be safely ejected automatically.

   .. image:: img/imager_finish_ubuntu.png
      :width: 90%

#. Remove the microSD card and insert it into your Raspberry Pi.  
   Your Raspberry Pi is now ready to boot with the new operating system.

   .. image:: img/os_sd_to_pi.jpg
      :width: 70%