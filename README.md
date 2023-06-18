# Mueler Spraydos AgOpenGPS section control
An electromechanical approach to open source section control of Mueler/Müller Spraydos spraying computers through software as AgOpenGPS. 
This project provides the mechanical design for a non-intrusive addon mod to automatically control the sections on a spraydos computer thourgh a gps system. All needed parts and other information are discribed bellow

The system consists out of a bracket, that calmps around the spraying computer and doubles as electronics box, and a servo box on a hinge. The main section switch and all other buttons remain freely accesible.

<p float="left">
  <img src="/Pictures/Front1.jpg"  height="550"/>
  <img src="/Pictures/Side1.jpg"  height="550"/>
</p>

The servo box contains servos to control the section switches through specially designed lever arms. The servo box is mounted on a hinge and can be swung away to regain manual control. The servo box can be kept closed through magnets or an M4 bolt
<img src="/Pictures/ServoFront.jpg"  width="770"/>

The electronics box on the back has mounting points to accomodate a 8ch servo controller, A DC buck converter and a 8 channel relay card (optional). The optional relay card can be replaced with a second servo controller when you need 9 sections.
<img src="/Pictures/El2.jpg"  width="770"/>

**_Why control the buttons mechanically and not switch section through relays?_**
* Motorised valves need 2 relays per section (18 in total...).
* You cannot put ralays in parallel to the buttons, you will create a short.
* To keep the switches as manual backup they cannot be replaced by relays.
* Breaking the lines going to the the valves and changeing the state there with relays could work. But the rate controller will not work anymore since it does not know the real state of the sections. (You could compensate this by changeing the speed signal however)
* To keep the mod as a bolt-on addon to keep the controller original for resale when the time comes.


## Needed hardware
### Printed parts
I provide some limited print service for Western europe. Contact me through github or on [this thread](https://discourse.agopengps.com/t/printing-service-for-aog-community-western-europe/12823)

<img src="/Pictures/Overview1.PNG"  width="200"/>


* [Servo box](/Printed_parts/ServoBox)
* [Servo box lid](/Printed_parts/ServoBoxlid)
* [Front bracket](/Printed_parts/FrontBracket)
* [Electronics box](/Printed_parts/ElBox)
* [Electronics box lid](/Printed_parts/ElBoxLid)
* [Servo arm](/Printed_parts/ServoArm)

### Montage parts
* Wood screw D3 l15 X14
* Bolt M4 l15 X4
* Nut M4 X4
* Bolt M5 l45 X1
* Nut M5 X1
* Hot melt nut M3 X12
* Closing latch (one of the two)
  * Magnet D5 L5 X2 (push in with solder iron)
  * Bolt M4 l8 + Nut M4

### Electronics
These electronics only work till 8 Sections for more sections you will need more servo controllers or a different type that can accomodate 9 servos
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

