# Mueler Spraydos AgOpenGPS section control
An electromechanical approach to open source section control of Mueler/Müller Spraydos spraying computers through software as AgOpenGPS. 
This project provides the mechanical design for a non-intrusive addon mod to automatically control the sections on a spraydos computer through a gps system. All needed parts and other information are discribed bellow.

The system consists out of a bracket, that clamps around the spraying computer and doubles as electronics box, and a servo box on a hinge. The main section switch and all other buttons remain freely accessible.

<p float="left">
  <img src="/Pictures/Front1.jpg"  height="550"/>
  <img src="/Pictures/Side1.jpg"  height="550"/>
</p>

The servo box contains servos to control the section switches through specially designed lever arms. The servo box is mounted on a hinge and can be swung away to regain manual control. The servo box can be kept closed through magnets or an M4 bolt
<img src="/Pictures/ServoFront.jpg"  width="770"/>

The electronics box on the back has mounting points to accommodate a 8ch servo controller, A DC buck converter and a 8 channel relay card (optional). The optional relay card can be replaced with a second servo controller when you need 9 sections (mounting holes are there in the new models). Two 16mm holes for input power and section signals and a threaded hole for a sleeve to the Servo box are foreseen.
<img src="/Pictures/El2.jpg"  width="770"/>

<img src="/Pictures/El_box_mount_points.PNG"  width="770"/>

**_Why control the buttons mechanically and not switch section through relays?_**
* Motorised valves need 2 relays per section (18 in total...).
* You cannot put relays in parallel to the buttons, you will create a short.
* To keep the switches as manual backup they cannot be replaced by relays.
* Breaking the lines going to the the valves and changing the state there with relays could work. But the rate controller will not work anymore since it does not know the real state of the sections. (You could compensate this by changeing the speed signal however)
* To keep the mod as a bolt-on add on to keep the controller original for resale when the time comes.


## Needed hardware
### Printed parts
I provide some limited print service for Western europe. Contact me through github or on [this thread](https://discourse.agopengps.com/t/printing-service-for-aog-community-western-europe/12823)

<img src="/Pictures/Overview1.PNG"  width="400"/>


* [Servo box](/Printed_parts/ServoBox)
* [Servo box lid](/Printed_parts/ServoBoxlid)
* [Front bracket](/Printed_parts/FrontBracket)
* [Electronics box](/Printed_parts/ElBox)
* [Electronics box lid](/Printed_parts/ElBoxLid)
* [Servo arm](/Printed_parts/ServoArm)

### Montage parts
* Wood screw D3 l15 X14 (for al the lids)
* Bolt M4 l15 X4 (for mounting the bracket to the electronics box)
* Nut M4 X4 (for mounting the bracket to the electronics box)
* Bolt M5 l45 X1 (Serves as hinge bolt)
* Nut M5 X1 (Serves as hinge bolt)
* Hot melt nut M3 X12
* Closing latch (one of the two)
  * Magnet D5 L5 X2 (push in with solder iron)
  * Bolt M4 l8 + Nut M4
* EPDM roofing sheet (+-1mm thick)
  * Glue a big patch or multiple smaller ones on the back of the electronics box. This will provide extra mounting friction and adapt better to the uneven surface of the spraydos controller  

### Electronics
For more than 8 sections you will need two servo controllers or a different type that can accommodate 9 servos.
* Servo motor MG90S (as many as needed for your sprayer) (other models might fit, did not try)
<img src="/Pictures/Servo.PNG"  width="250"/>

* Servo controller, i used [this one](https://nl.aliexpress.com/item/1005002120074314.html?spm=a2g0o.order_list.order_list_main.18.141d79d2i53ILI&gatewayAdapt=glo2nld) :
<img src="/Pictures/Servocontroller.PNG"  width="250"/>

* DC buck converter XL4015 5A, mounting holes are compatible with [CC/CV models like this one](https://nl.aliexpress.com/item/1005002554895443.html?spm=a2g0o.order_list.order_list_main.39.141d79d2i53ILI&gatewayAdapt=glo2nld) :
<img src="/Pictures/DCBuck.PNG"  width="250"/>

* Optional 8 way relay module, mounting holes are compatible with [this one](https://nl.aliexpress.com/item/1005002867727977.html?spm=a2g0o.order_list.order_list_main.20.16ab79d2H6eU5A&gatewayAdapt=glo2nld) :
<img src="/Pictures/Relaymod.PNG"  width="250"/>

* Wire nuts, connectors and cable protection
  * Two 16mm holes in electronics box for connections and supply powe
  * Threaded holes in electronics and servo box for flexible armoured cable sleeves (Will probably cahnge this in the future)

## Wiring and control
The servo control needs to be "dumbed down" to a bi-stable state that can be commanded by a section relay card. 
These connections can be switched around based on what kind of section reaction you want to different steering and logic conditions.

### Simple and works but you can create a short circuit!
Use the potentiometer from the servo controller to set one position of the servo arm and bridge the position signal pad (central pin of the potentiometer) to VCC or GND of the servo card with a relay to send it to the second position. Connect these wires to the mount points of the potentiometers on the back of the servo controller card. You only need number of sections+1 cables to control this board.

_Make sure NOT to turn the potentiometers to their full left or right position when relay bridge is closed._

<img src="/Pictures/Pot_bridge.PNG"  width="500"/>

### Safer way but more work
Desolder all the potentiometers from the servo controller board. Connect the common ports of your section relay board to the position signal pads (central pin) of the servo controller board. Connect the VCC and GND of the servo board to a separate pot (reuse on you just took of). Connect the GND and signal of the seperate pot to the NC/NO ports of your section relay board. You only need number of sections+2 cables to control this board. You now use the separate potentiometers to controll one position of all servos and the relay contact for the second position.

<img src="/Pictures/Pot_seperate.PNG"  width="500"/>

### Better way? use RS485 based servo controller?
TODO
