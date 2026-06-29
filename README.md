# configure-ad
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This project demonstrates the deployment and configuration of a traditional on-premises Active Directory environment hosted entirely within Microsoft Azure Virtual Machines.

The lab includes the creation of a Domain Controller, DNS configuration, organizational units (OUs), user account management, group policy implementation, and domain joining client machines to simulate a real-world enterprise environment.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://youtu.be/wuIE4p4io7Q?si=7LJP3ez9iq8jREe3)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell
- Azure Virtual Machines
- Azure Virtual Network
- Azure Network Security Groups
- Remote Desktop Protocol (RDP)
- Windows Server 2022
- Windows 10 Pro
- Active Directory Domain Services (AD DS)
- DNS
- Group Policy Management
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)


- ## High-Level Deployment and Configuration Steps

1. Create Azure Resource Group
2. Deploy Virtual Network and Subnet
3. Create Domain Controller Virtual Machine
4. Install Active Directory Domain Services
5. Promote Server to Domain Controller
6. Configure DNS
7. Create Organizational Units
8. Create Users and Security Groups
9. Deploy Client Virtual Machine
10. Join Client Machine to Domain
11. Verify Authentication and DNS Resolution
12. Test User Logins


## Skills Demonstrated

- Active Directory Administration
- Azure Virtual Machine Deployment
- DNS Configuration
- Windows Server Management
- User Account Administration
- Organizational Unit Management
- Group Policy Fundamentals
- PowerShell Automation
- Remote Desktop Troubleshooting
- Identity and Access Management




<h2>Deployment and Configuration Steps</h2>

## Step 1: Create Azure Resource Group

Create a dedicated Resource Group to contain all lab resources.

## Actions

- Log into Azure Portal
- Navigate to Resource Groups
- Click Create
- Name the Resource Group


<p>
<img width="1909" height="912" alt="Active directory Lab 1" src="https://github.com/user-attachments/assets/9f3799d4-92c8-46de-8825-336f0b69511b" />

</p>
<p>



  
## Step 2: Create Virtual Network

After creating the resource group, create the virtual network and add it to the resource group as well

## Configuration
VNET Name: Active-Directory-VNET

Address Space:
10.0.0.0/16

Subnet:
10.0.1.0/24
</p>
<br />

<p>
<img width="1908" height="906" alt="active directory lab 2(VNet)" src="https://github.com/user-attachments/assets/9f28ce40-b965-4851-ad29-c3e18c9dac72" />

</p>
<p>
  
## Step 3: Deploy Domain Controller VM

VM Name: dc-1

OS/Image:
Windows Server 2022

<br />

<p>
<img width="1911" height="912" alt="active directory lab3(VMachines)" src="https://github.com/user-attachments/assets/599ea761-77ef-463f-a631-496b2d35fc5f" />


After VM is created, set Domain Controller’s NIC Private IP address to be static

<img width="1917" height="960" alt="Screenshot 2026-06-23 231744" src="https://github.com/user-attachments/assets/451157f8-3736-4ae6-acaf-2f833aeb241d" />



<img width="1913" height="911" alt="Screenshot 2026-06-23 231931" src="https://github.com/user-attachments/assets/ccd28541-3d08-4dcf-964a-b3713b16aa70" />



</p>
<p>
  



</p>
<br />

## Disabling windows firewall in dc-1

In this image, I right-clicked on the Windows logo, clicked "RUN" and typed in "wf.msc"
<img width="3360" height="1950" alt="Screenshot 2026-06-23 at 11 38 47 PM" src="https://github.com/user-attachments/assets/4c519432-f3e5-49e1-8fa5-aced3c03c92b" />





<img width="3360" height="1950" alt="Screenshot 2026-06-23 at 11 40 24 PM" src="https://github.com/user-attachments/assets/90a47d98-ede7-4844-aca0-a779870e0d45" />





## set Client-1’s DNS settings to DC-1’s Private IP address

After Client-1 VM is created, set Client-1’s DNS settings to DC-1’s Private IP address

<img width="1908" height="911" alt="Screenshot 2026-06-23 234450" src="https://github.com/user-attachments/assets/87aacf72-5440-4c9f-b07f-273e5e96d18f" />



## Step 4: Install Active Directory Domain Services

Installing Active Directory
<img width="3360" height="1950" alt="Screenshot 2026-06-28 at 9 13 56 PM" src="https://github.com/user-attachments/assets/b771def2-788d-4893-81b2-cbee1955bd51" />



## Step 5: Promote Server to Domain Controller

<img width="3360" height="1950" alt="Screenshot 2026-06-28 at 9 24 15 PM" src="https://github.com/user-attachments/assets/2af3f98c-f606-41bc-b18e-785340343736" />

## Log back into dc-1 as the domain controller

<img width="3360" height="1950" alt="Screenshot 2026-06-28 at 9 49 30 PM" src="https://github.com/user-attachments/assets/1d3d9e14-20b9-4092-aa24-ce1c9e2a01c5" />


## Step 6: Create Organizational Units

<img width="3360" height="1950" alt="Screenshot 2026-06-28 at 10 24 58 PM" src="https://github.com/user-attachments/assets/78bc38cb-3868-454d-9693-e689af41f5e1" />


<img width="3360" height="1950" alt="Screenshot 2026-06-28 at 10 27 11 PM" src="https://github.com/user-attachments/assets/c6b0c569-0a38-4891-b1da-d11003f72d8f" />




## Step 7: Create Users and Security Groups


<img width="3360" height="1950" alt="Screenshot 2026-06-28 at 10 34 11 PM" src="https://github.com/user-attachments/assets/e23b0aee-7c3d-4976-bd16-3aa92bf0a9ee" />



<img width="3360" height="1950" alt="Screenshot 2026-06-28 at 10 40 13 PM" src="https://github.com/user-attachments/assets/0ca4bf08-e6d7-400f-9745-31f493be6960" />



## Step 8: Deploy Client Virtual Machine

Log back into dc-1 as jane_admin




## Step 9: Join Client Machine to Domain


<img width="3360" height="1950" alt="Screenshot 2026-06-28 at 11 32 47 PM" src="https://github.com/user-attachments/assets/dd0862ad-5c2b-4d26-a405-98a4154cf5c3" />




