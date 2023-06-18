# Mueler Spraydos AgOpenGPS section control
An electromechanical approach to open source section control of Mueler/Müller Spraydos spraying computers through software as AgOpenGPS

<p float="left">
  <img src="/Pictures/Real1.PNG"  height="500"/>
  <img src="/Pictures/Side1.PNG"  height="500"/>
</p>

**_Why control the buttons mechanically and not switch section through relays?_**
* Motorised valves need 2 relays per section (16 in total...).
* You cannot put ralays in parallel to the buttons, you will create a short.
* To keep the switches as manual backup they cannot be replaced by relays.
* Breaking the lines going to the the valves and changeing the state there with relays could work. But the rate controller will not work anymore since it does not know the real state of the sections. (You could compensate this by changeing the speed signal however)
* To keep the mod as a bolt-on addon to keep the controller original for resale when the time comes.


## Needed hardware
### Printed parts
I provide some limited print service for Western europe. Contact me through github or on [this thread](https://discourse.agopengps.com/t/printing-service-for-aog-community-western-europe/12823)
* [Servo box](/Printed_parts/ServoBox)
* [Servo box lid](/Printed_parts/ServoBoxlid)
* [Front bracket](/Printed_parts/FrontBracket)
* [Electronics box](/Printed_parts/ElBox)
* [Electronics box lid](/Printed_parts/ElBoxLid)

### Montage parts
* Wood screw D3 l15 X6
* Bolt M4 l15 X4
* Nut M4 X4
* Bolt M5 l45 X1
* Nut M5 X1
* Closing latch (one of the two)
  * Magnet D5 L5 X2 (push in with solder iron)
  * Bolt M4 l8 + Nut M4

### Electronics
* Servo motor MG90S (as many as needed for your sprayer) (other models might fit, did not try)
<img src="/Pictures/Servo.PNG"  width="250"/>

* Servo controller, i used [this one](https://nl.aliexpress.com/item/1005002120074314.html?spm=a2g0o.order_list.order_list_main.18.141d79d2i53ILI&gatewayAdapt=glo2nld) :
<img src="/Pictures/Servocontroller.PNG"  width="250"/>

* DC buck converter XL4015 5A, mounting holes are compatible with [CC/CV models like this one](https://nl.aliexpress.com/item/1005002554895443.html?spm=a2g0o.order_list.order_list_main.39.141d79d2i53ILI&gatewayAdapt=glo2nld) :
<img src="/Pictures/DCBuck.PNG"  width="250"/>

* Wire nuts, connectors and cable protection to own needs
  * Two 16mm holes in electronics box for connrctions
  * Threaded holes in electronics and servo box for armoured protection hose

## Wiring and control

