# Network Traffic Within Microsoft Azure

![image](https://github.com/user-attachments/assets/1a55355f-47ff-4c8d-8694-624efc5844fe)

<h2>Description</h2>
In this lab project we will create two virtual machines (Vm) within Microsoft Azure, a network between both Vms, and monitor network traffic with software called Wireshark. 


<h2>Environments and Utilities Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop Connection 
- Wireshark
- Various Network Protocols (ICMP, SSH, DHCP, DNS)
- Command Line Tools

<h2>Operating Systems Used </h2>

- Windows 10
- Ubuntu 24.04

<h2>Project Steps</h2>

1. Create Resource Group
 <p> 
</p>

Create -> Select Resource Group -> Enter Name -> Select Region -> Review and Create
 <p> 
</p>

2. Create First Virtual Machine (Vm)\`
3. 
 <p> 
</p>

Create -> Put in Resource Group (previously created) -> Enter (Vm) Name "Windows-Vm" -> Select Region (same as before) -> Select Image: Windows 10 Pro Version 22H2 -> *Note* Size: Standard, 2vcpus, 8 gib memory -> Username/Password -> Check "License" -> Next to Disk -> Next to Networking -> Under Virtual Network Select "Create VNet" -> Enter VNet Name -> Ok -> Review and Create -> Create
 <p> 
</p>

3. Create Second Virtual Machine (Vm) 
 <p> 
</p>

Create -> Put in Resource Group (previously created) -> Enter (Vm) Name "Linux-Vm" -> Select Region (same as before) -> Select Image: Ubuntu Server 22.04 -> *Note* Size: Standard, 2vcpus, 8 gib memory -> Username/Password -> Next to Disk -> Next to Networking-> Select VNet (previously created) -> Review and Create -> Create
 <p> 
</p>

4. Login to Windows 10 Vm

Vm in Azure -> Click Windows 10 Vm -> Copy Public Ip Address -> Remote Desktop -> Enter Ip Address -> Enter Username/Password -> Connect/Enter

5. Install Wireshark 

In Windows 10 Vm -> Browse to Wireshark.org -> Click Download -> Select Windows 64bit Installer -> Open -> Double Click to Run -> Yes -> No -> Next Several Times -> Check "Install NoCap 1.79" -> Next Several Times -> Agree -> Install -> Next -> Finish

6. Run Wireshark

In Windows 10 Vm -> Search bar -> Type "Wireshark" -> click to Run -> Click Ethernet to hylight -> Click blue Shark fin Icon -> Observe traffic capture

7. Filter ICMP "ping" Traffic

In Windows 10 Vm -> In Wireshark -> In Search bar -> Type "ICMP" -> enter

Wireshark will now filter our all other network/port traffic execpt IMCP "ping" traffic

8. Ping Linux Vm from windows 10 Vm

Get Linux Vm Private Ip Address

Vm in Azure -> Click Linux Vm -> Copy orm Notem Private Ip Address

In Windows 10 Vm -> Rt Click Start -> Run Powershell -> Type ping, spacem, Linux Private Ip Address -> Enter

9. Observe results of ping

If done correctly you can see the IMCP traffic filtered in Wireshark. You will see a request and a reply in both Wireshark and Powershell.

Now we are going to configure the Linux Vm virtual firewall and observe it's effects on network traffic.

10. Start a continuous ping (windows 10 Vm to Linux Vm)

In Windows 10 Vm -> Powershell -> Type ping, space, Linux Private Ip Address, space, -t (will make non-stop ping) -> Enter

11. Observe results of continuous ping

12. Configure Linux Vm virtual firewall
