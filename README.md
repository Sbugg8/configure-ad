<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://youtu.be/cwlVz4tD8pk?si=j_TErrOFuFU3tKub)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>


 - Setup up Domain Controller in Azure: Create a Resource Group, Create a Virtual Network and Subnet, Create the Domain Controller VM (Windows Server 2022) named “DC-1”.
- Setup Client in Azure: Create the Client VM (Windows 10) named “Client-1”
 
- Configure Active Directory Components
- Deploying Active Directory

<h2>Deployment and Configuration Steps</h2>

The first step in setting up Active Directory, is creating a virtual machine. Inside of that VM, a Resource Group is created. This is essential because it groups related resources (e.g., VMs, storage, and databases for an application) into a single unit and assists with better resource management and visibility. Once the VM is created and the Resource Group is deployed, a Domain Controller (DC-1) is created.

![image](https://github.com/user-attachments/assets/e00f8123-c6f1-4e69-8805-1ecba37ecf09)


A Domain Controller (DC) is a crucial component of Active Directory (AD) in a Windows-based network. It is responsible for authentication, security policies, and overall network management. Without a DC, users and devices would have difficulty accessing resources, enforcing security rules, and maintaining centralized management. In order to depoly the Domain Controllers inside of the VM, a Static Private IP address needs to be assigned.


</p>
<br />


![image](https://github.com/user-attachments/assets/f9562df7-e659-42ef-86b3-97b13070bc7e)


</p>
<p>
After VM is created, set Domain Controller’s NIC Private IP address to be static and log into the VM and disable the Windows Firewall to test the connectivity. Once this is done, create the Client VM. Make sure to attach it to the same region and virtual network as the DC. After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address.



![image](https://github.com/user-attachments/assets/3a23ca90-1a9d-459e-ba4f-25cd829920fa)
</p>
<p>
  Once Active Directory is configured so that Client and Domain Controller are able to communicate, the next step is installing Active Directory inside of the Domain Controller.

  ![image](https://github.com/user-attachments/assets/dd1dea01-7319-438d-a4d6-665d5c050b67)
![image](https://github.com/user-attachments/assets/fd8f4866-6c27-46f5-98b9-bfc4dfb9a213)


Active Directory (AD) is critical for businesses and organizations because it centralizes user and resource management, enhances security, and ensures efficient network operations. It allows IT to define access to specific files, systems, or applications. This is also categorized as "Group Policy".


![image](https://github.com/user-attachments/assets/c21c42ac-c467-48d0-a620-cafdd6482c0f)

The best way to customize Active Directory, is by giving permissions to specific users, using Powershell.


![image](https://github.com/user-attachments/assets/6fcae5da-bac5-432f-8e2f-c8d5cb473556)

PowerShell is like a supercharged remote control for your computer. It helps you automate tasks, manage systems, and control settings using commands and scripts.

![image](https://github.com/user-attachments/assets/9a433a20-02b9-4b4e-8246-5028bd83c9c1)
![image](https://github.com/user-attachments/assets/09567460-fcb7-4742-abfe-bbc92c0b24c6)









