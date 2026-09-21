## Fortinet Firewall:

**Fortinet FortiGate is a next-generation firewall (NGFW)** appliance/platform used to secure and control traffic between the Internet, internal networks, servers, users, and other network zones.



### What is FortiGate?

> **FortiGate = Firewall + Routing + VPN + Security + Network Management**

_A typical deployment looks like:_
```
                         Internet
                            |
                       ISP Router
                            |
                         WAN/Port1
                            |
                    +----------------+
                    |    FortiGate   |
                    |     Firewall   |
                    +----------------+
                      |      |      |
                    LAN    DMZ    VPN
                     |      |      |
                  Users   Servers  Remote Users
```



### Core Capabilities & Features:
- **Next-Generation Firewall (NGFW) & Stateful Inspection**: Beyond basic packet filtering, FortiGate monitors stateful traffic and provides granular control based on applications, users, and devices rather than just ports and IP addresses.  
- **Deep Packet Inspection (DPI) & SSL Inspection**: High-speed inspection of encrypted traffic (HTTPS/SSL) ensures that hidden malware or vulnerabilities are intercepted without sacrificing network performance.  
- **Unified Threat Management (UTM)**: Integrates essential security functions into a single platform, including:
    - **Intrusion Prevention System (IPS)**: Detects and blocks network intrusions.  
    - **Web & DNS Filtering**: Restricts access to malicious, risky, or inappropriate websites.  
    - **Antivirus & Anti-Malware**: Real-time scanning to stop ransomware, viruses, and zero-day payloads.
    - **Application Control**: Identifies and regulates application usage across the network.  
- **Secure SD-WAN**: Merges high-performing routing with next-generation security to optimize branch office connectivity while maintaining direct, secure internet access.  
- **VPN Support**: Offers robust IPsec and SSL-VPN capabilities for secure remote access and site-to-site connectivity.




### Major FortiGate Features:

| Feature                 | Purpose                                              |
| ----------------------- | ---------------------------------------------------- |
| **Firewall Policy**     | Allow/deny network traffic                           |
| **NAT**                 | Translate private ↔ public IP addresses              |
| **Routing**             | Static routes, default routes, dynamic routing       |
| **VLAN**                | Segment networks                                     |
| **DHCP Server**         | Assign IP addresses to clients                       |
| **DNS**                 | DNS forwarding/resolution                            |
| **IPsec VPN**           | Site-to-site VPN                                     |
| **SSL VPN / ZTNA**      | Remote-user access                                   |
| **Web Filter**          | Control website access                               |
| **Application Control** | Control applications such as Facebook, YouTube, etc. |
| **IPS**                 | Detect/block network attacks                         |
| **Antivirus**           | Scan network traffic for malware                     |
| **DNS Filter**          | Block malicious/unwanted domains                     |
| **Traffic Shaping**     | Control bandwidth                                    |
| **SD-WAN**              | Intelligent use of multiple WAN connections          |
| **High Availability**   | Active-passive/active-active firewall clusters       |
| **Logging**             | Traffic and security event logging                   |




### FortiGate Interfaces:

_A FortiGate commonly has interfaces such as:_
```
Port1 → WAN / Internet
Port2 → LAN
Port3 → DMZ
Port4 → Server Network
```


_For example:_
```
Internet
    |
    | Public IP
    |
  Port1
+-----------+
| FortiGate |
+-----------+
  Port2
    |
    | 192.168.11.1/24
    |
    |
  Switch
    |
+---+---+---+
|   |   |   |
PC  PC Server
```




### Firewall Policy:

Firewall policies determine who can communicate with whom and what they can do.

_Example:_
```
LAN → Internet

Incoming Interface:  port2
Outgoing Interface:  port1
Source:              LAN subnet
Destination:         all
Service:             ALL
Action:              ACCEPT
NAT:                 ENABLE
```


FortiGate evaluates traffic against policies from top to bottom.

_Traffic flow:_
```
Client
192.168.11.5
     |
     | HTTPS
     ↓
FortiGate
     |
     | NAT
     ↓
Internet
```




### VPN:


#### Site-to-Site IPsec VPN:

_Example:_
```
Office A                         Office B

10.10.10.0/24                   10.20.20.0/24
     |                                |
 FortiGate                         FortiGate
     |                                |
     +--------- IPsec VPN ------------+
```



#### Remote Access VPN:

```
Remote User
     |
 Internet
     |
 FortiGate
     |
 Internal Network
```



### High Availability

_For critical environments:_
```
                 Internet
                    |
              +-----+-----+
              |           |
          FortiGate-1  FortiGate-2
             Active      Standby
              |           |
              +-----+-----+
                    |
                  LAN
```






### Useful FortiGate CLI:

```conf
## Check system information:
get system status

## Get FortiGate-VM license information (VMware, KVM, AWS, GCP, Azure):
diagnose debug vm-print-license
diag debug vm-print-license

## Check interfaces:
get system interface

## Show interface configuration:
show system interface
show system interface port1

## Check routing table:
get router info routing-table all

## Show DNS info: 
show system dns

## Check ARP:
get system arp

## Ping:
execute ping 8.8.8.8

## Traceroute:
execute traceroute 8.8.8.8

## DNS test:
execute nslookup google.com

## Graceful shutdown:
execute shutdown


## Reset to factory defaults (Do not run this on a production): 
execute factoryreset
```



---
---



