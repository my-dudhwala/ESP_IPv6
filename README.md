# ESP_IPv6
I am working(Actually trying) to connect ESP32 or ESP8266 with my IPv6 router. This repo is made to update my work. I'm sharing this repo where I have to update status of my work, I am open to modify this document from anyone. And I am open to collaborate on this until the project works successfully.

## Example codes and errors
- 20/09/2023
  - esp_http_client(Builtin exaple)
> IDF 4.4.5
> Errors:
> E (13733) esp-tls: [sock=54] select() timeout
> E (13734) TRANSPORT_BASE: Failed to open a new connection: 32774
> E (13735) HTTP_CLIENT: Connection failed, sock < 0
> E (13740) HTTP_CLIENT: HTTP GET request failed: ESP_ERR_HTTP_CONNECT

## Old updates
> This updates were initially updated on reddit post, now its copy is placed below,

Problem statement: I am using generic ESP32 module with ESP Wroom 32 chip. I am trying to connect it with WiFi router with IPv6 configuration as the router is IPv6 only. I have spent hours of working on it, I have tried many codes from GitHub, ChatGPT and many other articles. Please guide me regarding this, and take me as a beginner, Thank you

#### Update 1 :
After searching a little, I found that the "Station" example, inside WiFi>Getting Started directory. And I'm getting 7 identifier errors, And thank you for your response, I am willing to step further as your instruction, please take me as a beginner, a warm thank you

__Edit:__ I am using visual studio code with Pio, and I have recognised that this functionality is not available in Arduino framework, and this is also a reason to use IDF.

#### Update 2 : 
The code it uploaded successfully, previously It was showing errors in VS code.

#### Update 3 :
Managed to compile and upload the code with IDF 4.4.5 in 2-3 days, got printed global and local IPv6, but not sure if it will work to connect with internet or not, I will try to update if I will remember, thanks for giving me hope

#### Update 4 :

(This is copied comment from a new reddit and IDF post)Getting above error in IDF while compiling a code, which is a merged code. I have merged 2 codes, one is IPv6 from a git repo(Link is given below) and the second code is esp32 with google sheet(Link is attached), help please, and I am not sure that the IPv6 code is working correctly or not but I have managed to get serial output. take me as a very beginner in IDF, thank you

GitHub for IPv6:https://github.com/amitesh-singh/EspDDNS_with_IDF

ESP32 and Google Sheet automation:https://iotdesignpro.com/articles/esp32-data-logging-to-google-sheets-with-google-scripts

From here I am updating everything on different document, I will release it somewhere if need be.

_Future updates: I am placing all of my updates on my github repo, link is given below,_

https://github.com/my-dudhwala/ESP_IPv6/
