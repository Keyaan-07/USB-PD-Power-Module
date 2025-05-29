# USB-PD-Power-Supply
Sometimes it happens that when playing with electronics, we need more than 5V or 9V. USB PD Power Supply Solves this issue.  
By using USB PD Protocol, it can negotiate more than 5V from the USB PD charger. It can give voltage outputs as supported by the PD charger from 5V to 20V and it also supports the new USB PPS protocol which allows us set the voltage according to our own needs. For Example, if some device needs 18V, PPS can do the task and it could supply voltage.  

USB PD Power Supply can use both PD and PPS to cupply voltage. The microcontroller is the OG RP2040, which communications with the AP33772SDKZ USB PD negotiator IC to negotiate voltage levels. The Voltage and max current settings are controllable using the two rotary encoders present on the PCB.  

# Images
 ![image](https://github.com/user-attachments/assets/babcb920-5bb2-4972-af39-2042b7cf4a04)    
 ![image](https://github.com/user-attachments/assets/7cf7985a-c85c-4552-ae46-b0d065034048)
<br>

![image](https://github.com/user-attachments/assets/b1b06363-f7c4-4f2f-ad24-0d1307ba7d3d)  
![image](https://github.com/user-attachments/assets/72b781c0-492a-476f-b777-d17956618048)  

<br>  

![image](https://github.com/user-attachments/assets/9dbc4ca2-4019-4f28-ac9c-9ed065456d70)  
![image](https://github.com/user-attachments/assets/2375700d-478d-4c71-bd65-8e767b2b3966)

# BOM
