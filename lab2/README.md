# LAB 2 — Creating a Resource Group and a Virtual Machine

## Region Assignment

To avoid hitting the **trial subscription quotas**, the class will distribute deployments across different regions.

Choose **ONE** of the following regions:

| Region |
|------|
| westeurope |
| northeurope |
| norwayeast |
| switzerlandnorth |
| canadacentral |

Important rules:

- Each student must **pick only one region**
- Coordinate with the other students
- **Maximum 2 students per region**

Example distribution for 10 students:

| Region | Students |
|------|------|
| westeurope | 2 |
| northeurope | 2 |
| norwayeast | 2 |
| switzerlandnorth | 2 |
| canadacentral | 2 |

---


## STEP 1: Create a Resource Group

1.1) In the portal, click `+ Create a resource` or search for `Resource groups`

<img width="946" height="353" alt="image" src="https://github.com/user-attachments/assets/5e86d5e5-800c-440e-9b99-052efb91e762" />


1.2) Click `+ Create` on the Resource Groups page

1.3) Select your subscription from the dropdown (this is the billing boundary for your resources)

1.4) Enter the name: rg-**<your_name>**-lab
     
**Naming convention tip:** use prefixes like 'rg' for Resource Groups, 'vm' for VMs, 'st' for Storage — this makes resources easy to identify at a glance.

OBS: on the field of `<your_name>`, each student must use a **unique key** to avoid overwriting another student's state. 

1.5) Select the region according to the table above.

**OBS:** in a normal scenario, choosing properly the region is important because it affects latency, pricing, and data residency compliance.

1.6) Go to the `Tags` tab and add:

Environment = `Training`

Owner = `<your_name>`

Tags help you organize resources and track costs across projects — get into the habit of tagging everything

1.7) Click `Review + Create`, then `Create`

---

## STEP 2: Create a Virtual Machine

2.1) Inside your new resource group, click `+ Create` > `Virtual Machine`. Use the following parameters when implementing your configuration.


| Parameter | Description | Value |
|---|---|---|
| **Project Details**   |
| Subscription | The Azure subscription used for billing and resource management. | Select the default trial Subscription |
| Resource Group | A logical container for managing related Azure resources together. | Resource group created previously |
| **Instance Details**  |
| VM Name | A unique identifier for the virtual machine within the resource group. | vm-**<your_name>**-lab |
| Region | The physical Azure datacenter location (e.g., East US, West Europe). | Same as your resource group |
| Availability Options | Redundancy settings like Availability Zones or Sets for high availability. | 1 |
| Security Type | Boot security level (Standard, Trusted Launch, or Confidential VM). | Standard |
| Image | The operating system and version (e.g., Windows Server 2022, Ubuntu 22.04). | Ubuntu 22.04 LTS |
| VM Size | Hardware specifications (vCPU, RAM, and throughput) like Standard_D2s_v3. | Standard_B2ls_v2 |
| **Administrator Account** |
| Authentication Type | The login method: SSH Public Key (recommended for Linux) or Password. | Password |
| Admin Username | The username for the local administrator account. | azureuser |
| SSH Key / Password | The credential used to authenticate the admin user. | Password123! |
| **Disks** |
| OS Disk Type | Storage performance level (Premium SSD, Standard SSD, or Standard HDD). | Standard SSD |
| Delete with VM | Option to automatically delete the disk when the VM is deleted. | Check |
| **Networking** |
| Virtual Network (VNet) | The isolated private network where the VM will reside. | Accept default values |
| Subnet | The specific IP range within the Virtual Network. | Accept default values |
| Public IP | An address that allows the VM to be reachable from the internet. | Accept default values |
| Network Security Group | A virtual firewall used to control inbound and outbound traffic. | Accept default values |
| Public Inbound Ports | Specific ports to open for remote access (e.g., 22 for SSH, 3389 for RDP). | 22 |
| **Management** |
| Auto-shutdown | A scheduled time to turn off the VM automatically to save costs. | Check |
| Backup | Enables Azure Backup to protect against data loss. | Check |
| Patching Options | Defines how the OS receives updates (Manual, Automatic, or Orchestrated). | Manual |
| **Tags** |
| Tags | Metadata name/value pairs used for organizing and billing. | Repeat the same tags as the Resource Group |


--- 
## STEP 3: Deploy the VM

3.1) Go to `Review + Create` — Wait for the conformity check. Review the summary and the estimated cost per hour/month at the bottom.

3.2) Click `Create` and wait for the deployment (typically 2-5 minutes)

3.3) Once deployed, click `Go to resource` to see the VM overview: public IP, status, OS, size, and location, etc.

--- 
## STEP 4: Connect to Your VM

4.1) For Linux: open Cloud Shell and run:  ssh your-username@public-IP-address

4.2) For Windows: click `Connect` > `RDP`, download the RDP file, and open it with your credentials

4.3) Once connected, try these commands to confirm everything works:
     hostname       (shows the VM name)
     ip addr        (shows network configuration)
     free -h        (shows available memory)
     lsb_release -a (shows the Linux distribution details)

4.4) Back in the portal, check the Metrics section to see real-time CPU, network, and disk activity

--- 
## STEP 5: Clean Up (IMPORTANT!)

5.1) Navigate to your resource group

5.2) Click `Delete resource group`

5.3) Type the resource group name to confirm, then delete — **this removes ALL resources inside it**

5.4) Always clean up after labs to avoid unexpected charges. This is a best practice for any test/dev environment

NOTE: If you want to keep practicing, you can stop (deallocate) the VM instead of deleting it. A stopped VM does not incur compute charges, but storage charges still apply.
