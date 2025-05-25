---
title: "USB PD Power Suply"
author: "Keyaan"
description: "USB-PD Based Power Supply to power your non-5V electronics"
created_at: "2024-05-23"
---

# May 23 2025:
Today i will be finding the USB PD negotiation IC. So basically i have the idea of making the smallest(that i can create) power module to power my electronics projects,
when i am prototyping.

okay, found the IC, it is [AP33772SDKZ-13-FA01](https://www.mouser.in/ProductDetail/Diodes-Incorporated/AP33772SDKZ-13-FA01?qs=2wMNvWM5ZX4CLYQ4%252BLyimw%3D%3D), and now i have another idea, let's make a variable power supply, which gives variable power supply if PPS is available, or else it gives constant supply @ 5V, 9V, 12V, 15V or 20V.

i think i am gonna use some microcontroller (probably an rp2040) along with an OLED that displays voltage and current, and also rotary encoders/potentiometers, although i haven't decided on that.

### Total Time Spent - 20 Mins

# May 24 2025:
Today, i made a block diagram by hand, and i selected the [ams1117 3.3v LDO regulator](https://lcsc.com/product-detail/Linear-Voltage-Regulators-LDO_Advanced-Monolithic-Systems-AMS1117-3-3_C6186.html) for the RP2040, but then i came to realise that the max input voltage for ams1117 is 15V, while max voltage with PD is 20V, so i chose another regulator(it is so hard to find a proper regulator). the new regulator now is [AMS1117S-3.3](https://lcsc.com/product-detail/Voltage-Regulators-Linear-Low-Drop-Out-LDO-Regulators_JSMSEMI-AMS1117S-3-3_C917152.html)

<img src="https://github.com/user-attachments/assets/e52aae66-0bd2-412d-a26d-ffc273337d7d" alt="Handmade Block Diagram" width="500" height="282">

I have also decided that instead of using EasyEDA this time, i will be using "KICAD - THE DAD OF CIRCUIT DESIGN"(lol). I started working on the schematic. RP2040 is also finalised for now. so 2 USB-C connectors will be on the PCB, one for programming RP2040 and other for **POWER**

Ok, so let me just write out all the finalised parts here:
1. [I2C OLED](https://robu.in/product/4pin-oled-display-module-blue-color/)
2. [Rotary Encoders x2](https://robu.in/product/hongyan-ec11h-7ce15p1zy15f7-rotary-encoder-with-push-button-switch-vertical-plug-in/), [what i chose earlier](https://robu.in/product/4pin-oled-display-module-blue-color/)
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

ok, so i have finished with the work for the day, today i completed the RP2040 connections, like the bare minimum connections required, and i also finalised the parts, and tomorrow i will be looking into the connections of the USB-PD controller, and i hope to make a 4 layer PCB, although i will try with 2 layers, if it will be possible.
![Schematic done on 24th may](https://github.com/user-attachments/assets/033630af-b5f1-48d7-bd09-a7f47c8bbd45)

PS: I am changing the rotary encoders as i found out about a new, more popular encoder, the [EC11H](https://robu.in/product/hongyan-ec11h-7ce15p1zy15f7-rotary-encoder-with-push-button-switch-vertical-plug-in/), which is the one that i will be using...  

okay, i had some free time tonight so i worked more on the schematic, i came to realise that i have to LOGIC-SHIFT the I2C communication, so that i dont burn the rp2040, so for logic shifting i found BS138 to be the most common and i went with them. So, for proper logic-shifting, we also need a proper 5V supply, so i chose another LDO regulator😭(it's a pain finding proper regulator). A wise legend once said, choose your components wisely.Btw, i also added a few capacitors to the PD controller.

Things added to schematic:  
![image](https://github.com/user-attachments/assets/a2c67a91-b5f2-40c4-9b77-74e53549e0ee)
![image](https://github.com/user-attachments/assets/7894817c-4af5-4eb1-8c2e-939a754048d4)

If i were to rate the experience using Kicad rather than EasyEDA, i would say that it is good, and you get A LOT of customisability, but EasyEDA is much simple.

### Total Time Spent today - 2 hours 10 mins
