# LAB 1 — Azure Account Creation & Portal Navigation

## STEP 1: Create a Free Azure Account

1.1) Open your browser and go to www.portal.azure.com

1.2) Click `Start free` or `Create a free account`

1.3) Sign in with your Microsoft account (or create one if you don`t have one yet)

1.4) Fill in your profile information and phone verification

1.5) Enter a credit card for identity verification — you will NOT be charged automatically. The free account includes:
     - USD 200 in credits for the first 30 days
     - 12 months of free access to popular services
     - 55+ services that are always free

1.6) Once your account is created, you`ll land on the Azure Portal home page

OBS: This video gives some tips regarding the creation of Trial Account: https://www.youtube.com/watch?v=J48EaQkpUeo



---
## STEP 2: Explore the Azure Portal Interface

2.1) Look at the left sidebar menu — you'll see `All services`, `Favorites`, and `Recent`

2.2) Try the global search bar at the top: type `Virtual Machines`, then `Storage accounts` — notice how it searches across services, resources, and documentation

2.3) Click `All services` and browse the categories: `Compute, Networking, Storage, Databases, AI + Machine Learning`

2.4) Useful keyboard shortcuts to remember: G+/ opens search, G+N creates a new resource

2.5) Notice the difference between `Home` (overview with quick links) and `Dashboard` (customizable workspace)

---
## STEP 3: Try the Cloud Shell

3.1) Click the Cloud Shell icon (>_) in the top toolbar

3.2) Choose `Bash` or `PowerShell` — Bash uses Linux commands, PowerShell uses Windows-style cmdlets. Either works for Azure management

3.3) The first time, you`ll be asked to create a storage account to persist your files between sessions — click `Create storage`

3.4) Try these commands to verify your setup:
     
`az account show`
(displays your current subscription)
     
`az group list --output table`
(lists your resource groups in a table format)

3.5) You can upload files, use code editors (code .), and run scripts directly in the Cloud Shell

---
## STEP 4: Customize Your Dashboard

4.1) Go to `Dashboard` in the left menu, then click `Edit` at the top

4.2) Drag and drop widgets from the tile gallery: clock, resource metrics, quick links, Markdown panels

4.3) Resize and rearrange tiles to suit your workflow

4.4) Click `Save` when you`re happy with the layout

4.5) You can create multiple dashboards for different purposes (e.g., `Monitoring`, `Costs`, `Development`) using the `+ New dashboard` button

TIP: Bookmark portal.azure.com — you'll use it throughout this entire training program. The more familiar you are with the portal layout, the faster you`ll work in later sessions.
