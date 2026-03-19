.. include:: /index.rst
   :start-after: start_hello_message
   :end-before: end_hello_message

.. _install_driver_retropie:

Install 3.5'' IPS Screen Driver on RetroPie
===============================================

This section explains how to install the 3.5'' IPS screen driver on the **RetroPie** system.  
You will first access your Raspberry Pi via SSH, and then install the driver so that the RetroPie interface can be displayed on both the HDMI monitor and the 3.5'' screen.

Install 3.5'' IPS Screen Driver (Important)
--------------------------------------------------

#. Connect your Raspberry Pi to a monitor and power it on. Make sure an Ethernet cable is also connected so the device can access the network.

   .. image:: img/connect_all_retropie.jpg
      :width: 90%

#. Once the RetroPie interface appears, press **F4** on the keyboard to exit and enter the command line interface.

#. To enable SSH, run the following command:

   .. code-block:: shell
   
       sudo raspi-config
   
   In the menu, navigate to: **Interface Options** → **SSH** → **Enable**.

#. (Optional) If you want to connect using an IP address, you can check it by running:

   .. code-block:: shell

       hostname -I

   You will see output similar to:

   .. code-block:: text

       192.168.100.119 xxxx.xxx

#. On your computer, open a terminal and connect to the Raspberry Pi via SSH using one of the following methods:

   * **Using hostname (recommended):**

     .. code-block:: shell

         ssh pi@retropie.local

   * **Using IP address:**

     .. code-block:: shell

         ssh pi@IP_ADDRESS

     For example:

     .. code-block:: shell

         ssh pi@192.168.100.119

   When connecting for the first time, type ``yes`` to confirm, then enter the default password:

   .. code-block:: text

       raspberry

#. After logging in, run the following commands to install the 3.5'' IPS screen driver:

   .. note::
   
       * For the **RetroPie** system, make sure you are using the version provided in |link_retropie| (Raspberry Pi 4 only).

   .. code-block:: shell
   
       sudo rm -rf LCD-show-retropie
       git clone https://github.com/sunfounder/LCD-show-retropie.git
       chmod -R 755 LCD-show-retropie
       cd LCD-show-retropie/
       sudo ./MHS35IPS-show

#. Once the installation is complete, the Raspberry Pi will reboot automatically.

   * After rebooting, both the HDMI monitor and the 3.5'' IPS screen will display the RetroPie interface.
   * The startup process may take 1–2 minutes, so please wait patiently.

Rotate the Display
-----------------------------

You can rotate the display and touch orientation by running:



.. code-block:: shell

    cd LCD-show-retropie/
    sudo ./rotate.sh 90

The system will reboot automatically. After restart, the screen and touch orientation will be rotated to **90°**.  
You can replace ``90`` with ``0``, ``180``, or ``270`` to set the desired rotation.
