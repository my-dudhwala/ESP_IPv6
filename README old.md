# ESP_IPv6
I am working(Actually trying) to connect ESP32 or ESP8266 with my IPv6 router. This repo is made and shared to update status of my work and keep documentation of the process flow, I am open to modify this document from anyone. And I am open to collaborate on this until the project works successfully.

> You are requested to formate this document, change where you think it should be there.
## Important updates  
I am using **IDF version 4.4.5** to test some codes which are supported in this version without any problem.  

**Code related updates**  
According to IDF documents, "Enable IPv4 stack. If you want to use IPv6 only TCP/IP stack, disable this." but I'm not seeing any exact option to the same, but yea, there are related options available. _There is an option named "Enable IPv4 Link-Local Addressing(AUTOIP)" but this is not disabling._
### Several updates
#### 21/09/2023  
**Reddit**  
1. [IPv6 Community - Does anyone have connected Microcontroller(ESP) to IPv6 internet?](https://www.reddit.com/r/ipv6/comments/16ods1t/comment/k1k2rtl/)  
2. [Arduino Community - How to connect ESP32 to WiFi with IPv6 configuration?](https://www.reddit.com/r/arduino/comments/15spv4q/how_to_connect_esp32_to_wifi_with_ipv6/)  
3. [Arduino Community - Is it passible to connect ESP32 with IPv6 internet?](https://www.reddit.com/r/arduino/comments/16o9yj0/comment/k1kyf3l/?context=3)  

**GitHub**  
1. [EspDDNS_with_IDF - GitHub](https://github.com/amitesh-singh/EspDDNS_with_IDF)

#### Error in different code
Inbuilt example Code: Espressif\frameworks\esp-idf-v4.4.5\examples\protocols\http_request>  
[On GitHub](https://github.com/espressif/esp-idf/blob/master/examples/protocols/http_request/main/http_request_example_main.c)  
**Error :** socket connect failed errno=113  
**Serial Output :**  

I (4966) esp_netif_handlers: example_connect: sta ip: 192.168.0.236, mask: 255.255.255.0, gw: 192.168.0.254

I (4967) example_connect: Got IPv4 event: Interface "example_connect: sta" address: 192.168.0.236

I (5550) example_connect: Got IPv6 event: Interface "example_connect: sta" address: fe80:0000:0000:0000:96e6:86ff:fe05:0dd0, type: ESP_IP6_ADDR_IS_LINK_LOCAL

I (7549) example_connect: Got IPv6 event: Interface "example_connect: sta" address: 2002:c0a8:00fe:0001:96e6:86ff:fe05:0dd0, type: ESP_IP6_ADDR_IS_GLOBAL

I (7554) example_connect: Got IPv6 event: Interface "example_connect: sta" address: 2002:c0a8:0165:0001:96e6:86ff:fe05:0dd0, type: ESP_IP6_ADDR_IS_GLOBAL

I (7568) example_connect: Connected to example_connect: sta

I (7574) example_connect: - IPv4 address: 192.168.0.236

I (7580) example_connect: - IPv6 address: fe80:0000:0000:0000:96e6:86ff:fe05:0dd0, type: ESP_IP6_ADDR_IS_LINK_LOCAL

I (7591) example_connect: - IPv6 address: 2002:c0a8:00fe:0001:96e6:86ff:fe05:0dd0, type: ESP_IP6_ADDR_IS_GLOBAL

I (7602) example_connect: - IPv6 address: 2002:c0a8:0165:0001:96e6:86ff:fe05:0dd0, type: ESP_IP6_ADDR_IS_GLOBAL

I (7627) example: DNS lookup succeeded. IP=93.184.216.34

I (7628) example: ... allocated socket

I (8885) wifi:<ba-add>idx:1 (ifx:0, b0:be:76:59:c5:02), tid:6, ssn:2, winSize:64

**E (25890) example: ... socket connect failed errno=113**

I (29891) example: DNS lookup succeeded. IP=93.184.216.34

I (29892) example: ... allocated socket

**E (48405) example: ... socket connect failed errno=113**

I (52406) example: DNS lookup succeeded. IP=93.184.216.34

I (52407) example: ... allocated socket

## Menuconfig: Every setting about IPv6 20/09/2023
**Note:** For this I have searched on IDF article(Link is given below) about all of IPv6 menuconfig options, if you don't know about menuconfig, probably you are not using IDF, in IDF there is a long GUI setting to configure ESP code automatically. If you are using IDF and dont know menuconfig, enter "idf.py menuconfig" in cmd(Windows) you will know it soon in your ESP IDF journey...!, I am sorry if you are not using CLI, and yea, the configuration menu is also available in VS Code, IDF extension..., but CLI is more faster than VS code, I use VS code for editing the code only, Thanks  

[ESP IDF menuconfig](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-reference/kconfig.html#configuration-options-reference)  
  
### Every setting containing **"IP6"** word in main title is given below, as of 20/09/2023
  
**_CONFIG_LWIP_IP6_FRAG_**  
Enable fragment outgoing IP6 packets

Found in: Component config > LWIP

Enabling this option allows fragmenting outgoing IP6 packets if their size exceeds MTU.

Default value:
Yes (enabled)  
  
_**CONFIG_LWIP_IP6_REASSEMBLY**_  
Enable reassembly incoming fragmented IP6 packets  

Found in: Component config > LWIP  

Enabling this option allows reassemblying incoming fragmented IP6 packets.  

Default value:  
No (disabled)   
  
_**CONFIG_LWIP_HOOK_IP6_INPUT**_  
IPv6 packet input  
  
Found in: Component config > LWIP > Hooks  
  
Enables custom IPv6 packet input. Setting this to “default” provides weak implementation stub that could be overwritten in application code. Setting this to “custom” provides hook’s declaration only and expects the application to implement it.  
  
Available options:  
No hook declared (LWIP_HOOK_IP6_INPUT_NONE)  
  
Default (weak) implementation (LWIP_HOOK_IP6_INPUT_DEFAULT)  
  
Custom implementation (LWIP_HOOK_IP6_INPUT_CUSTOM)  
  
**_CONFIG_LWIP_HOOK_IP6_ROUTE_**  
IPv6 route Hook  
  
Found in: Component config > LWIP > Hooks  
  
Enables custom IPv6 route hook. Setting this to “default” provides weak implementation stub that could be overwritten in application code. Setting this to “custom” provides hook’s declaration only and expects the application to implement it.  
  
Available options:  
No hook declared (LWIP_HOOK_IP6_ROUTE_NONE)  
  
Default (weak) implementation (LWIP_HOOK_IP6_ROUTE_DEFAULT)  
  
Custom implementation (LWIP_HOOK_IP6_ROUTE_CUSTOM)  
  
_**CONFIG_LWIP_HOOK_IP6_SELECT_SRC_ADDR**_  
IPv6 source address selection Hook  
  
Found in: Component config > LWIP > Hooks  
  
Enables custom IPv6 source address selection. Setting this to “default” provides weak implementation stub that could be overwritten in application code. Setting this to “custom” provides hook’s declaration only and expects the application to implement it.  
  
Available options:  
No hook declared (LWIP_HOOK_IP6_SELECT_SRC_ADDR_NONE)  
  
Default (weak) implementation (LWIP_HOOK_IP6_SELECT_SRC_ADDR_DEFAULT)  
  
Custom implementation (LWIP_HOOK_IP6_SELECT_SRC_ADDR_CUSTOM)  

_**CONFIG_LWIP_IP6_DEBUG**_  
Enable IP6 debug messages  
  
Found in: Component config > LWIP > CONFIG_LWIP_DEBUG  
  
Default value:  
No (disabled) if CONFIG_LWIP_DEBUG  

### Every setting containing **"IPv6"** word in main title is given below, as of 20/09/2023

_**CONFIG_LWIP_IPV6_DHCP6**_  
Enable DHCPv6 stateless address autoconfiguration  
  
Found in: Component config > LWIP  
  
Enable DHCPv6 for IPv6 stateless address autoconfiguration. Note that the dhcpv6 client has to be started using dhcp6_enable_stateless(netif); Note that the stateful address autoconfiguration is not supported.  
  
Default value:  
No (disabled) if CONFIG_LWIP_IPV6_AUTOCONFIG  

_**CONFIG_LWIP_IPV6**_  
Enable IPv6  
  
Found in: Component config > LWIP  
  
Enable IPv6 function. If not use IPv6 function, set this option to n. If disabling LWIP_IPV6 then some other components (coap and asio) will no longer be available.  

Default value:  
Yes (enabled)  
  
_**CONFIG_LWIP_IPV6_ND6_NUM_NEIGHBORS**_  
Max number of entries in IPv6 neighbor cache  
  
Found in: Component config > LWIP  
  
Config max number of entries in IPv6 neighbor cache  
  
Range:  
from 3 to 10  
  
Default value:  
5  
  
[More about Neighbor Discovery](https://blogs.infoblox.com/ipv6-coe/ipv6-neighbor-discovery-cache-part-1-of-2/)  

_**CONFIG_LWIP_IPV6_MEMP_NUM_ND6_QUEUE**_  
Max number of IPv6 packets to queue during MAC resolution  
  
Found in: Component config > LWIP  
  
Config max number of IPv6 packets to queue during MAC resolution.  
  
Range:  
from 3 to 20  
  
Default value:  
3  

_**CONFIG_LWIP_IPV6_RDNSS_MAX_DNS_SERVERS**_  
Use IPv6 Router Advertisement Recursive DNS Server Option  
  
Found in: Component config > LWIP  
  
Use IPv6 Router Advertisement Recursive DNS Server Option (as per RFC 6106) to copy a defined maximum number of DNS servers to the DNS module. Set this option to a number of desired DNS servers advertised in the RA protocol. This feature is disabled when set to 0.  
  
Default value:  
0 if CONFIG_LWIP_IPV6_AUTOCONFIG  
  
_**CONFIG_LWIP_ND6**_  
LWIP NDP6 Enable/Disable  
  
Found in: Component config > LWIP  
  
This option is used to disable the Network Discovery Protocol (NDP) if it is not required. Please use this option with caution, as the NDP is essential for IPv6 functionality within a local network.  
  
Default value:  
Yes (enabled)  


  
  
## Example codes and errors  
- 20/09/2023
  - esp_http_client(Builtin exaple)
> IDF 4.4.5
> Errors:  
> E (13733) esp-tls: [sock=54] select() timeout  
> E (13734) TRANSPORT_BASE: Failed to open a new connection: 32774  
> E (13735) HTTP_CLIENT: Connection failed, sock < 0  
> E (13740) HTTP_CLIENT: HTTP GET request failed: ESP_ERR_HTTP_CONNECT  

## Initial and old updates
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

[Reddit post](https://www.reddit.com/r/arduino/comments/15spv4q/how_to_connect_esp32_to_wifi_with_ipv6/)

GitHub for IPv6:https://github.com/amitesh-singh/EspDDNS_with_IDF

ESP32 and Google Sheet automation:https://iotdesignpro.com/articles/esp32-data-logging-to-google-sheets-with-google-scripts

From here I am updating everything on different document, I will release it somewhere if need be.

_Future updates: I am placing all of my updates on my github repo, link is given below,_

https://github.com/my-dudhwala/ESP_IPv6/
