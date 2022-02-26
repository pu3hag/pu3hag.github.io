# Display noise
## BITX20 groups.io
### 300Hz noise caused by Nextion backlight PWM, specially if less than 90% brightness


* Use a separated 5v power source
* Update 7805 dedicated for Nextion
    * Add 4.7R to 10R between +B and 7805 input, plus 470-1000uF cap between 7805 input and 7805 ground pins.
    * 2.2mH RF choke in series to 5v line going to Nextion. At nextion 5v and GND, 220uF. The noise reduced to just 10%.
* Change brightness
* Swap wires that goes to volume control
* Wrap 4 wires around small toroid
* 2.5mH toroid, 70 turns, 22AWG, FT114-43 core series +5v to Nextion


https://groups.io/g/BITX20/message/64399
https://groups.io/g/BITX20/message/67642
https://groups.io/g/BITX20/message/70753
https://groups.io/g/BITX20/message/73406
https://groups.io/g/BITX20/topic/52079174
https://ubitx.net/category/nextion-display/

### 
