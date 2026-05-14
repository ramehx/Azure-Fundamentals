# LAB 1 — Azure Account Creation & Portal Navigation

## STEP 1: Create a Free Azure Account

1.1) Open your browser and go to www.portal.azure.com

1.2) Click `Start free` or `Create a free account`

<img width="80%" alt="image" src="https://github.com/user-attachments/assets/25e5093e-90ee-402b-8ab5-6fb4a1ab2453" />

<img width="80%" alt="image" src="https://github.com/user-attachments/assets/fc2e6be0-5fe5-4849-b376-1b1ab8674a78" />

1.3) Sign in with your Microsoft account (or create one if you don`t have one yet)

<img width="1840" height="549" alt="image" src="https://github.com/user-attachments/assets/109e5800-3e95-4c95-8f51-a868d90757fa" />

1.4) Fill in your profile information and phone verification

<img width="1531" height="786" alt="image" src="https://github.com/user-attachments/assets/8ef4ef64-34c8-4e98-b6e0-8671f6cffd48" />

1.5) Enter a credit card for identity verification — you will NOT be charged automatically. The free account includes:
     - USD 200 in credits for the first 30 days
     - 12 months of free access to popular services
     - 55+ services that are always free

<img width="60%" alt="image" src="https://github.com/user-attachments/assets/d89cbf6a-8f92-45c3-a104-c416052336fc" />

1.6) Once your account is created, you`ll land on the Azure Portal home page

OBS: This video gives some extra tips regarding the creation of Trial Account: https://www.youtube.com/watch?v=J48EaQkpUeo



---
## STEP 2: Explore the Azure Portal Interface

2.1) Look at the left sidebar menu — you'll see `All services`, `Favorites`, and `Recent`

<img width="227" height="538" alt="image" src="https://github.com/user-attachments/assets/a356b6f8-5c88-47d4-89d7-1de6a1868d95" />


2.2) Try the global search bar at the top: type `Virtual Machines`, then `Storage accounts` — notice how it searches across services, resources, and documentation

<img width="60%" alt="image" src="https://github.com/user-attachments/assets/b8b2ec71-ffcc-4398-b67e-cb805b11f938" />

2.3) Click `All services` and browse the categories: `Compute, Networking, Storage, Databases, AI + Machine Learning`


<img width="80%" alt="image" src="https://github.com/user-attachments/assets/23ab855a-87ba-49c6-aec9-aa3be50bf89a" />


2.4) Notice the difference between `Home` (overview with quick links) and `Dashboard` (customizable workspace)

<img width="1067" height="812" alt="image" src="https://github.com/user-attachments/assets/6762323c-1f91-474c-a507-7af7a0a09821" />

---
## STEP 3: Try the Cloud Shell

3.1) Click the Cloud Shell icon (>_) in the top toolbar

<img width="1005" height="167" alt="image" src="https://github.com/user-attachments/assets/ed3eb65e-b812-46da-9243-40d35396855a" />

3.2) Choose `Bash` or `PowerShell` — Bash uses Linux commands, PowerShell uses Windows-style cmdlets. Either works for Azure management

3.3) The first time, you'll be asked to create a storage account to persist your files between sessions — click `Create storage`

<img width="60%" alt="image" src="https://github.com/user-attachments/assets/1bfe10a2-54f4-42e9-9cb0-433fe0e99602" />

<img width="60%" alt="image" src="https://github.com/user-attachments/assets/2e8efb9a-e28d-4ab5-a278-aa2bdfa481a1" />

<img width="1183" height="296" alt="image" src="https://github.com/user-attachments/assets/085f5b71-ac96-4120-bba6-2a68430a4329" />


3.4) Try these commands to verify your setup:
     
`az account show`
(displays your current subscription)
     
`az group list --output table`
(lists your resource groups in a table format)

3.5) You can upload files, use code editors (code .), and run scripts directly in the Cloud Shell

<img width="912" height="183" alt="image" src="https://github.com/user-attachments/assets/aa09ab66-33fc-44b7-a71e-7d88a05b6642" />

---
## STEP 4: Customize Your Dashboard

4.1) Go to `Dashboard` in the left menu, then click `Edit` at the top

4.2) Drag and drop widgets from the tile gallery: clock, resource metrics, quick links, Markdown panels

<img width="1369" height="808" alt="image" src="https://github.com/user-attachments/assets/045c7c81-ee17-40e1-9ef9-401abdf42334" />


4.3) Resize and rearrange tiles to suit your workflow

4.4) Click `Save` when you`re happy with the layout

4.5) You can create multiple dashboards for different purposes (e.g., `Monitoring`, `Costs`, `Development`) using the `+ New dashboard` button

TIP: Bookmark https://portal.azure.com — you'll use it throughout this entire training program. The more familiar you are with the portal layout, the faster you`ll work in later sessions.
