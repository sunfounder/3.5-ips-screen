.. note::

    Hello, welcome to the SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts Community on Facebook! Dive deeper into Raspberry Pi, Arduino, and ESP32 with fellow enthusiasts.

    **Why Join?**

    - **Expert Support**: Solve post-sale issues and technical challenges with help from our community and team.
    - **Learn & Share**: Exchange tips and tutorials to enhance your skills.
    - **Exclusive Previews**: Get early access to new product announcements and sneak peeks.
    - **Special Discounts**: Enjoy exclusive discounts on our newest products.
    - **Festive Promotions and Giveaways**: Take part in giveaways and holiday promotions.

    👉 Ready to explore and create with us? Click [|link_sf_facebook|] and join today!

Hardware Description
===========================

**Parameters**

.. list-table::
    :header-rows: 1

    * - Parameter
      - Description
    * - Screen Size
      - 3.5-inch
    * - LCD Type
      - IPS
    * - Viewing Angle
      - Full Viewing Angle
    * - Module Interface
      - SPI (Supports up to 125MHz SPI input)
    * - Resolution
      - 320×480 (Pixel)
    * - Number of Pins
      - 40-pin (Same as the Raspberry Pi)
    * - Colors
      - 65K
    * - Touch Screen Controller
      - XPT2046
    * - LCD Driver IC
      - ST7796U
    * - Backlight
      - LED
    * - Power Consumption
      - 0.16A × 5V
    * - Working Temperature (℃)
      - -20 ~ 60
    * - Active Area
      - 48.96 × 73.44 (mm)
    * - Module PCB Size
      - 85.42 × 55.60 (mm)
    * - Package Size
      - 132 × 96 × 40 (mm)
    * - Product Weight (Including Package)
      - 93.8 g

**Interface Definition**

Here is the pinout diagram for the 3.5-inch IPS screen. In reality, only the first 26 pins are connected. Pins 27–40 are not connected; they are only there to be compatible with the current 40-pin Raspberry Pi models and to reduce the chance of incorrect insertion.

.. image:: img/3.5_ips_pins.png
  :width: 500
  :align: center

.. list-table:: 
    :header-rows: 1

    * - PIN NO.
      - SYMBOL
      - DESCRIPTION
    * - 1, 17
      - 3.3V
      - Power supply input (3.3V)
    * - 2, 4
      - 5V
      - Power supply input (5V)
    * - 3, 5, 7, 8, 10, 12, 13, 15, 16, 27~40
      - NC
      - Not connected
    * - 6, 9, 14, 20, 25
      - GND
      - Power ground
    * - 11
      - TP_IRQ
      - Touch panel interrupt signal, active low when pressed
    * - 18
      - LCD_RS
      - LCD register select signal (low: instruction, high: data)
    * - 19
      - LCD_SI / TP_SI
      - SPI data input for LCD display / touch panel
    * - 21
      - TP_SO
      - SPI data output from the touch panel
    * - 22
      - RST
      - Reset signal, active low
    * - 23
      - LCD_SCK / TP_SCK
      - SPI clock signal for LCD display / touch panel
    * - 24
      - LCD_CS
      - LCD chip select signal, active low
    * - 26
      - TP_CS
      - Touch panel chip select signal, active low


**Fan Pins**

On the back of the screen, there are two fan pins that allow you to connect an external fan. However, once the fan is connected, it will run continuously and cannot be controlled by code.

.. image:: img/3.5_ips_fan_pins.png
  :width: 400
  :align: center

