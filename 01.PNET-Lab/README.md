## PNET Lab:

**PNETLab (Packet Network Emulator Tool Lab)** is a network and system lab platform used to create, run, practice, test, and share virtual networking environments. It is especially useful for learning Cisco, Juniper, Arista, MikroTik, Fortinet, Linux, Docker, and other technologies.

PNETLab itself **runs as a virtual machine**, and you access its lab environment through a web browser. The official documentation describes deploying the PNETLab `.ova` on virtualization platforms such as VMware.



### Features:

Some useful features are:

| Feature                 | Description       |
| :---------------------- | :---------------- |
| **OFFLINE VERSION**                   | Offline version with full features of the Online version and is completely free. |
| **Price**                             | Free |
| **Lab Store**                         | A place to share labs (online) with many people. |
| **Device Store**                      | Allows you to get devices with only one click. |
| **IOS (Cisco, Juniper, Arista...)**   | Included in the lab when you download from the store (saves time for learning). |
| **Docker Integrated**                 | Included in the devices tab button, just download and use. |
| **User's roles**                      | Admin, User (depends on your definition). |
| **Learning Center**                   | Full feature access. |
| **Lab Timer**                         | Timer for lab training. |
| **Lab Task (workbook)**               | Add PDF or HTML workbooks to the lab file. |
| **Running Lab Management**            | Users can run multiple labs; running labs appear in the Running Lab tab management. |
| **Unlimited node per Lab**            | Unlimited nodes per lab. |
| **Wireshark Capture**                 | Local and Docker Wireshark integrated. |
| **Telnet**                            | Local and HTML Console. |
| **Hot connections**                   | Live Node interface connections. |
| **NAT Cloud**                         | Integrated PNETLab NAT Cloud. |
| **Multi startup configuration per lab** | Multi startup configuration per lab. |
| **Custom Image template**             | Option to use custom image templates. |
| **Link design feature**               | Option to change connection color and style. |
| **Rich integrated text editor**       | Rich HTML text editor for text and object management in the lab. |
| **Admin user option to join in other user labs** | Admin can join other user labs in a parallel session. |
| **Admin user option to open a parallel console session to other user nodes** | Admin can open a parallel console session to other user nodes. |
| **Running labs and nodes management** | Admin can manage other users' running labs and nodes (join or stop labs/nodes). |
| **Info about HDD/labs use per user**  | Information about user HDD resource usage on the web GUI. |
| **Dark Mode**                         | Switch lab view mode to Dark or Light mode. |
| **3D Model**                          | Switch lab view to 3D Mode. |
| **Change the size of the node icon**  | Change the size of the node icon in the lab. |
| **Proxy Configuration**               | Proxy configuration support in PNETLab. |
| **Change the Label position**         | Change the label position in the lab. |
| **Manage RAM, CPU, HDD**              | Manage RAM, CPU, and HDD for each Node, User, and Lab. |
| **Limit RAM, CPU, HDD**               | Ability to limit RAM, CPU, and HDD per user. If thresholds are exceeded, users cannot open new nodes or labs. |
| **Beautiful Icons**                   | Allows users to add more icons. |



### What can you run?

PNETLab supports different types of virtual devices, including:
| Category   | Examples                        |
| ---------- | ------------------------------- |
| Routers    | Cisco IOS, IOS-XR, CSR1000v     |
| Switches   | Cisco IOL/IOU, virtual switches |
| Firewall   | FortiGate, Cisco FTD/FMC        |
| Linux      | Ubuntu, Debian, Alpine          |
| Network OS | Juniper, Arista, etc.           |
| Containers | Docker-based nodes              |
| Servers    | Linux servers and services      |
| Security   | IDS/IPS and security appliances |



### Hardware requirements:

> Intel CPU supporting Intel® VT-x /EPT virtualization, Operating System: Windows 7, 8, 10 or Linux Desktop, VMware Workstation 12.5 or later. 



_For a small personal lab, the official minimum is approximately:_
- CPU       : Intel i5/i7 (4 Logical processors), Enabled Intel virtualization in BIOS
- RAM       : 8 GB host / 6 GB+ PNETLab VM
- Disk      : 40 GB+
- Network   : LAN/WLAN / VMware NAT or Bridged network adapter
- Virtualization: Intel VT-x/EPT




### System Mode in PNETLab:

| Feature or Capability | Online Mode | Offline Mode |
| :--- | :--- | :--- |
| **Internet Requirement** | Requires internet to work | Does not need internet to work |
| **Registration & Login** | Requires registration | No registration needed (logs in by default with account: `admin/pnet`) |
| **Core Functions** | Supports full functions of PNETLab | Supports full functions of PNETLab |
| **Lab Store Access** | Download and use all Labs on the Store | Only download and use Open Labs (Labs with "Open" in the top) on the Store |
| **Sharing & Selling Labs** | You can share or sell labs to the Store | You cannot share or sell labs to the Store |
| **Account Limit** | Limit of 10 accounts (can be upgraded) | Limit of 10 accounts (can be upgraded, but requires internet) |



---
---


## Deploy PNETLab:


Download the `.ova` file and deploy on virtualization platforms such as VMWare. 


### Register and Login:

Access to your box by a browser (through IP address in your PNETLab box - in my case, the IP address is: `https://10.1.1.149`)

1. Select `Offline Mode`
    - Username: `admin` (GUI mode)
    - Password: `pnet`
    - Click `Login`


2. CLI Mode ssh to `10.1.1.149` (User: `root` and Password: `pnet`)
    - Type the root password: `pnet`
    - Repeat the root password: `pnet`
    - DNS domain name: Hit Enter 
    - Use DHCP/Static IP Address: `(*) dhcp`
    - NTP Server: Hit Enter 
    - Proxy Server: `(*) direct connection` 
    - Then, reboot the system 





---
---


### Ref:
- [PNET Docs](https://www.pnetlab.com/pages/documentation) 
- [Download PNET](https://www.pnetlab.com/pages/download) 

