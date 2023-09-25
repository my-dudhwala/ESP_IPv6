### http_request inbuilt code with errors

#### Serial output

I (4374) wifi:connected with TP-Link_C502 R&D, aid = 1, channel 2, BW20, bssid = b0:be:76:59:c5:02  
I (4374) wifi:security: WPA2-PSK, phy: bgn, rssi: -34  
I (4384) wifi:pm start, type: 1  
  
I (4394) wifi:<ba-add>idx:0 (ifx:0, b0:be:76:59:c5:02), tid:0, ssn:0, winSize:64  
I (4434) wifi:AP's beacon interval = 102400 us, DTIM period = 1  
I (5384) esp_netif_handlers: example_netif_sta ip: 192.168.0.236, mask: 255.255.255.0, gw: 192.168.0.254  
I (5384) example_connect: Got IPv4 event: Interface "example_netif_sta" address: 192.168.0.236  
I (5564) example_connect: Got IPv6 event: Interface "example_netif_sta" address: fe80:0000:0000:0000:96e6:86ff:fe05:0dd0, type: ESP_IP6_ADDR_IS_LINK_LOCAL  
I (5564) example_common: Connected to example_netif_sta  
I (5574) example_common: - IPv4 address: 192.168.0.236,  
I (5574) example_common: - IPv6 address: fe80:0000:0000:0000:96e6:86ff:fe05:0dd0, type: ESP_IP6_ADDR_IS_LINK_LOCAL  
I (5594) main_task: Returned from app_main()  
I (5634) wifi:<ba-add>idx:1 (ifx:0, b0:be:76:59:c5:02), tid:6, ssn:2, winSize:64  
I (7564) example_connect: Got IPv6 event: Interface "example_netif_sta" address: 2002:c0a8:00fe:0001:96e6:86ff:fe05:0dd0, type: ESP_IP6_ADDR_IS_GLOBAL  
I (7564) example_connect: Got IPv6 event: Interface "example_netif_sta" address: 2405:0201:2002:f043:96e6:86ff:fe05:0dd0, type: ESP_IP6_ADDR_IS_GLOBAL  
I (8574) example: DNS lookup succeeded. IP=38.6.40.0  
I (8574) example: ... allocated socket  
**E (26824) example: ... socket connect failed errno=113**  
