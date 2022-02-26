# Display noise
<br>
### 300Hz hash noise from backlight PWM

|  |  |  |
| --- | --- | --- |
|  | Separated power source |  |
| . | Update 7805 dedicated for Nextion: Add 4.7R to 10R between +B and 7805 input, plus 470-1000uF cap between 7805 input and 7805 ground pins |  |
|  | Update 7805 dedicated for Nextion: 2.2mH RF choke in series to 5v line going to Nextion. At nextion 5v and GND, 220uF. The noise reduced to just 10% |  |
|  | 2ohm and 2.5mH toroid, 70 turns, 22AWG, FT114-43 core series +5v to Nextion |  |
|  | 5.6 ohm and 12.3 mH inductor from old TV board plus  2200uF cap |  |
|  | Wrap 4 wires around small toroid |  |
|  | Swap wires that goes to volume control |  |
|  | Change brightness to 90% or more |  |
|  | Leave brightness at 100%, use a resistor to drop current to control brightness. |  |

Sources:
BitX20 groups.io / uBitX site / uBitX user sites
https://groups.io/g/BITX20/message/64399
https://groups.io/g/BITX20/message/67642
https://groups.io/g/BITX20/message/70753
https://groups.io/g/BITX20/message/73406
[https://groups.io/g/BITX20/topic/52079174](https://groups.io/g/BITX20/topic/52079174)
[https://groups.io/g/BITX20/message/81841](https://groups.io/g/BITX20/message/81841)
[https://ubitx.net/category/nextion-display/](https://ubitx.net/category/nextion-display/)
[http://www.hamskey.com/2018/06/nextion-tjc-character-lcd-current.html](http://www.hamskey.com/2018/06/nextion-tjc-character-lcd-current.html)
<br>
### Noise during data transmission or screen updates

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
|  | Board with MPU and Display back-to-back, same board | BitX Raduino with Teensy 4.1 <br>[http://www.w0eb.com/uBITX\_V6\_T4.1RaduinoCloneConstMan.pdf](http://www.w0eb.com/uBITX_V6_T4.1RaduinoCloneConstMan.pdf)<br>Picture 1 and 2 |  |  |
|  | Use twisted pair and shielded cable | [http://www.w0eb.com/BITeensioBoardConstructionManual.pdf](http://www.w0eb.com/BITeensioBoardConstructionManual.pdf) <br><br><ul><li>Twist together power &amp; ground leads – connect to the new 3.3V 1.5A regulator output &amp; ground on the BITeensio card.</li><li>Twist together MISO and MOSI (twist in a ground wire as well – connect this ground to BITeensio header P5 Ground) All three (MISO, MOSI and this ground) connect to P5.</li><li>Twist together the other 3 wires, SCLK, CS and INT and connect these to P(TFT) as indicated above.</li><li>The cable MUST be shielded with the shield connected to ground on both ends. The ground end going to the BITeensio should be connected to P5 pin 1 (Ground) for convenience as well as providing additional grounding for the display. This really helps keep RFI to a minimum and noise out of the display.</li></ul> |  |  |
|  |  |  |  |  |
<br>
<br>
Picture 1
![image.png](.media/img_1.png)

Picture 2
![image.png](.media/img_2.png)
