.. note::

    Hello, welcome to the SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts Community on Facebook! Dive deeper into Raspberry Pi, Arduino, and ESP32 with fellow enthusiasts.

    **Why Join?**

    - **Expert Support**: Solve post-sale issues and technical challenges with help from our community and team.
    - **Learn & Share**: Exchange tips and tutorials to enhance your skills.
    - **Exclusive Previews**: Get early access to new product announcements and sneak peeks.
    - **Special Discounts**: Enjoy exclusive discounts on our newest products.
    - **Festive Promotions and Giveaways**: Take part in giveaways and holiday promotions.

    👉 Ready to explore and create with us? Click [|link_sf_facebook|] and join today!

FAQ
===========================

Does the 3.5'' touchscreen support the Raspberry Pi Trixie system?  
------------------------------------------------------------------------------------

The 3.5'' touchscreen is not yet supported on the **Trixie** system. We’re updating the driver soon.  

- If you are using a **Raspberry Pi 4 or 5**, please install the older |link_bookwarm_rpi5/4| system.  
- If you are using a **Raspberry Pi 3B/3B+ or Zero 2W**, you must install the |link_bullseye| system.
- Do not run ``sudo apt update`` or ``sudo apt upgrade`` after installation, as this may update the kernel and break the display driver.

Why can’t I log in after installing the 3.5-inch display driver?
------------------------------------------------------------------------------------

This issue is usually caused by a **kernel update**.  
Updating the system after installation may upgrade the kernel and make the display driver incompatible.  
Avoid running ``sudo apt update`` or ``sudo apt upgrade`` to prevent login issues.


Why does my 3.5-inch screen stay black or white after powering on?
--------------------------------------------------------------------

* Make sure the correct driver is installed. For detailed instructions, please refer to :ref:`install_driver`.
* If you are using **Raspberry Pi OS** on Raspberry Pi 3B/3B+ or Zero 2W boards, you must install **Bullseye** instead of **Bookworm** to ensure compatibility.  
* Ensure the screen is firmly connected and properly aligned with the GPIO pins.

Can the 3.5'' IPS touchscreen and the HDMI monitor be used simultaneously?
--------------------------------------------------------------------------------

The 3.5-inch touchscreen cannot be used simultaneously with an HDMI monitor.

After installing the driver for the 3.5" IPS display, if both the 3.5" IPS screen and an HDMI monitor are connected, the system will default to HDMI output.

To display on the 3.5" IPS touchscreen, disconnect (unplug) the HDMI monitor.

Screen orientation is incorrect?
-----------------------------------------------------------------------------------

Run the rotation script to fix it: 

* ``cd LCD-show/``   # adjust path for your OS  
* ``sudo ./rotate.sh 90``

Replace ``90`` with ``0``, ``180``, or ``270`` to match your desired orientation.

Can I use it without installing drivers?
-------------------------------------------

No. This screen uses an SPI interface and requires a dedicated driver to work properly.

For detailed instructions, please refer to :ref:`install_driver`.

Why does the fan keep spinning after connecting? Can it be controlled by code?
------------------------------------------------------------------------------------------

The fan header on the back provides direct 5V power and has no software control. The fan will always spin when connected.

What if I get ``git not found`` or network errors during driver installation?
--------------------------------------------------------------------------------------

Make sure the Raspberry Pi is connected to the internet.

If git is missing, run:  
        
* ``sudo apt update``  
* ``sudo apt install git``  

Then re-run the installation steps.

Can this screen work on Ubuntu, Kali or RetroPie?
-----------------------------------------------------------------

Yes, but it requires installing specific drivers.

For detailed instructions, please refer to :ref:`install_driver`.


Can it operate under extreme temperatures?
--------------------------------------------------------

The operating temperature range is -20°C to 60°C. Do not exceed this range to avoid damage or shortened lifespan.

What if I see color distortion on the screen?
----------------------------------------------------------

On systems like Kali Linux, use the ``MHS35IPS-show`` driver or update to the latest tested version (e.g., 2025.8.04) for better compatibility.
