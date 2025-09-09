# Footprinting
## scanning host on network
1. nmap
` nmap -sn < gateway >/cidr `


Example
```
Nmap scan report for 192.168.0.1
Host is up (0.018s latency).
MAC Address: B0:4E:26:22:5E:DA (TP-Link Technologies)
Nmap scan report for 192.168.0.103
Host is up (0.00067s latency).
MAC Address: C0:BF:BE:3F:61:E7 (Unknown)
Nmap scan report for 192.168.0.105
Host is up (0.16s latency).
MAC Address: AC:19:8E:12:E8:EB (Intel Corporate)
Nmap scan report for 192.168.0.106
Host is up (0.17s latency).
MAC Address: AC:19:8E:12:E8:EB (Intel Corporate)
Nmap scan report for 192.168.0.107
Host is up (0.16s latency).
MAC Address: 78:2B:46:8F:F1:60 (Intel Corporate)
Nmap scan report for 192.168.0.108
Host is up (0.17s latency).
MAC Address: AC:19:8E:12:E8:EB (Intel Corporate)
Nmap scan report for 192.168.0.109
Host is up (0.019s latency).
MAC Address: 08:00:27:09:0E:2C (PCS Systemtechnik/Oracle VirtualBox virtual NIC)
Nmap scan report for 192.168.0.112
Host is up (0.36s latency).
MAC Address: 28:F3:66:30:4C:D5 (Shenzhen Bilian electronic)
Nmap scan report for 192.168.0.113
Host is up (0.21s latency).
MAC Address: 44:A3:BB:19:C0:03 (Unknown)
Nmap scan report for 192.168.0.110
Host is up.
Nmap done: 256 IP addresses (10 hosts up) scanned in 6.73 seconds
```
2. Netdiscover
` sudo netdiscover < gateway > /cidr `


Example
```
 Currently scanning: Finished!   |   Screen View: Unique Hosts                                                               
                                                                                                                             
 25 Captured ARP Req/Rep packets, from 9 hosts.   Total size: 1500                                                           
 _____________________________________________________________________________
   IP            At MAC Address     Count     Len  MAC Vendor / Hostname      
 -----------------------------------------------------------------------------
 192.168.0.103   c0:bf:be:3f:61:e7      1      60  AzureWave Technology Inc.                                                 
 192.168.0.109   08:00:27:09:0e:2c      1      60  PCS Systemtechnik GmbH                                                    
 192.168.0.106   ac:19:8e:12:e8:eb      1      60  Intel Corporate                                                           
 192.168.0.108   ac:19:8e:12:e8:eb      1      60  Intel Corporate                                                           
 192.168.0.112   28:f3:66:30:4c:d5      1      60  Shenzhen Bilian electronic CO.,LTD                                        
 192.168.0.1     b0:4e:26:22:5e:da      2     120  TP-LINK TECHNOLOGIES CO.,LTD.                                             
 192.168.0.105   ac:19:8e:12:e8:eb      4     240  Intel Corporate                                                           
 192.168.0.111   26:fa:22:de:9a:7a     11     660  Unknown vendor                                                            
 192.168.0.115   8a:07:02:29:95:cd      3     180  Unknown vendor                                                            
```
