# May 23 2025:
Today i will be finding the USB PD negotiation IC. So basically i have the idea of making the smallest(that i can create) power module to power my electronics projects,
when i am prototyping.

okay, found the IC, it is [AP33772SDKZ-13-FA01](https://www.mouser.in/ProductDetail/Diodes-Incorporated/AP33772SDKZ-13-FA01?qs=2wMNvWM5ZX4CLYQ4%252BLyimw%3D%3D), and now i have another idea, let's make a variable power supply, which gives variable power supply if PPS is available, or else it gives constant supply @ 5V, 9V, 12V, 15V or 20V.

i think i am gonna use some microcontroller (probably an rp2040) along with an OLED that displays voltage and current, and also rotary encoders/potentiometers, although i haven't decided on that.

### Total Time Spent - 20 Mins

# May 24 2025:
Today, i made a block diagram by hand, and i selected the [ams1117 3.3v LDO regulator](https://lcsc.com/product-detail/Linear-Voltage-Regulators-LDO_Advanced-Monolithic-Systems-AMS1117-3-3_C6186.html) for the RP2040, but then i came to realise that the max input voltage for ams1117 is 15V, while max voltage with PD is 20V, so i chose another regulator(it is so hard to find a proper regulator). the new regulator now is [AMS1117S-3.3](https://lcsc.com/product-detail/Voltage-Regulators-Linear-Low-Drop-Out-LDO-Regulators_JSMSEMI-AMS1117S-3-3_C917152.html)

![Handmade Block Diagram](https://github.com/user-attachments/assets/e52aae66-0bd2-412d-a26d-ffc273337d7d)

I have also decided that instead of using EasyEDA this time, i will be using "KICAD - THE DAD OF CIRCUIT DESIGN"(lol). I started working on the schematic. RP2040 is also finalised for now. so 2 USB-C connectors will be on the PCB, one for programming RP2040 and other for **POWER**

