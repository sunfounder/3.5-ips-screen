.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_driver_kali:

Install 3.5'' IPS Screen Driver on Kali
===============================================

This section guides you through installing the 3.5'' IPS screen driver on **Kali Linux**.  
You will log in to the system, open a terminal, and install the driver to enable display output on the 3.5'' IPS screen.

Install 3.5'' IPS Screen Driver (Important)
--------------------------------------------------

#. Connect your Raspberry Pi to a monitor and power it on.  
   Make sure an Ethernet cable is connected for network access.

#. Log in using the default Kali credentials:

   * Username: ``kali``
   * Password: ``kali``

   After logging in, search for and open the **Terminal**.

#. Open the built-in Firefox browser and visit:

   ``35-ips-screen.rtfd.io``

#. Copy and run the following commands in the Terminal one by one to install the driver:

   .. code-block:: shell
   
      sudo rm -rf LCD-show-kali
      git clone https://github.com/sunfounder/LCD-show-kali.git
      chmod -R 755 LCD-show-kali
      cd LCD-show-kali/
      sudo ./MHS35IPS-show

#. After the installation is complete:

   * Disconnect the HDMI monitor.
   * The Raspberry Pi will reboot automatically.
   * After rebooting, the system will be displayed on the 3.5'' IPS screen.

Rotate the Display
-----------------------------

You can change the screen and touch orientation by running:

.. code-block:: shell

    cd LCD-show-kali/
    sudo ./rotate.sh 90

The system will reboot automatically. After restart, the display and touch direction will be rotated to **90°**.  
You can replace ``90`` with ``0``, ``180``, or ``270`` to set your desired orientation.