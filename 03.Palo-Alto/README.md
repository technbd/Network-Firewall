## Palo Alto Networks Firewall: 

Palo Alto Networks is a cybersecurity vendor known for its **Next-Generation Firewall (NGFW)** technology. Its firewalls are used in enterprise networks, data centers, branch offices, and cloud environments.

The main difference from a traditional firewall is that Palo Alto can **identify applications and users and inspect traffic contents**, rather than relying only on **IP addresses and port numbers**.




### Core Technologies: 

- **App-ID**: Identifies the **exact application** (e.g., SSL, YouTube, BitTorrent, Salesforce) regardless of port, protocol, or evasive techniques.
- **User-ID**: Integrates with directory services (like Active Directory) to tie firewall rules to **specific users and groups** instead of just IP addresses.
- **Content-ID**: **Inspects traffic payloads** to stop threats, including viruses, spyware, vulnerabilities, and custom-coded malware.
- **Single-Pass Architecture**: Processes networking, application identification, user mapping, and threat inspection simultaneously in a single engine pass to keep latency low.



### Palo Alto vs. FortiGate:


| Capability | Palo Alto | FortiGate |
|------------|-----------|-----------|
| Application identification | App-ID | Application Control |
| User-based policies | User-ID | Identity-based policies |
| Threat prevention | Threat Prevention / Advanced Threat Prevention | IPS and Antivirus |
| Website filtering | URL Filtering | Web Filter |
| Malware sandboxing | WildFire | FortiSandbox |
| Central management | Panorama / Strata Cloud Manager | FortiManager / FortiGate Cloud |
| Operating system | PAN-OS | FortiOS |
| Configuration activation | Commit | Configuration changes generally apply immediately |




### Typical traffic flow:

```
Internal users (Trust / LAN)
          |
          v
  Next-Generation Firewall
  - Security policy
  - Application identification
  - User identity (if configured)
  - NAT and routing
  - Threat inspection (if licensed/configured)
          |
          v
     Internet (Untrust / WAN)
```




### Versions this guide is based on:

```
    EVE Image Foldername	Downloaded Filename	    Version	vCPUs	vRAM	Console	  Qemu Version
1.	paloalto-8.0.1	        PA-VM-KVM-8.0.1.qcow2	8.0.1	2	    4096	telnet	  2.12.0
2.	paloalto-9.0.X	        PA-VM-KVM-9.0.1.qcow2	9.0.x	4	    8192	telnet	  2.12.0
3.	paloalto-10.1.1	        PA-VM-KVM-10.1.1.qcow2	10.1.1	4	    8192	telnet	  2.12.0
4.	paloalto-11.0.0	        PA-VM-KVM-11.0.0.qcow2	11.0.0	4	    8192	telnet	  5.2.0
```



### CLI Access Modes:

#### 1. Operational Mode (>):
Operational mode is used to **monitor, verify, troubleshoot, and execute operational commands**.

```
admin@PA-VM>
```


_Common commands:_
- `show system info`	- Display system information
- `show interface all`	- View interface status
- `show routing route`	- Display routing table
- `show session all`	- View active sessions
- `show jobs all`	- Check running and completed jobs
- `ping host 8.8.8.8`	- Test connectivity
- `configure`	- Enter Configuration Mode
- `request shutdown system` - To perform a graceful shutdown
- `request restart system`  - To restart the device



#### 2. Configuration Mode (#): 
Configuration mode is used to **create, modify, and delete firewall configuration settings**.

```
admin@PA-VM> configure
admin@PA-VM#

admin@PA-VM# set network interface ethernet ethernet1/2 layer3 ip 10.1.1.5/24
admin@PA-VM# commit
```


_Common commands:_
- `set`	- Create or modify configuration
- `delete`	- Remove configuration
- `edit`	- Enter a configuration hierarchy
- `show`	- Display candidate configuration
- `validate full`	- Validate the candidate configuration
- `commit`	- Apply candidate configuration
- `exit`	- Leave the current mode or hierarchy




---
---


