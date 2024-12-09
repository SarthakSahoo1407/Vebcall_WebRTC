# Spring Boot WebRTC Peer-to-Peer Video Communication Room Based

#### Technologies:

- WebRTC
- Socket.IO
- NginX
- Docker


WebRTC (Web Real-Time Communication): An open-source project that provides real-time communication between web browsers and mobile applications. Mostly used for video, audio communications, screen sharing, and streaming.



SocketIO: A JavaScript library designed for real-time, bidirectional communication. In this project, I have implemented "netty-socket.io" ( Java Spring Boot compatible) as a signaling mechanism.


### Instructions


#### write your local ip for each step

1) **Generate certificates:** 
   - Find your local ip address of your computer/host like `192.168.0.100` 
   - Please create an empty ssl folder under the project root directory

`mkdir ssl && openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout ssl/private_key.pem -out ssl/certificate.pem -subj "//C=US//ST=California//L=San Francisco//O=MyOrganization//OU=MyDepartment//CN=<YOUR_LOCAL_IP>"`

   - Past the generated ssl certificate in rssl foler under root directory

2) **update nginx.conf**

change the current ip with your local ip same as step 1

3) **update client.js file in resources**

file location: `src/main/resources/static/client.js`

```let socket = io.connect("https://192.168.0.100", {secure: true});```
change the current ip with your local ip same as step 2


4) **build docker image**

`docker-compose up -d --build`


