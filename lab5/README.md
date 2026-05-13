# LAB 5 — Cost Management and Resource Monitoring

## STEP 1: Explore Cost Analysis

1.1) In the portal, search for `Cost Management + Billing`

1.2) Click `Cost analysis` in the left menu

1.3) Explore the different visualization modes:

- **Bar chart** — costs over time (daily, weekly, monthly)

- **Table** — detailed breakdown by service

- **Donut chart** — percentage distribution by category

1.4) Apply filters to narrow your view: by resource group, service name, tag, or time period

1.5) Group your costs by different dimensions: try grouping by `Service name`, then by `Location`, then by `Tag`

1.6) Click `Download` to export a cost report as CSV or Excel for further analysis

---

## STEP 2: Set Up a Budget with Alerts

2.1) Click `Budgets` in the left menu

2.2) Click `+ Add` to create a new budget

2.3) Configure the budget:

- **Name:** Budget-Training

- **Reset period:** Monthly

- **Amount** set an amount you`re comfortable with (e.g., USD 10 for a training account)

2.4) Set up alert thresholds at multiple levels:

- At 50%: email notification (early warning)

- At 75%: email notification (attention needed)

- At 90%: email notification + optional automation (e.g., auto-shutdown VMs)

- At 100%: urgent email notification

2.5) Add your email address as a recipient for the alerts

2.6) Optionally, link an Action Group to trigger automated responses when a threshold is reached (like stopping non-critical resources)

---

## STEP 3: Explore Azure Monitor

3.1) Search for `Monitor` in the portal

3.2) Look at the overview page — it shows Application Insights, Alerts, Metrics, Logs, and more

3.3) Click `Metrics` and select a resource you`ve created (a VM or storage account)

3.4) Build a metrics chart: pick a metric like `Percentage CPU` for a VM, or `Transactions` for a storage account

3.5) Adjust the time range (last 1 hour, 6 hours, 24 hours) and granularity

3.6) Click `Pin to dashboard` to add this chart to your custom dashboard for ongoing monitoring

---

## STEP 4: Check Service Health

4.1) In the Monitor menu, click `Service Health`

4.2) Explore the three sections:

- **Service issues:** active incidents affecting Azure services

- **Planned maintenance:** upcoming maintenance windows that might impact your resources

- **Health advisories:** changes or deprecations you should be aware of

4.3) Filter by your region (e.g., West Europe) and the services you use

4.4) Check the incident history to see past outages and how they were resolved — this is useful for understanding Azure`s reliability track record

4.5) Click `+ Create health alert` to set up automatic notifications when Azure services you depend on have issues

4.6) Remember the three levels:

- **Azure Status** https://status.azure.com — global view of all services

- **Service Health** — personalized to your subscription and resources

- **Resource Health** — status of a specific individual resource

---

## STEP 5: Try the Pricing Calculator

5.1) Open a new browser tab and go to https://azure.microsoft.com/pricing/calculator 

5.2) Add a sample scenario: search for `Virtual Machines` and add one

5.3) Configure it: region, OS, tier, instance size, hours per month

5.4) Add `Storage Accounts` and `Virtual Network` to see how a complete solution adds up

5.5) Review the estimated monthly cost at the bottom

---

## STEP 6: Final Cleanup

6.1) Check if is there still any resource groups you`ve created during the 5 training sessions

6.2) If so, delete each resource group to avoid any future charges

6.3) Verify in Cost Management that no charges are pending

6.4) If you no longer need the subscription, you can cancel it from the Subscriptions page

**TIP:** Bookmark the Pricing Calculator — it's one of the most practical tools you`ll use when planning real Azure deployments.
