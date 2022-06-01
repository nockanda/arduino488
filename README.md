# arduino488
homeassistant+ESPNOW<BR>
![488-1_bb](https://user-images.githubusercontent.com/106683637/171434047-9e906fe8-15ac-4aa6-9811-78eab4331291.jpg)
https://youtu.be/yDNLyEdO9e4<BR>

홈어시스턴트에 ESPNOW를 연동해서 사용하는 방법!(연구주제)
이번편은 녹칸다의 홈어시스턴트 내용이다!
최근 녹칸다가 ESPNOW로 메시네트워크를 구성하는 예제를 만들었다!
메시네트워크에서 인터넷이 연결되는 보드를 홈어시스턴트(home assistant)에 연결하는 작업을 해보자!

일단 espnow는 인터넷공유기의 연결범위 밖에 있는 센서값을 수집하기 위해서 사용하고 있다고 생각하면 된다!
그럼 센서데이터를 수집하는 전용노드가 있고 그것을 홈어시스턴트로 넘겨보는 것이다!
(ESPNOW는 ESP보드들 끼리 아무런 장치 없이 데이터를 주고 받을 수 있는 전용 프로토콜 이다)

아래와 같이 2가지 방법이 있을 수 있다!(테스트 안해봄)
1.HASS의 애드온인 ESPHOME에 library를 등록해서 사용하는 방법!
2.HASS의 애드온인 노드레드(node-red)에 MQTT로 연결하는 방법!

뭐가 좋을지는 직접 해보면서 판단해보도록 하자!
일단 1번의 경우 외부 라이브러리를 어디다가 둬야하는지 컴파일이 잘되는지 이런 것을 사전에 확인을 못해본 상태라 여의치 않으면 바로 2번으로 넘어갈 수 도 있다!

(esphome에서 espnow를 사용할 수 있도록 누군가가 만들어준게 있다)
https://github.com/iphong/esphome-espnow

페이로드 '{{ trigger.payload }}'
JSON페이로드 '{{ trigger.payload_json.name }}'

MAC어드레스출력(469-1)
양방향기본코드(475-1)
  
(실제로한거)

1.ESPNOW의 개념을 다시 확인하기 위해서 간단한 양방향 예제 구현하기!<BR>
2.홈어시스턴트와 ESPHOME을 이용해서 양방향통신하기!<BR>
3.ESP8266보드에서 전송한 MQTT메시지를 홈어시스턴트에서 수신하는 예시를 만드시오!<BR>
4.A보드에 가상의 온습도센서가 있다! A보드가 B보드에게 ESPNOW로 데이터를 전송하고 B보드는 인터넷에 연결한다음 MQTT로 홈어시스턴트에 대시보드에 출력하시오!<BR>
5.홈어시스턴트의 애드온인 노드레드를 이용해서 A,B보드간에 업로드되는 센서데이터를 홈어시스턴트 화면에 출력하시오!(보드 코드는 4와동일함)<BR>
6.홈어시스턴트에서 A보드쪽으로 ESPNOW를 이용해서 특정한 메시지를 전송하시오!<BR>
7.노드레드에 인젝트노드를 이용해서 ESPNOW데이터를 전송시키시오!(보드 코드는 6과 동일함)<BR>
  
(Machine translation)<BR>
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
  
1.Implement a simple interactive example to reconfirm the concept of ESPNOW!<BR>
2.Two-way communication using Home Assistant and ESPHOME!<BR>
3.Make an example of receiving the MQTT message sent by the ESP8266 board from the home assistant!<BR>
4.A board has a virtual temperature and humidity sensor! Board A sends data to board B via ESPNOW, board B connects to the Internet, and then prints it on the dashboard to home assistant with MQTT!<BR>
5.Use Node Red, an add-on for Home Assistant, to output the sensor data uploaded between A and B boards on the Home Assistant screen! (Board code is the same as 4)<BR>
6.Send a specific message from the home assistant to the A board using ESPNOW!<BR>
7.Transmit ESPNOW data to Node Red using the inject node! (Board code is the same as 6)<BR>
  
 
