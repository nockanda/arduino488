# arduino488
homeassistant+ESPNOW<BR>
![488-1_bb](https://user-images.githubusercontent.com/106683637/171434047-9e906fe8-15ac-4aa6-9811-78eab4331291.jpg)
How to use ESPNOW in conjunction with Home Assistant! (Research Topic)
This episode is about Nokanda's home assistant!
Recently, Nokanda made an example of configuring a mesh network with ESPNOW!
Let's try to connect the Internet-connected board to the home assistant in the mesh network!

First of all, you can think of espnow as being used to collect sensor values ​​that are outside the connection range of the router!
Then there is a dedicated node that collects sensor data, and hand it over to the home assistant!
(ESPNOW is a dedicated protocol that can send and receive data between ESP boards without any device)

There can be two ways as below! (I haven't tested it)<BR>
1.How to register and use the library in ESPHOME, an add-on of HASS!<BR>
2.How to connect to node-red, an add-on of HASS, by MQTT!<BR>

Let's try it for ourselves and decide which one is better!
First of all, in case 1, where to put the external library and whether the compilation works well, I have not been able to check these things beforehand.

(Someone made it so you can use espnow in esphome)
  https://github.com/iphong/esphome-espnow
  
1. Implement a simple interactive example to reconfirm the concept of ESPNOW!<BR>
2. Two-way communication using Home Assistant and ESPHOME!<BR>
3.Make an example of receiving the MQTT message sent by the ESP8266 board from the home assistant!<BR>
4.A board has a virtual temperature and humidity sensor! Board A sends data to board B via ESPNOW, board B connects to the Internet, and then prints it on the dashboard to home assistant with MQTT!<BR>
5. Use Node Red, an add-on for Home Assistant, to output the sensor data uploaded between A and B boards on the Home Assistant screen! (Board code is the same as 4)<BR>
6. Send a specific message from the home assistant to the A board using ESPNOW!<BR>
7. Transmit ESPNOW data to Node Red using the inject node! (Board code is the same as 6)<BR>
 
