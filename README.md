<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. 

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- [Create our Resources](#step1)
- [Observe ICMP Traffic](#step2)
- [Observe SSH Traffic](#step3)
- [Observe DHCP Traffic](#step4)
- [Observe DNS Traffic](#step5)
- [Observe RDP Traffic](#step6)



<h2 id="step1">1. Create our Resources</h2>



<p>
<img width="1470" alt="Screenshot 2024-07-25 at 10 04 26 PM" src="https://github.com/user-attachments/assets/2bbb34d6-aa59-4072-a4e2-5233c7fcab0b">
</p>
<h3>

*Create a Resource Group* 
</h3>
<p>
  
If you haven't already, set up your azure account to get some free credits. Then go to [portal.azure.com/](https://portal.azure.com/) and go to the search bar and search "resource group" and click on the cube with the brackets. Click create and name the resource group "network_lab" and finish making the resource group.
</p>
<br />

<p>
<img width="1470" alt="Screenshot 2024-07-25 at 10 13 23 PM" src="https://github.com/user-attachments/assets/31ff57d1-a47e-43e3-a25c-fc4bb5ffefe1">
</p>
<h3>

*Create a Windows 10 Virtual Machine*
</h3>
<p>
Go to the same search bar and search "virtual machine" and click on the computer. After name the VM ``VM1" with the username "labuser" and a password you can remember. After you're finished it should look something like the picture and click create to start the deployment process.
</p>
<br />

<p>
<img width="1470" alt="Screenshot 2024-07-25 at 10 21 52 PM" src="https://github.com/user-attachments/assets/1ba8a8e9-49a1-4376-b603-57b30dc9b662">
</p>
<h3>

*Create a Linux Virtual Machine*
</h3>
<p>
In the same way create a linux virtual machine and call it "VM2" with the same username and password (this is not best practice but for the lab it's fine). <ins>Make sure to select the same VNET under the network tab</ins> it won't work if you don't.
</p>
<br />



<h2 id="step2">2. Observe ICMP Traffic</h2>



<p>
<img width="711" alt="Screenshot 2024-07-26 at 2 15 47 PM" src="https://github.com/user-attachments/assets/4d7f80f7-daf7-4a5b-8632-e3c64d54844f">
</p>
<h3>

*Use Remote Desktop to connect to your Windows 10 Virtual Machine*
</h3>
<p>
Find the public IP address found in Azure portal and use it to log in using "Microsoft Remote Desktop" with mac or "Remote Desktop" in windows. Use the user you created earlier.
</p>
<br />

<p>
<img width="1470" alt="Screenshot 2024-07-26 at 2 28 03 PM" src="https://github.com/user-attachments/assets/48a08a07-be73-4101-a640-c9a38ac24413">
</p>
<h3>

*Install Wireshark*
</h3>
<p>
In the web browser, search for wireshark and click "Download" and download "Windows x64".
</p>
<br />

<p>
<img width="1470" alt="Screenshot 2024-07-26 at 2 39 07 PM" src="https://github.com/user-attachments/assets/e45840d4-1f58-40ee-a92c-512b36db430c">
</p>
<h3>

*Open Wireshark and filter for ICMP traffic*
</h3>
<p>
Open the installer file and click through to install wireshark. After installing, open wireshark and click the fin to start analyzing. Then go to the search bar and type "icmp" to filter for that kind of traffic.
</p>
<br />

<p>
<img width="1470" alt="Screenshot 2024-07-26 at 2 45 00 PM" src="https://github.com/user-attachments/assets/9982c2cd-605e-4b56-a00e-f790e89238bd">
<img width="1470" alt="Screenshot 2024-07-26 at 2 45 28 PM" src="https://github.com/user-attachments/assets/9c436052-8a1a-48cc-a993-64dd65a897c4">
</p>
<h3>

*Ping Ubuntu VM from Windows VM*
</h3>
<p>

From the Azure portal, find the private IP, take note of this IP. Press the windows key + R to open the run command (Command+R in mac) and type "cmd" to open the command line. When the window opens, type ``` ping -t 10.0.0.5 ``` (My ip in the azure portal was 10.0.0.5) and hit enter. When that happens you should see the command line fill up and in wireshark stuff is going to start filling up.
</p>
<br />

<p>
<img width="1470" alt="Screenshot 2024-07-26 at 2 56 03 PM" src="https://github.com/user-attachments/assets/7614e56a-a3ab-4a7c-b06f-ab2f0f5cb2a3">
</p>
<h3>

*Ping a Public Website*
</h3>
<p>

When you're done pinging the linux computer, "press control+c" to end the ping. Then in the command line type ``` ping -t google.com ``` to start pinging google and look at the traffic in wireshark.
</p>
<br />



<h2 id="step3">3. Observe SSH Traffic</h2>



<p>
<img width="1470" alt="Screenshot 2024-07-26 at 3 00 53 PM" src="https://github.com/user-attachments/assets/033a7e68-460d-4557-86a9-4cd0e6ae2304">
</p>
<h3>

*Filter for SSH traffic*
</h3>
<p>
In the search bar in wireshark, type ssh to filter for ssh traffic.
</p>
<br />

<p>
<img width="1470" alt="Screenshot 2024-07-26 at 3 06 00 PM" src="https://github.com/user-attachments/assets/19eaadab-945b-4dbc-80c6-e4a4060e7c46">
<img width="1470" alt="Screenshot 2024-07-26 at 3 11 59 PM" src="https://github.com/user-attachments/assets/454c5537-1df8-4ed6-bf0f-b79290349510">
</p>
<h3>

*SSH into your Ubuntu VM*
</h3>
<p>
  
In the terminal type ``` ssh 10.0.0.5 ```, when prompted type the password you set up when creating the VM and you should see wireshark populate with the ssh traffic. 
</p>
<br />



<h2 id="step4">4. Observe DHCP Traffic</h2>



<p>
<img width="1470" alt="Screenshot 2024-07-26 at 3 13 53 PM" src="https://github.com/user-attachments/assets/4716cf31-0749-475a-94f0-c347fe1ab7e5">
</p>
<h3>

*Filter for DHCP traffic*
</h3>
<p>
In the search bar in wireshark, type dhcp to filter for dhcp traffic.
</p>
<br />

<p>
<img width="1470" alt="Screenshot 2024-07-26 at 3 16 10 PM" src="https://github.com/user-attachments/assets/2656cf80-b2cb-498f-a5d6-cab6e1919ac7">
</p>
<h3>

*Issue your VM a new IP address from the command line*
</h3>
<p>
  
In the command line type ``` ipconfig /renew ``` and press enter. You should see wireshark populate with traffic after.
</p>
<br />



<h2 id="step5">5. Observe DNS Traffic</h2>



<p>
<img width="1470" alt="Screenshot 2024-07-26 at 3 19 14 PM" src="https://github.com/user-attachments/assets/9767cb61-b326-4e38-b27c-abd8a54f0528">
</p>
<h3>

*Filter for DNS traffic*
</h3>
<p>
In the search bar in wireshark, type dns to filter for dns traffic. If there's traffic, you can click the green fin to reset the analysis.
</p>
<br />

<p>
<img width="1470" alt="Screenshot 2024-07-26 at 3 22 24 PM" src="https://github.com/user-attachments/assets/e0375f14-cfbd-465e-b4eb-fe3010466d38">
</p>
<h3>

*Use nslookup*
</h3>
<p>
  
In the command line, type ``` nslookup google.com ``` or ```nslookup disney.com``` to simulate DNS traffic and see wireshark fill up.
</p>
<br />



<h2 id="step6">6. Observe RDP Traffic</h2>



<p>
<img width="1470" alt="Screenshot 2024-07-26 at 3 30 09 PM" src="https://github.com/user-attachments/assets/258f64cb-2517-42ab-bbe9-ec4c1c29bb20">
</p>
<h3>

*Filter for RDP traffic*
</h3>
<p>
  
In the search bar type ``` tcp.port == 3389 ``` (this is the same as typing rdp in the search bar).
</p>
<br />

<h3>

*Observe Traffic*
</h3>
<p>
Notice that the traffic is non-stop? This is because while seeing the screen, you're transmitting information from the VM to your computer.
</p>
<br />



<h2>Optional step: Delete Resources</h2>



<p>
<img width="1470" alt="Screenshot 2024-07-26 at 3 36 48 PM" src="https://github.com/user-attachments/assets/f2b3df4c-de96-4ce2-8d36-4b71c1259190">
<img width="1470" alt="Screenshot 2024-07-26 at 3 37 05 PM" src="https://github.com/user-attachments/assets/8b83ac40-2d12-4d8d-9c63-32a31e4b04af">
</p>
<p>
  This is optional but for the lab its best to delete the resources to save money for the free credits.
</p>

<h3>This concludes the making of the network protocols lab for Azure, to look at the other projects i've done you can look at my [home page](https://github.com/rcruz04/rcruz04).
</h3>

end








