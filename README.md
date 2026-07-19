Here is a fully DC power supply with implemented Safety features, real-time MCU control, Voltage & Current adjustment, a cooling system, a wireless charger, and an TFT Display for output voltage.

<img width="837" height="486" alt="Screenshot 2026-07-17 235530" src="https://github.com/user-attachments/assets/2e4b0f45-31d2-46c4-bc5c-6e98faf4f254" />

#  Adjustable Smart Bench PSU

A modular laboratory power supply designed from scratch with
real-time monitoring, protection systems, and scalable multi-output architecture.

# Contents:

1- The main identity and features                                                                              
2- Why DIY, not buy a new, ready-made one?                                                                      
3- list of materials and cost                                                                        
4- The System Architecture flow                                                               
5- The main system Parameters                                                               
6- The automation and building process (METHODS)                                                               
7- Coding-related Part                                                               
8- Documented Failures                                                               
9- Outcome                                                               
10- Safety features and precautions                                                               
11- Upcoming Progress                                                               
12- References                                                               
13- ###<strong>Acknowledgments, refreneces, and AI usage </strong>                                                               
14- Contact                                                               
15- License                                                               


## The Main identity and features:

I had always dreamed about owning an awesome power supply for my projects, a cable to handle various projects, ideas, and testing loads.
Unfortunately, the features, design, and flexibility I need would cost me a lot of money. So I decided to make my own. Additionally, since I had no workshop, tools, devices, or anything, I found it cool to make a full series about building my lab. 


### The Features I was dreaming about:                                                               
1- Adjustable DC power supply ranging from Lim➡️ ZERO to 24V.                                                               
2- Multi-port for output like 4 or 5.                                                               
3- TFT screen of 3.4 inches, rather than 7-segment.                                                               
4- Nice Design.                                                               
5- High Safety features.                                                               
6- one or two AC Ports.                                                               
7- integrated USB HUB                                                             
7- Wireless Charger.                                                               
8- Cooling System.                                                               
9- Data Logging, Graphing, and connection to PC or Lab capability.                                                               
10- Desktop APP                                                               
11- Short Circuit prevention.
12- Battery Charging.                                                               
13- Cable for Modification.                                                                
14- OverVoltage Protection (OVP), OverCurrent protection (OCP), and OverTemperature Protection (OTP)                               
15- Reverse polarity protection
16- Port protection by relay
17- Enclosure design


To find these features in PSU today, it would cost about 10,000 to 30,000 EGP, which is quite expensive for beginners.
For that sake, I made the Making My Lab series, where I will make a full lab device open-sourced for all around the world.
Additionally, you don't have to make the full project; there are versions of this project and other combinations I will provide through the journal file, and the system architecture part in that Readme, so make whatever you need. Also, I am available all of the time to answer your questions and give you help❤️ in any kinda of project, whatever it is. Just Feel Free to go for the Contact part.



## Why DIY, not buy a new, ready one??                                                             
Some people may disagree with my point of view as a maker, and someone aspires to become a mechatronics engineer like me. However, the main purpose for any project u will ever make is to *learn new kinda of stuff!!*

Is that all?    *For sure no!*
The customization and the flexibility are also important points to take into consideration with respect to the needs and price.

## The schematics
<img width="835" height="572" alt="Screenshot 2026-07-18 052406" src="https://github.com/user-attachments/assets/aba273a9-39a5-4b09-9547-871f9d86ec78" />
<img width="887" height="600" alt="Screenshot 2026-07-18 040531" src="https://github.com/user-attachments/assets/9bf1b906-2147-4382-b186-96d227cc180f" />
<img width="861" height="601" alt="Screenshot 2026-07-18 040436" src="https://github.com/user-attachments/assets/8e25037c-ef4e-4de6-99d1-1bfededd7796" />


## List of materials and cost                                                                        
### The Power section:
#### DC section:-
1) Power Adaptor AC to DC 24V and 10A
2) Power adaptor AC to DC 12V and 5A                                                              
4) XL4016 DC to DC buck converter for each adjustable port                                                                 
6) Terminal Blocks + connectors
7) Wiring
8) Ports                                              

#### AC Power Section:-
External three-AC power strip

#### Wireless Charger module:-
Wireless Charger Module


### The Controlling section:-

1)- THE Microcontroller (MCU):                                    
<ul>
<li> ESP 32 (in case of making the final version)</li>
or 
<li>just any MCU (unless it fits the main parameters of the project)</li>
</ul>

2)- Current Sensor:
<ul>
<li>ACS 712</li>
</ul>

3)- Voltage Calibration circuit (Voltage Divider):-
<incline> under research until now </incline>

4)- Liquid Crystal Display (LCD):
Simply to display the voltage and current for every port, additionally warning in case a short circuit occurs.

5)- Buzzer:
For a short-circuit warning.

6)- Relay module (Fuse integrated) for every port of DC and the wireless charger.

7)- Switch per every DC and the wireless charger.

8)- Circuit of continuous control for the fans and cooling.

### 🌡️ Cooling system & seafty control:

#### Cooling System:
<ol>
<li>SSR Heatsink</li>
<li>Two or three Fans</li>
</ol>

And right here, I made many ventilation holes for the fans, like what is there in the upper case of the usb hub and the PSU too. Additionally, two ventilation holes in the back of the PSU.

#### safety control:
<ol>
<li><strong> Main fuse after the power Adapter </strong></li>
<li>May be added a fuse to every port</li>
</ol>
</br>


# The system architecture flow:
## The power Circuit:
<img width="1260" height="694" alt="the power shematic drawio" src="https://github.com/user-attachments/assets/fbcd72be-52ff-44ec-9abc-dd06c07b2b23" />

I made this using Draw.io.

## The automation and building Instructions:

### The PSU main Power input and protection
Here are all the instructions u are gonna need:
First of all, for the main power source, I will be using a ready-made Power Adapter of 24 V and 10 A (u could for sure get a better one till 32V as maximum and maybe till 12 amperes. However u will need proper cooling)
Secondly, the Protection circuit, where the (by the same order):
<ol>
  <li>Main Fuse <em>-it is better to use an 11 or 12 amp slow-blow fuse if u are gonna make the system with 10 amps-</em></li>
  <li>A switch -make sure u choose a switch typically to the system power input, or simply choose this switch which cable to shut off, even 220 V and 10 amps-
    <img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/06de0c10-9813-49b4-9231-df95a1fb5b4d" />
  <li>Transient protection aligned with decoupling capacitors, and yes, I am talking about surge transient protection, not just any overvoltage so make sure u are using transient diode </li>
  <li>Then here is our main system power input of 24v and 10 amps</li>
  <img width="676" height="206" alt="image" src="https://github.com/user-attachments/assets/41bb8ba1-e934-49a1-b6a2-5361a8978027" />

  <li>Finally, i added a relay as a way to shut down the whole system, ensuring safety. In case anything happens.
  I am here controlling the relay with something like an AND gate with an independent switch, and an ESP signal too. We will use the ESP for the relay in case of reverse polarity, overcurrent, overvoltage, or any severe cases. And as far as we go and make an app, we will be able to use WIFI to control the whole system</li>
  <img width="386" height="155" alt="image" src="https://github.com/user-attachments/assets/733cdbec-52b1-4068-b787-aa47bb2d6928" />
</ol>


### The Power distribution and Outputs:
For the adjustment outputs, I will be using XL4016 for each adjustable output, and I will make them in parallel, for sure so they will all take the same voltage, and the current will be distributed.
<img width="372" height="547" alt="image" src="https://github.com/user-attachments/assets/16cbd79d-1184-411b-87ff-e31606238a19" />
And as seen above in the image, I also have one extra constant output taking from the main rail. In conclusion, we have three adjustable outputs and one fixed output.

Additionally, I will be using Relay for each port to manually close and open, or using WIFI.
<img width="230" height="301" alt="image" src="https://github.com/user-attachments/assets/39ac571b-a1c8-4a74-b83a-2a2ddfc4dc05" />

### The power sensing for each Output:
Think of this as a way for self-parameter monitoring, where the system flows through each port and the total voltage-current consumption.

<strong>For this project, mainly I WILL USE ADC THE MOST, SO I DECIDED TO USE READY ADS MODULE 1115. Just as an alternative to the noisy ESP ADC</strong>

#### For the Current sensing for each port for the XL4016 using ACS712:
<img width="247" height="348" alt="image" src="https://github.com/user-attachments/assets/90fc8f3a-6dc4-4e30-b1d8-4d238ef5328a" />

Additionally, I will be using a capacitor for each sensor to filter the noise as much as possible. You could simply use this equation to calculate your values. Since the ACS712 also uses a 5V signal, which isn't proper for the ESP PINS, I made all of the signal outputs with 3.3v using voltage dividers.
<img width="332" height="167" alt="image" src="https://github.com/user-attachments/assets/077c4e40-7433-4ae5-a165-69cf16e313e7" />


#### However, for the voltage sensing, I will be using a normal voltage divider connected to the ADS module 1115, like that:
<img width="240" height="456" alt="image" src="https://github.com/user-attachments/assets/a3f44f23-ff8c-4276-acd0-21e0928e795b" />

### Then, we finally finished our Power circuit:
<img width="847" height="577" alt="image" src="https://github.com/user-attachments/assets/26f748f8-d2a4-42f8-969d-e0de12aa6edf" />

## The Control circuit:
The main idea of the PSU is adjustment for the outputs, so how will this work using those XL4016 modules?
<img width="533" height="372" alt="image" src="https://github.com/user-attachments/assets/8396396f-c6fd-4b25-a894-cb54741efdfd" />

The solution is to remove the Timer potentiometer, with a varying DC source of reference 1.25v. However, for the NPN injection transistor or MOSFET, it wouldn't go well.


For the assembly of the 3d case, I am gonna use a silicon paste. Additionally, the RGB light will be rounded and immersed in the edges of the upper and bottom enclosures. 
And for the outputs of the PSU, I will be using 4 mm Safety Banana Binding Posts and GX16-2

#Acknowledgments and AI usage:
<ul>
<li>My friend SID Batra: the first one who reviewed my early schematics.</li>

<li>those incredible references:</li>
<ol>
  <li> Practical electronics for inventors</li>
  <li>fundamentals of electronic circuits, especially for the FB circuits</li>
</ol>

<li>and Claude AI for the following:
<ol>
<li>Explaining the PID with Simple coding.</li>
<li>Major help in the PID coding part</li>
<li>and most importantly, the CC and CV controlling. I spent a week entirely trying to figure out the way of controlling the XL4016, and yeah, after long frustration through OP-AMPS, FB circuits, and the TL431 architecture. I just found it is better to replace the trimmers with a varying DC voltage source at the wiper</li>
</li>
</ol>
</ul>

###FUN FACT: also, the trimer potentiometer <strong>can't</strong> be replaced by the following for controlling:
<ul>
<li>NPN injection transistor, as it is non-linear and is affected by temperature  change</li>
  <li>same as the same as MOSFET </li>
</ul>
