Here is a fully DC power supply with implemented Safety features, real-time MCU control, Voltage & Current adjustment, a cooling system, a wireless charger, and an LCD Display for output voltage.

<img width="837" height="486" alt="Screenshot 2026-07-17 235530" src="https://github.com/user-attachments/assets/2e4b0f45-31d2-46c4-bc5c-6e98faf4f254" />

# ⚡ Adjustable Smart Bench PSU

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
13- Acknowledgments                                                               
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
May some people disagree with my point of view as a maker, and someone aspires to become a mechatronics engineer like me. However, the main purpose for any project u will ever make is to *learn new kinda of stuff!!*

Is that all?    *For sure no!*
The customization and the flexibility are also important points to take into consideration with respect to the needs and price.


## List of materials and cost                                                                        
### 🔌The Power section:
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


### 📟The Controlling section:-

1)- THE Microcontroller (MCU):                                    
<ul>
<li>Air001 MCU Cortex M0 core 32Kflash TSSOP20</li>                             
or                                                 
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

### 🌡️ Cooling system & 🔐seafty control:

#### 🌡️Cooling System:
<ol>
<li>SSR Heatsink</li>
<li>Two or three Fans</li>
</ol>

#### 🔐 safety control:
<ol>
<li><strong> Main fuse after the power Adapter </strong></li>
<li>May be added a fuse to every port</li>
</ol>
</br>


# The system architecture flow:
## The power Circuit:
<img width="1260" height="694" alt="the power shematic drawio" src="https://github.com/user-attachments/assets/fbcd72be-52ff-44ec-9abc-dd06c07b2b23" />

I made this using Draw.io.




Upcoming progress:
