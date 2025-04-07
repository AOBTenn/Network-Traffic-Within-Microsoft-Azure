# Network Traffic Within Microsoft Azure

![image](https://github.com/user-attachments/assets/1b409f85-58eb-49c7-af18-890bba03dae9)

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

![image](https://github.com/user-attachments/assets/591345cf-2814-4826-b416-b0f0c9ed2394)
![image](https://github.com/user-attachments/assets/aaacfdfd-0cb8-4d7b-86dd-1fd8a7f5f45b)

2. Create First Virtual Machine (Vm)
 <p> 
</p>

In Azure -> Create -> Put in Resource Group (previously created) -> Enter (Vm) Name "Windows 10-Vm" -> Select Region (same as before) -> Select Image: Windows 10 Pro Version 22H2 -> *Note* Size: Standard, 2vcpus, 8 gib memory -> Username/Password -> Check "License" -> Next to Disk -> Next to Networking -> Under Virtual Network Select "Create VNet" -> Enter VNet Name -> Ok -> Review and Create -> Create
 <p> 
</p>

![image](https://github.com/user-attachments/assets/5da39162-3ff6-4714-83b6-198386b051c1)
![image](https://github.com/user-attachments/assets/6201f944-0ab0-41c2-87f1-b7f7b3a9c5c4)
![image](https://github.com/user-attachments/assets/36311c98-460d-4d88-9647-8b8e3d0754a6)
![image](https://github.com/user-attachments/assets/7031961d-d012-45bc-8e94-d08ddcae6e1a)
![image](https://github.com/user-attachments/assets/e367e8b4-fcb2-41fa-ac06-e24f27b15141)
![image](https://github.com/user-attachments/assets/430fdd6f-29cd-4d43-bec0-4a279770c8ac)

3. Create Second Virtual Machine (Vm) 
 <p> 
</p>

In Azure -> Create -> Put in Resource Group (previously created) -> Enter (Vm) Name "Linux-Vm" -> Select Region (same as before) -> Select Image: Ubuntu Server 22.04 -> *Note* Size: Standard, 2vcpus, 8 gib memory -> Username/Password -> Next to Disk -> Next to Networking-> Select VNet (previously created) -> Review and Create -> Create
 <p> 
</p>

![image](https://github.com/user-attachments/assets/4b2c4157-5d8b-4071-8e97-f6b93405d67c)
![image](https://github.com/user-attachments/assets/82671356-ad53-42fd-8498-dbf65e4cb48b)
![image](https://github.com/user-attachments/assets/81adecf9-3569-4947-9df8-99ae389171f7)
![image](https://github.com/user-attachments/assets/19025de5-2358-4179-8ed1-2e59ff1f11da)

4. Login to Windows 10 Vm

Vm in Azure -> Click Windows 10 Vm -> Copy Public Ip Address -> Remote Desktop -> Enter Ip Address -> Enter Username/Password -> Connect/Enter

![image](https://github.com/user-attachments/assets/858e4843-3a98-46a0-8aa6-a6a4fb5d75c6)
![image](https://github.com/user-attachments/assets/34fff7b9-5102-43a8-a3e2-f7f4360f5688)

5. Install Wireshark 

In Windows 10 Vm -> Browse to Wireshark.org -> Click Download -> Select Windows 64bit Installer -> Double Click to Run -> Yes -> No -> Next Several Times -> Check "Install NpCap 1.79" -> Next Several Times -> Agree -> Install -> Next -> Finish

![image](https://github.com/user-attachments/assets/4eada9c4-22bc-4cb1-ac34-22f416308b3d)
![image](https://github.com/user-attachments/assets/242ae70b-0fa1-490c-a9c0-548e9d9892df)
![image](https://github.com/user-attachments/assets/a107a723-0028-4892-bdc9-085900d29892)
![image](https://github.com/user-attachments/assets/4cb6254a-d8c7-4da3-8f10-0d63838cbdd0)
![image](https://github.com/user-attachments/assets/17167834-218b-4d04-8e73-796dfdbd05b7)
![image](https://github.com/user-attachments/assets/84415ce4-8a84-4e07-ad73-9d38e7dacc3b)
![image](https://github.com/user-attachments/assets/32b57392-45f1-4af5-864a-78a87a549e51)
![image](https://github.com/user-attachments/assets/0ef2e5f9-cef0-4533-9639-d6f9767eddcb)
![image](https://github.com/user-attachments/assets/67969353-a792-45c6-ad7c-a1a1cd8c077c)

6. Run Wireshark

In Windows 10 Vm -> Search bar -> Type "Wireshark" -> Click to Run -> Click Ethernet to highlight -> Click Blue Shark Fin Icon -> Observe Traffic Capture

![image](https://github.com/user-attachments/assets/9e135ca1-b3a7-488f-bc47-92a32b3d092f)
![image](https://github.com/user-attachments/assets/3a81e08a-b138-4bf3-8434-897b10f87aff)
![image](https://github.com/user-attachments/assets/d8350aed-6222-4f36-9c91-01b474692dfd)

7. Filter ICMP "ping" Traffic

In Windows 10 Vm -> In Wireshark -> In Search Bar -> Type "ICMP" -> Enter

![image](https://github.com/user-attachments/assets/e0e3780f-2ba5-4902-84c3-320d30c903da)

Wireshark will now filter our all other network/port traffic execpt IMCP "ping" traffic

8. Get Linux Vm Private Ip Address

Vm in Azure -> Click Linux Vm -> Copy or Note Private Ip Address

![image](https://github.com/user-attachments/assets/fd1ef944-f69a-410f-8906-48b8de0f99f2)

9. Ping Linux Vm from windows 10 Vm

In Windows 10 Vm -> Rt Click Start -> Run Powershell -> Type "ping, space, Linux Private Ip Address" -> Enter

![image](https://github.com/user-attachments/assets/c36c99c2-7509-4668-8af5-56ca7275a3c2)
![image](https://github.com/user-attachments/assets/c2cc7ea6-1e6a-44f5-a5a7-380731fdbdf0)

Observe Results of Ping

![image](https://github.com/user-attachments/assets/1ef12e45-a02a-4ec9-9cfe-2f1a2f4915f7)

If done correctly you can see the IMCP traffic filtered in Wireshark. You will see a request and a reply in both Wireshark and Powershell.

Now we are going to configure the Linux Vm virtual firewall and observe it's effects on network traffic.

11. Start a Continuous Ping (windows 10 Vm to Linux Vm)

In Windows 10 Vm -> Powershell -> Type "ping, space, Linux Private Ip Address, space, -t" (will make non-stop ping) -> Enter -> Restart Capture

![image](https://github.com/user-attachments/assets/564df52e-0bac-4898-a7d7-d1f10dbe7c8c)
![image](https://github.com/user-attachments/assets/7c631696-0d4b-4b97-b1c3-8dd0204179bd)

Observe results of Continuous Ping

![image](https://github.com/user-attachments/assets/63d4ddd9-36e2-466a-9a67-5482f26fc1ee)

12. Configure Linux Vm Virtual Firewall

Vm in Azure -> Click Linux Vm -> Networking -> Network Settings -> Network Security Group -> Settings -> Inbound Security Rules -> Add -> Source: Any -> Source Port: * -> Destination: Any -> Destination Port: * -> Protocal: ICMP v4 -> Action: Deny -> Priority: 290 (Enter number lower than current lowest rule to supersede prior rules) -> Add

![image](https://github.com/user-attachments/assets/e1e727f5-8f26-441d-9b46-b3ccf9cd6b81)
![image](https://github.com/user-attachments/assets/14be74eb-7820-406f-bd80-e69a73b6d746)
![image](https://github.com/user-attachments/assets/d807c796-8e31-4ade-8394-c0465ed7009a)
![image](https://github.com/user-attachments/assets/3653d393-839d-4158-8076-408bf917b046)

Observe Ping Traffic as firewall configuration takes effect

![image](https://github.com/user-attachments/assets/49e4cfc9-1909-4c20-a0b4-11301de3e37a)

In Powershell the request will time out while in Wireshark there will be a spream of "no response" after a "request in." This shows that the new rule took effect and the firewall is blocking the traffic to the Linux Vm.

14. Disable Linux Vm Firewall Configuration

Vm in Azure -> Click Linux Vm -> Networking -> Network settings -> Network Security Group -> Settings -> Inbound Security Rules -> Delete Rule 290 (or highest priorty)

![image](https://github.com/user-attachments/assets/644af004-7ef0-4071-9c82-06cf8885bc02)
![image](https://github.com/user-attachments/assets/4f9066a5-37e0-4813-aae3-6dc78ce01b3a)

Observe Ping Traffic as firewall configuration takes effect

In Powershell there will be a spream of "replys" while in Wireshark there will be a spream of "Request" and "reply." This shows that once the new rule deletion took effect the firewall stopped blocking the traffic to the Linux Vm.

![image](https://github.com/user-attachments/assets/6e7491ea-52ed-41c4-8152-986fdd2c25a0)

16. Stop Ping and Capture

In Powershell -> Press Contral C (on keyboard) -> Wireshark -> Red Stop Button

![image](https://github.com/user-attachments/assets/8dd66784-2975-419c-8200-8356be2e991d)

17. Filter SSH Traffic

In Windows 10 Vm -> In Wireshark -> In Search Bar -> Type SSH -> Enter -> Start New Capture

![image](https://github.com/user-attachments/assets/26f48f53-e241-45bf-8b83-55d227bbd110)
![image](https://github.com/user-attachments/assets/1687447a-3bfa-4576-8d6a-6a1006964b0d)

Wireshark will now filter our all other network/port traffic execpt SSH traffic

18. Run SSH in Powershell

In Powershell -> Type ssh space labuser@ "<" Linux Vm private Ip Address ">" -> Enter

![image](https://github.com/user-attachments/assets/5d80dd3f-1915-4f61-9708-1a063948015f)

Observe SSh Traffic

Continue connectin (In Powershell) -> Yes -> Enter -> Observe Capture is Wireshark -> Type password for Linux Vm (In Powershell) -> Observe more traffic -> Observe Powershell Id prompt change

In Powershell -> Type "Exit" -> Enter 

![image](https://github.com/user-attachments/assets/54a6b2c6-e7d5-47ac-8591-a91bac1c3e0f)

19. Open Powershell as Admin

In Windows 10 Vm -> Search Bar -> Type "Powershell" -> Click Run as Administrator

20. Create Mini Script

In Windows 10 Vm -> In Notepad -> Type "ipconfig space /release" and "ipconfig space /renew" -> Save to c:\programdata -> Name Script: "dhcp.bat"

21. Check Directory for Script/ Change Directory in Powershell

In Windows 10 Vm -> Open File Explorer -> Browse to c:\programdata -> Search for Script: "dhcp.bat"

22. Filter for DHCP Traffic

In Windows 10 Vm -> In Wireshark -> Clear Filter -> Type dhcp -> Enter -> Restart Capture

23. Run Script / Observe DHCP Capture

In Windows 10 Vm -> In Powershell -> Type "./dhcp.bat" -> Enter

24. Filter for DNS Traffic

In Windows 10 Vm -> In Wireshark -> Clear Filter -> Type dns -> Enter -> Restart Capture

In Powershell -> Type "nslookup space www.disney.com" -> Enter -> Observe Wireshark & Powershell

In Powershell -> Type "nslookup space www.pixar.com" -> Enter -> Observe Wireshark & Powershell

25. Filter RDP Traffic

In Windows 10 Vm -> In Wireshark -> Clear Filter -> Type "tcp.port == 3389" -> Enter -> Restart Capture -> Observe Wireshark Capture

The Capture should be very active and no apparent change because Remote Desktop is already running and sending data packes through port 3389.

