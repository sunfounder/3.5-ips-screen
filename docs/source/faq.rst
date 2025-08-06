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

Why does my 3.5-inch screen stay black or white after powering on?
--------------------------------------------------------------------

* Make sure the correct driver is installed. For the first installation, use an HDMI monitor or remote login.  
* If you are using **Raspberry Pi OS** on Raspberry Pi 3, 2, 1, Zero, or Zero 2 W boards, you must install **Bullseye** instead of **Bookworm** to ensure compatibility.  
* Ensure the screen is firmly connected and properly aligned with the GPIO pins.

Touch orientation is incorrect after driver installation, what should I do?
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
