---
title: "Smart Adjustable PSU"
author: "Peter Fayez."
description: "This is a power supply 24V and 10A, with 4 adjustable output ports, with transient protection, overcurrent, overvoltage, and overtemperature protection. Additionally, it is added with a wireless charger module, a USB Hub, Remote Controlling, cooling system(Urgent+dominant), PC/andriod App, TFT touch screen, and Smart using Wi-Fi.
"
created_at: "2026-06-01"
---

The full idea: circuit design, components, CAD design, enclosure, and CFD cooling model are made entirely by me.
You can use my Readme record as some sort of check cuase i wasn't konw about journaling, so it is believable that it may have found some of the unmatched timing because I wasn't introduced to hackatime, lapses, or even journaling yet. I just got started.

# June 1: Begin search, study power electronics, write my parameters:
This was my actual first step as a new member in the electronics and hack club, too. I had barely enough electronics knowledge to understand the theoretical perspective of electricity and power conversion. So, I began to study, making my first flow chart with draw IO that took about 3 hours, including several mistakes and overkill misconceptions in basic power and wiring concepts, especially for the surge protection.

<img width="936" height="497" alt="Screenshot 2026-05-17 071048" src="https://github.com/user-attachments/assets/10447f69-c7f1-4000-91a5-4195e1a673eb" />

**Total time spent: 3 hours**


# June 2: Begin search, study power electronics, write my parameters:
This was a more detailed version, as I not only began the flow, but I began to figure out what components and wiring I would have. That drawing takes me about 4 hours!!
<img width="1194" height="697" alt="image" src="https://github.com/user-attachments/assets/61a2f36c-6dde-414c-961d-0ef090fc2680" />

Additionally, I had begun my first Kicad schematic ever in my entire life, and for the first hour, I was lagging. Fortunately, after some time, I began to figure out how things work!! And then I got another couple of hours trying to make this schematic.<img width="954" height="562" alt="image" src="https://github.com/user-attachments/assets/d0ca9e49-9b38-4ef0-82bb-bd65be386a31" />
I also spent a bunch of hours that day on some of the kidac tutorials and some of the power electronics reading books and courses.

**Total time spent: 7 hours**



# June 2: searching for the PSUs' parameters and features + trying to add some of the work to Draw. io. and my schematic:
I was searching for about two hours or maybe even much more (unfortunately, I wasn't introduced to lapsing, so I don't have screen records of the full search, but, predictably, it will exceed two hours) just searching for such things as the smart DC power supply, power output, design, and screens too so I can come up with clearer insight.

Also, I edited a little bit on the first schematic; I tried to make it cleaner. That takes about an hour.
<img width="1106" height="837" alt="Screenshot 2026-05-29 190148" src="https://github.com/user-attachments/assets/9bc85a80-1101-4da8-bca6-1835a0c3484e" />
**Total time spent: 3 hours**


# June 3: some kinda of improvements and learning
Also, I tried to add a lot of the things in the schematic that take about 1 hour.
<img width="1038" height="644" alt="Screenshot 2026-06-07 000439" src="https://github.com/user-attachments/assets/73c1f00b-7af3-43f3-8914-55493a34b0dc" />
Also, I made a circuit for the urgent fan in case of high TEMP! This takes me about half an hour.
<img width="645" height="350" alt="Screenshot 2026-06-07 004428" src="https://github.com/user-attachments/assets/883337e9-4b9f-43fe-8d92-38d979e0780b" />
Additionally, I had started searching for the components' availability in Egypt and the alternatives, which had much more at this stage. That was about 2 hours.
**Total time spent: 3.5 hours**

# June 4: the CV and CC adjustment discovery by the XL4016
This is the first day I understood how the FB pins in the XL4016 were really working and how it is adjusted to a ref. of 1.25v. Here is the core of the adjustable power supply emergent, and how it could be the Potentiometer replaced with encoders(my dream!!!!)
That research about available options takes me about 4 hours.
<img width="1083" height="391" alt="image" src="https://github.com/user-attachments/assets/291fa023-ce6c-416f-a310-8cbc7cf34082" />

And yes, I began to be hopeful that I came up with a more detailed approach to the digital potentiometer.

The MCP digital potentiometer. The worst electronics concept I've ever encountered!!
I had been studying that kinda of digital potentiometer of MCP!! And I made the entire circuit of the digital potentiometer, encoder, ESP 32 WROOM 32 pins! I spent 3 hours making that circuit. 
(Unfortunately, I didn't take any screenshots for this version of the schematic!)

**Total time spent: 7 hours**


# June 5: The Shock!! 
The MCP Dital potintiometers aren't avalbile on egypt!!! So, I tried to search for another option.
This was the hardest part as I needed to shift to the available option of DAC: X9C103S Digital Potentiometer module (10Kohm), which is even unsuitable with the parameters of the XL4016 pins (I had discovered that later). 
This takes me about 3 hours of searching, making a circuit, and trying to figure out the firmware by the ESP!!! 
<img width="973" height="406" alt="Screenshot 2026-06-07 030118" src="https://github.com/user-attachments/assets/3d89564b-27d6-44c8-a649-f1a63ff7c09f" />
Also, that day I made more detail shematic adding the NTC thermistor and relay connection!!!
<img width="1141" height="782" alt="Screenshot 2026-06-07 024625" src="https://github.com/user-attachments/assets/1a1bd1ef-f3c5-48c3-8a00-af7d251747b5" />
This takes me off overall by two hours!

**Total time spent: 5 hours**


# June 6: Replacing the inefficient and unsuitable X9C103S with the DAC built in the ESP32 s2, then with the PWM
This was the time I found I can't actually use that module, also it was so complicated, and may be i would need a two-layer PCB to achive teh indeed design

So, I made my first schematic for that, and it has two wrong aspects: firstly, the GPIO 33 wasn't even a DAC😂. Secondly, the ADJ pin of the XL4016 is connected to the main supply rail, which will cause it to blow up, or just the Feedback loop gets destroyed!!!
<img width="544" height="228" alt="Screenshot 2026-06-07 043901" src="https://github.com/user-attachments/assets/1e6e8939-5089-4846-b643-305aa3bdaf32" />

Whenever I simulate that part or ask Gemini or ChatGPT (both of them are bad, really baaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaad!!!!!). They were providing counterintuitive opinions. I remained stuck on that for about an hour, entirely trying to figure out what was going on. Until I revise the data sheet of the XL4016, as it had to be connected to the Vout+ pin!!!, where I also find that the filtered PWM can be much better than that of the DAC.
<img width="406" height="188" alt="Screenshot 2026-06-07 044458" src="https://github.com/user-attachments/assets/9a680c95-0e75-4f4f-ab7e-18bbae73c7e3" />
<img width="822" height="362" alt="Screenshot 2026-06-07 220633" src="https://github.com/user-attachments/assets/5566677e-5271-4990-bedd-9167bb997f19" />

simi- final schematic!!
<img width="1201" height="834" alt="Screenshot 2026-06-07 051921" src="https://github.com/user-attachments/assets/b70c387d-2526-432d-ad8d-94cdd50b92e0" />
Draw io. final flow chart edit:
<img width="1260" height="694" alt="image" src="https://github.com/user-attachments/assets/5c8c28e5-ebfe-4e6b-9842-16a4153b9c52" />

This was a long Day!!!!!!

**Total time spent: 6 hours**



# June 7: adding some of the details

I added the circuit of the relay once again (mistake)<img width="1195" height="822" alt="Screenshot 2026-06-07 201926" src="https://github.com/user-attachments/assets/3f2c6851-49cd-4ce8-81f9-8cc9a3659ea0" />
<img width="817" height="754" alt="Screenshot 2026-06-07 234148" src="https://github.com/user-attachments/assets/ce9e1d3c-50d8-47a3-bb38-c986a8a58496" />
That takes half an hour

Also, I made the first power rail schematic, which is much better for the final fabrication
<img width="914" height="636" alt="Screenshot 2026-06-07 234343" src="https://github.com/user-attachments/assets/eddd9802-064e-47e3-9260-4e3e17006e7a" />
and some of the buzzers' circuits:
<img width="502" height="165" alt="Screenshot 2026-06-08 002218" src="https://github.com/user-attachments/assets/cb0fdb42-f640-42b5-9831-cb1bb6abe28b" />
<img width="731" height="241" alt="Screenshot 2026-06-08 002814" src="https://github.com/user-attachments/assets/355e2505-2462-4b87-9a30-df0624201570" />

**Total time spent: 2.5 hours**


# June 8: making each of the power and control rail full independently!
That day, I discovered I won't be making one PCB integrating all of that system. I decided to split the PCBs into power rail and control rails, also decreasing the noise and electronic fluctuations as much as possible. So I made:
Control rail!!
<img width="1096" height="752" alt="Screenshot 2026-06-08 024149" src="https://github.com/user-attachments/assets/1990a1de-dc05-4aad-a259-73d0c314bee0" />
Where the ESP, Fans, NTC, ETC...
Power rail!!
<img width="1029" height="711" alt="Screenshot 2026-06-08 024431" src="https://github.com/user-attachments/assets/e62f1729-2901-4468-ac93-2eaebaa05fc6" />
Where the relay, XL4016, Etc...

**Total time spent: 3 hours**


# June 9: USB Hub!!
This was my actual beginning with the USB Hub. I was juggling between research, cooling, brainstorming, finding good internet ideas, and calculating the actual Ampere and voltage I need, respectively, to meet my parameters.
I take about four hours, thus I need a separate power adaptor of 12V and 5A using another XL4016 with a display for operating 4 type-A female USBs and two Type-C USBs.
<img width="225" height="225" alt="image" src="https://github.com/user-attachments/assets/08b89397-4939-49f7-af2d-25539a644b5e" />

Also, I had chosen all of the materials I needed. 
One's choice was hard, but the most difficult is the choice of the fan, either it's opperation method or even dimensions!!
I chose after a long brainstorming session, I chose to use a simple switch; however, I will leave it open all of the time.
Additionally, I made the Type-C as a rail and the Type-A USBs as another rail parallel to each other, adding a small cool feature:
Although I added a fuse to each rail, what if the fuse just blew out(in case of connection of the four USBs with huge current devices)? Then my family will wait until Peter comes from the trip to find a way to fix that thing?
So, added within each rail to parallel rails leading to the USB's rail, one with only a fuse and the other with a closed switch and fuse, so that the first fuse blew out. We will be able to operate the same rail in another way.
And for the cooling: I was so confused choosing a 12025 fan or a 6015 fan, as the bigger dimensions it is, the quieter it became(good deal!), but less RPM(Bad deal). I chose the 6015 fan for proper cooling, and also after I found that the USB hub had to be relatively small.
<img width="1224" height="1584" alt="image" src="https://github.com/user-attachments/assets/439a4929-5d02-4765-8800-342b931933ba" />

**Total time spent: 4 hours**



# June 11:The Boom and materials writing on Google spreadsheet!
I know it sounds crazy that someone will take three hours to write the BOOM, but how things go in Egypt Cuz i don't know what is available or not, and there is no unified price. Additionally, I may need to categorize the materials into sublists from every shop, which takes much time.
<img width="1438" height="602" alt="image" src="https://github.com/user-attachments/assets/dfe8fd5f-9997-48c6-ae89-471ce35f17dd" />

I know it may sound a little bit unbelievable!!
**Total time spent: 3 hours**




# June 12: Cad with ONSHAPE
<img width="1422" height="650" alt="image" src="https://github.com/user-attachments/assets/be2910af-b01f-4b0f-aff7-02772bbcf405" />
https://lapse.hackclub.com/timelapse/p3Fguz1rJplR
https://lapse.hackclub.com/timelapse/XrkDsW8N9rKd
https://lapse.hackclub.com/timelapse/pcyGR5MnPfYz
https://lapse.hackclub.com/timelapse/gKYMVtGurDUY
https://lapse.hackclub.com/timelapse/yevhhOZqur6d
https://lapse.hackclub.com/timelapse/zA62v7QnH9z3
<img width="638" height="222" alt="image" src="https://github.com/user-attachments/assets/5ef3c3b3-4f53-4ea4-94c5-7ee3f11e90af" />


**Total time spent: 6 hours and a quarter of an hour**

# June 18: re-CAD the whole project and coding 
I found that the whole project enclosure case is not that perfect and is missing a lot of things, even the ports of the outputs and the TFT, so I decided to make another one in the shape of a house, for the sake of making a workbench power supply. Additionally, I made it in a modular way as it can be assembled or separated in onyl one minute and for ht esake the whole project i was inspired by the way framework making thier products so why i amn't adopting this technology? 

<img width="718" height="527" alt="Screenshot 2026-07-17 211532" src="https://github.com/user-attachments/assets/346b3510-26db-4c90-b5a1-05e8619970b4" />
<img width="767" height="567" alt="Screenshot 2026-07-17 235737" src="https://github.com/user-attachments/assets/7e49a6be-a04e-405b-a9e1-868e5d626dfd" />
<img width="828" height="547" alt="Screenshot 2026-07-17 235617" src="https://github.com/user-attachments/assets/13cf2852-aae8-4fb2-b5d1-b708183fc0a4" />
<img width="891" height="552" alt="Screenshot 2026-07-17 235543" src="https://github.com/user-attachments/assets/1072cd89-c4c0-41a0-abc5-c2d20214e79e" />
<img width="652" height="522" alt="Screenshot 2026-07-17 233832" src="https://github.com/user-attachments/assets/91c59673-2fb0-41ba-aa18-5b7ee846ad78" />
<img width="781" height="525" alt="Screenshot 2026-07-17 233730" src="https://github.com/user-attachments/assets/97a38e6e-c96a-46c0-89d6-c7bbc7398cc0" />
<img width="688" height="463" alt="Screenshot 2026-07-17 233712" src="https://github.com/user-attachments/assets/9e7b15cf-1c06-4fbb-a540-1666e8b95585" />
<img width="715" height="568" alt="Screenshot 2026-07-17 233543" src="https://github.com/user-attachments/assets/e875298c-0d59-48aa-aabf-8139c87a331a" />
<img width="758" height="456" alt="Screenshot 2026-07-17 233530" src="https://github.com/user-attachments/assets/c77402b0-656e-407a-b446-96756765730d" />
<img width="595" height="538" alt="Screenshot 2026-07-17 233416" src="https://github.com/user-attachments/assets/ce805277-19e0-4a68-92b5-c3e1c8d74198" />
<img width="718" height="527" alt="Screenshot 2026-07-17 211532" src="https://github.com/user-attachments/assets/79b4dc4a-7d48-446f-b39a-001c592c44b7" />
<img width="837" height="486" a<img width="808" height="476" alt="Screenshot 2026-07-17 235500" src="https://github.com/user-attachments/assets/43b36a9a-25da-437b-8b4b-6891580f98ba" />
<img width="798" height="517" alt="Screenshot 2026-07-17 235417" src="https://github.com/user-attachments/assets/7eb7d74b-8329-4c24-aebf-712693843640" />
<img width="467" height="392" alt="Screenshot 2026-07-17 233907" src="https://github.com/user-attachments/assets/cd342893-6272-4cda-91f9-a66fc4a4cf77" />
<img width="605" height="560" alt="Screenshot 2026-07-17 233849" src="https://github.com/user-attachments/assets/f2d58ac0-25e2-4d72-85cf-b18441cf2143" />
lt="Screenshot 2026-07-17 235530" src="https://github.com/user-attachments/assets/b111d489-329a-47e2-9a9c-e2131ac42f36" />
addtionally i wrote the full code, and mistakenly I found myself already stopped all of the extensions in vs code includeing WAKA time so the whole code of 700 lines and a bunch of other crazy comments I wrote, counted only as one hour 
as shown here in the repo the python source code also https://github.com/PETERFEAYEZ-PERO/Smart-Modular-adjustable-DC-PSU/blob/main/PSU-code.py 



**The total time working on that project till now is: 52 hours**















