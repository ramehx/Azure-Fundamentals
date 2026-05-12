# LAB 2 — Creating a Resource Group and a Virtual Machine

## STEP 1: Create a Resource Group

1.1) In the portal, click '+ Create a resource' or search for 'Resource groups'

1.2) Click '+ Create' on the Resource Groups page

1.3) Select your subscription from the dropdown (this is the billing boundary for your resources)

1.4) Enter the name: rg-training-az900
     Naming convention tip: use prefixes like rg- for Resource Groups, vm- for VMs, st for Storage — this makes resources easy to identify at a glance

1.5) Select the region: Brazil South (or the region closest to you)
     Why the region matters: it affects latency, pricing, and data residency compliance

1.6) Go to the Tags tab and add:
     Environment = Training
     Owner = your-name
     Tags help you organize resources and track costs across projects — get into the habit of tagging everything

1.7) Click 'Review + Create', then 'Create'

---

## STEP 2: Create a Virtual Machine

2.1) Inside your new resource group, click '+ Create' > 'Virtual Machine'

2.2) Basics tab:
     - Name: vm-demo-az900
     - Region: same as your resource group
     - Availability: No infrastructure redundancy required (fine for a demo)

2.3) Image: browse the options — Windows Server 2022, Ubuntu 
22.04 LTS, Red Hat, etc.
     Select Ubuntu 
22.04 LTS for this exercise (it's lightweight and free)

2.4) Size: click 'See all sizes' and look at the families:
     - B-series (burstable) — cheapest, great for demos. Pick B1s (~USD 
0.01/hour)
     - D-series (general purpose), F-series (compute optimized), E-series (memory optimized)

2.5) Authentication: choose 'Password' for simplicity. In production, SSH keys are more secure

2.6) Inbound ports: check SSH (22) for Linux. For a Windows VM, you'd check RDP (3389)

--- 
## STEP 3: Review Disk and Network Settings

3.1) Disks tab: notice the disk type options and their cost differences:
     - Premium SSD — high performance (for production workloads)
     - Standard SSD — balanced price/performance
     - Standard HDD — lowest cost (fine for our demo)

3.2) Networking tab: a Virtual Network (VNet) is created automatically. Note the public IP and the Network Security Group (NSG) that controls traffic

3.3) Management tab: check 'Enable auto-shutdown' and set a time — this prevents accidental charges if you forget to stop the VM

--- 
## STEP 4: Deploy the VM

4.1) Go to 'Review + Create' — check the summary and the estimated cost per hour/month at the bottom

4.2) Click 'Create' and wait for the deployment (typically 2-5 minutes)

4.3) Once deployed, click 'Go to resource' to see the VM overview: public IP, status, OS, size, and location

--- 
## STEP 5: Connect to Your VM

5.1) For Linux: open Cloud Shell and run:  ssh your-username@public-IP-address

5.2) For Windows: click 'Connect' > 'RDP', download the RDP file, and open it with your credentials

5.3) Once connected, try these commands to confirm everything works:
     hostname       (shows the VM name)
     ip addr        (shows network configuration)
     free -h        (shows available memory)
     lsb_release -a (shows the Linux distribution details)

5.4) Back in the portal, check the Metrics section to see real-time CPU, network, and disk activity

--- 
## STEP 6: Clean Up (IMPORTANT!)

6.1) Navigate to your resource group: rg-training-az900

6.2) Click 'Delete resource group'

6.3) Type the resource group name to confirm, then delete — this removes ALL resources inside it

6.4) Always clean up after labs to avoid unexpected charges. This is a best practice for any test/dev environment

NOTE: If you want to keep practicing, you can stop (deallocate) the VM instead of deleting it. A stopped VM does not incur compute charges, but storage charges still apply.
