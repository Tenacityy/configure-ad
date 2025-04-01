<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup Virtual Machines Through Azure
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
1) Let's create a Resource Group within Azure! Navigate to "Resource Groups" by typing it in the search bar.
<p>
<img src="https://i.imgur.com/x6ljaCc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Tlllxlr.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<p>
<p>
<img src="https://i.imgur.com/MFe4ReH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<p>
2) Let's create a Virtual Network! Navigate to "Virtual Networks" by typing it in the search bar.
<img src="https://i.imgur.com/LiYfkNX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
Make sure your Region is the same as your Resource Group.
<p>
<img src="https://i.imgur.com/QxXiKjU.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/WF2GocN.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/xD4zHSo.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<p>
3) Next we will Create a Virtual Machine For our Domain Controller! Navigate to "Virtual Machines" by typing it in the search bar.
<p>
<img src="https://i.imgur.com/YPswrBy.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<p>
Make sure you select "Windows Server 2022 Datacenter" and also make sure the region is the same.
<p>
<img src="https://i.imgur.com/2dz2Q78.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<p>
Make sure you check these 2 lisencing boxes!
<p>
<img src="https://i.imgur.com/4MBlWTv.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/RNZR0hv.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<p>
Make sure you select the correct Virtual Network!
<p></p>
<img src="https://i.imgur.com/lNiOS0j.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/2wkqECP.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/s2KTy9d.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />
4) Let's Create another Virtual Machine name Client-1! Navigate to "Virtual Machines" by typing it in the search bar.
<p>
<img src="https://i.imgur.com/UMEPdws.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<p>
Make sure to select "Windows 10 Pro" and select the same region as the "dc-1" Virtual Machine
<p>
<img src="https://i.imgur.com/HtiLQIV.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<p>
Make sure to check this box!
<p>
<img src="https://i.imgur.com/USDDXxp.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/mSpqsuN.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/r36Kf2P.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/6hEM3np.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/twBg4n1.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />
5) Next let's set the Domain Controller’s NIC Private IP address to be static. Let's Navigate to "Virtual Machine" on Azure.
<p></p>
<img src="https://i.imgur.com/hAxxvSI.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/SMUDyFv.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/mlxFywx.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/jYdhkxb.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/8ME7SEk.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />
6) For the sake of this tutorial let's disable the Windows Firewall inside of "dc-1" Virtual Machine for Testing Connectivity.
<p></p>
<img src="https://i.imgur.com/6gpuu0v.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ajAudPM.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />
7) Next we will set Client-1’s DNS settings to DC-1’s Private IP address. Navigate to "dc-1" Virtual Machine in Azure.
<p></p>
<p>
Copy the Private IP Address from "dc-1" to your clipboard.
<p>
<img src="https://i.imgur.com/S9hTfVo.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
Next we will Navigate to "client-1" Virtual Machine
<p>
<img src="https://i.imgur.com/oJBeKal.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/h1k2kQi.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Oaoa4Fp.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/FXKgZaI.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />
8) Next let's login to "Client-1" Virtual Machine and attempt to ping "dc-1"
<p></p>
<p>
Open up Windows Powershell and type "ping [INSERT PRIVATE IP]"
<p>
<img src="https://i.imgur.com/hAxxvSI.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/SMUDyFv.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/mlxFywx.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/jYdhkxb.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/8ME7SEk.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

