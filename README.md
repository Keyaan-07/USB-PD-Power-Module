# USB-PD-Power-Supply
Sometimes it happens that when playing with electronics, we need more than 5V or 9V. USB PD Power Supply Solves this issue.  
By using USB PD Protocol, it can negotiate more than 5V from the USB PD charger. It can give voltage outputs as supported by the PD charger from 5V to 20V and it also supports the new USB PPS protocol which allows us set the voltage according to our own needs. For Example, if some device needs 18V, PPS can do the task and it could supply voltage.  

USB PD Power Supply can use both PD and PPS to cupply voltage. The microcontroller is the OG RP2040, which communications with the AP33772SDKZ USB PD negotiator IC to negotiate voltage levels. The Voltage and max current settings are controllable using the two rotary encoders present on the PCB.  

# Images
 ![image](https://github.com/Keyaan-07/USB-PD-Power-Supply/blob/main/Images/Final1.png)    
 ![image](https://github.com/Keyaan-07/USB-PD-Power-Supply/blob/main/Images/Final2.png)
<br>

  
![image](https://github.com/Keyaan-07/USB-PD-Power-Supply/blob/main/Images/pcb.png)  

<br>  

![image](https://github.com/Keyaan-07/USB-PD-Power-Supply/blob/main/Images/Bottom1.png)  
![image](https://github.com/Keyaan-07/USB-PD-Power-Supply/blob/main/Images/Top1.png)

# BOM
