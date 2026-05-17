# LAB 4 — Exploring Access Controls and Policies in the Portal

## STEP 1: View Role Assignments (IAM)

1.1) Navigate to any resource group in the portal.

1.2) Click `Access control (IAM)` in the left menu.

1.3) Click the `Role assignments` tab to see who has access and at what level.

<img width="1653" height="700" alt="image" src="https://github.com/user-attachments/assets/047615c2-13ba-47be-aab1-a21a1d05ab33" />


1.4) Look at the built-in roles listed:

- **Owner** — full access to all resources, can delegate access to others.

- **Contributor** — can create and manage all resources, but cannot grant access.

- **Reader** — can only view existing resources, no changes allowed.

- **Cost Management Reader** — Can view cost data and configuration.

1.5) Click `Check access` and type your own name or email — you`ll see which roles are assigned to you and where they were inherited from.

<img width="899" height="492" alt="image" src="https://github.com/user-attachments/assets/65e6289b-f298-416f-b644-a5bf0eac3998" />

<img width="526" height="273" alt="image" src="https://github.com/user-attachments/assets/6cc073e2-1155-46c7-9372-6637bbbbdd8e" />


---

## STEP 2: Understand Role Assignment (Read-Only Walkthrough)

2.1) Click `+ Add` > `Add role assignment` to see the workflow (you don't need to complete it).

<img width="568" height="281" alt="image" src="https://github.com/user-attachments/assets/7ef039dd-f118-40b8-814a-1ab777492667" />

2.2) Browse the available roles — notice there are dozens beyond the basic four, like `Virtual Machine Contributor` or `Storage Blob Data Reader`

<img width="1468" height="813" alt="image" src="https://github.com/user-attachments/assets/aea7490d-302c-4f3a-8451-1e8e6849415f" />


2.3) On the `Members` tab, you`d search for a user, group, or service principal to assign the role to.

<img width="785" height="491" alt="image" src="https://github.com/user-attachments/assets/5979366e-f662-432f-88a5-1358b3609367" />

<img width="509" height="555" alt="image" src="https://github.com/user-attachments/assets/89b81d65-b530-4228-814f-19f57ebac6a0" />

2.4) On the `Conditions` tab (available for some roles), you can add fine-grained conditions like `only allow access to blobs tagged with department=finance`

<img width="1316" height="797" alt="image" src="https://github.com/user-attachments/assets/e865f01d-bc26-4f4a-acd8-e7def4f9300b" />

2.5) Key concept — inheritance: a role assigned at the subscription level automatically applies to all resource groups and resources below it. This is why the hierarchy matters.

2.6) Cancel out of the assignment — this was just to explore the interface.

---

## STEP 3: Explore Azure Policy

3.1) Search for `Policy` in the portal search bar.

3.2) Click `Definitions` in the left menu to see all built-in policy definitions.

<img width="1800" height="761" alt="image" src="https://github.com/user-attachments/assets/9b352f93-54dc-4ec8-aac5-443f170f71b9" />


3.3) Use the Category filter to browse policies by topic: try `Tags`, `Compute`, `Storage`, `Monitoring`.

<img width="474" height="343" alt="image" src="https://github.com/user-attachments/assets/8c558186-1af4-43db-9652-637705a99863" />


3.4) Open an example policy: `Require a tag on resource groups`.

<img width="965" height="735" alt="image" src="https://github.com/user-attachments/assets/18385781-d4e5-4037-8f9f-5b3cc689a54f" />


3.5) Read the policy rule — it follows an if/then structure:

- IF: a resource group is created or updated without the required tag.

- THEN: the effect is applied (Deny = block it, Audit = log it, Modify = auto-fix it).

3.6) Notice how policies are written in JSON.

<img width="675" height="784" alt="image" src="https://github.com/user-attachments/assets/9963f92b-32f6-4b9a-bf7f-0144803a4f2e" />


---

## STEP 4: See a Policy Assignment in Action

4.1) Click `Assignments` in the left menu to see policies currently assigned to your subscription.

<img width="1888" height="597" alt="image" src="https://github.com/user-attachments/assets/6d0d77f1-208e-4030-9a0b-e3e9cc056c9a" />

4.2) Click `+ Assign policy` to explore the workflow:

- Scope: where the policy applies (subscription or resource group).

- Policy definition: which rule to enforce.

- Parameters: specific values (e.g., tag name = `Environment`)

<img width="1898" height="769" alt="image" src="https://github.com/user-attachments/assets/dff6f11f-f163-45d4-a9d0-4f5f9693573f" />


4.3) If a policy with `Deny` effect is assigned and you try to create a resource group without the required tag, Azure will block the creation with an error message.

4.4) Remember the key difference: Azure Policy controls what RESOURCES can do. RBAC controls what USERS can do.

---

## STEP 5: Explore Microsoft Defender for Cloud

5.1) Search for `Defender for Cloud` in the portal.

5.2) Look at the overview dashboard: Secure Score, security recommendations, and active alerts.

<img width="1394" height="831" alt="image" src="https://github.com/user-attachments/assets/8b570904-7268-49ee-a24d-8529af24f09c" />

5.3) Explore other tabs like: 

 - **Secure Score:** graph that reflects how many security recommendations you've implemented. Higher is better.

 - **Recommendations:** Tracks security vulnerabilities, configuration errors and exposed secrets on your environment. You can browse through categories: networking, compute, data, identity, and IoT.
 
 - **Regulatory compliance dashboard:** Shows how your environment maps to standards like ISO 27001, PCI DSS, and SOC 2.

 - **Network Security:** Enable Azure network security features like: Firewall, DDoS protection and Web Application Firewall (WAF)

