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

Ok, so let me just write out all the finalised parts here:
1. [I2C OLED](https://robu.in/product/4pin-oled-display-module-blue-color/)
2. [Rotary Encoders x2](https://robu.in/product/4pin-oled-display-module-blue-color/)
3. Microcontroller: [RP2040](https://www.lcsc.com/product-detail/Microcontrollers-MCU-MPU-SOC_Raspberry-Pi-RP2040_C2040.html)
4. [Flash for RP2040](https://lcsc.com/product-detail/NOR-FLASH_Winbond-Elec-W25Q128JVSIQ_C97521.html)
5. USB PD Sink Controller: [AP33772SDKZ-13-FA01](https://www.mouser.in/ProductDetail/Diodes-Incorporated/AP33772SDKZ-13-FA01?qs=2wMNvWM5ZX4CLYQ4%252BLyimw%3D%3D)
6. [Push Button](https://lcsc.com/product-detail/Tactile-Switches_C-K-PTS810SJK250SMTRLFS_C221896.html)
7. [Crystal @ 12MHz](https://www.lcsc.com/product-detail/Crystals_Abracon-LLC-ABM8-272-T3_C20625731.html?s_z=n_ABM8-272-T3)

#### Why I chose a 128Mbit chip instead of a smaller one?
I chose a bigger chip rather than the typical 16Mbit because of mainly three reasons:  
    1. the difference in price is about $0.1.  
    2. The RP2040 design guide recommends it.  
    3. I dont know how long is the code gonna be.  
