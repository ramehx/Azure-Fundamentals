# LAB 3 — Creating a Storage Account and Managing Blob Storage


## STEP 1: Create a Storage Account

1.1) In the portal, search for `Storage accounts` and click `+ Create`

1.2) Select the Subscription and resource group.  (create a new one if needed:  rg-**<your_name>**-lab)

1.3) **Storage account name:** pick something unique like stdemoyourname (rules: 3-24 characters, lowercase letters and numbers only, must be globally unique)

1.4) **Region:** Select the region according to the table above.

1.5) **Performance tier:**

- Standard — backed by HDDs, cost-effective for most workloads

- Premium — backed by SSDs, for low-latency/high-throughput scenarios

Select `Standard` for this exercise

1.6) **Redundancy** — this is where you choose how many copies of your data Azure keeps:

- LRS: 3 copies in one data center (cheapest, protects against hardware failure)

- ZRS: 3 copies across 3 availability zones (protects against data center failure)

- GRS: 6 copies across 2 regions (protects against regional disaster)

- GZRS: ZRS in primary region + LRS in secondary (most resilient)

Select `LRS` for this demo to keep costs low

1.7) Click `Review + Create`, then `Create`

---

## STEP 2: Create a Blob Container

2.1) Open your new storage account

2.2) In the left menu under `Data storage`, click `Containers`

2.3) Click `+ Container` to create a new one

2.4) Name: documents-demo

2.5) Access level — understand the three options:

- Private (no anonymous access) — default and most secure. You need authentication to read blobs

- Blob (anonymous read for blobs only) — anyone with the URL can read individual files

- Container (anonymous read for entire container) — anyone can list and read all files

Select `Private` for this exercise

2.6) Click `Create`

---

## STEP 3: Upload Files

3.1) Open the container you just created

3.2) Click `Upload`

3.3) Select a few sample files from your computer (images, PDFs, text files — anything works)

3.4) Expand `Advanced` to see options like blob type (Block, Page, Append) and access tier (Hot, Cool, Cold, Archive)

3.5) Click `Upload` and verify your files appear in the list

---

## STEP 4: Manage Your Blobs

4.1) Click on any blob to see its properties: URL, size, content type, access tier, and last modified date

4.2) Try changing the access tier: click `Change tier` and switch from Hot to Cool

Note: Cool tier has a minimum retention of 30 days — if you delete or move data before that, you`ll pay an early deletion fee

4.3) Generate a SAS (Shared Access Signature) URL:

- Click `Generate SAS` on the blob

- Set permissions (Read is enough for sharing)

- Set an expiry date/time

- Click `Generate SAS token and URL`

4.4) Copy the `Blob SAS URL` and paste it in a private/incognito browser window — you should be able to view the file without logging in. This is how you share private blobs securely with a time-limited link

4.5) Practice downloading and deleting blobs using the toolbar buttons

---

## STEP 5: Review Storage Metrics

5.1) Go back to your storage account overview page

5.2) Check the `Overview` section: used capacity, account kind, redundancy, performance tier

5.3) Click `Metrics` in the left menu: explore charts for transactions, latency, ingress/egress, and capacity

5.4) Try `Diagnose and solve problems` if you want to see troubleshooting tools

---

## STEP 6: Clean Up

6.1) Delete the resource group ( rg-**<your_name>**-lab) to remove all resources at once

6.2) Verify in Cost Management that no charges are pending

TIP: You can also manage storage from the command line. Try: az storage account create, az storage container create, and az storage blob upload in the Cloud Shell.
