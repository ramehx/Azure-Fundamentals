# LAB 4 — Exploring Access Controls and Policies in the Portal

## STEP 1: View Role Assignments (IAM)

1.1) Navigate to any resource group in the portal.

1.2) Click `Access control (IAM)` in the left menu.

1.3) Click the `Role assignments` tab to see who has access and at what level.

1.4) Look at the built-in roles listed:

- **Owner** — full access to all resources, can delegate access to others.

- **Contributor** — can create and manage all resources, but cannot grant access.

- **Reader** — can only view existing resources, no changes allowed.

- **User Access Administrator** — can manage user access to resources.

1.5) Click `Check access` and type your own email — you`ll see which roles are assigned to you and where they were inherited from.

---

## STEP 2: Understand Role Assignment (Read-Only Walkthrough)

2.1) Click `+ Add` > `Add role assignment` to see the workflow (you don`t need to complete it).

2.2) Browse the available roles — notice there are dozens beyond the basic four, like `Virtual Machine Contributor` or `Storage Blob Data Reader`

2.3) On the `Members` tab, you`d search for a user, group, or service principal to assign the role to.

2.4) On the `Conditions` tab (available for some roles), you can add fine-grained conditions like `only allow access to blobs tagged with department=finance`

2.5) Key concept — inheritance: a role assigned at the subscription level automatically applies to all resource groups and resources below it. This is why the hierarchy matters.

2.6) Cancel out of the assignment — this was just to explore the interface.

---

## STEP 3: Explore Azure Policy

3.1) Search for `Policy` in the portal search bar.

3.2) Click `Definitions` in the left menu to see all built-in policy definitions.

3.3) Use the Category filter to browse policies by topic: try `Tags`, `Compute`, `Storage`, `Monitoring`.

3.4) Open an example policy: `Require a tag on resource groups`.

3.5) Read the policy rule — it follows an if/then structure:

- IF: a resource group is created or updated without the required tag.

- THEN: the effect is applied (Deny = block it, Audit = log it, Modify = auto-fix it).

3.6) Notice how policies are written in JSON.

---

## STEP 4: See a Policy Assignment in Action

4.1) Click `Assignments` in the left menu to see policies currently assigned to your subscription.

4.2) Click `+ Assign policy` to explore the workflow:

- Scope: where the policy applies (subscription or resource group).

- Policy definition: which rule to enforce.

- Parameters: specific values (e.g., tag name = `Environment`)

4.3) If a policy with `Deny` effect is assigned and you try to create a resource group without the required tag, Azure will block the creation with an error message.

4.4) Remember the key difference: Azure Policy controls what RESOURCES can do. RBAC controls what USERS can do.

---

## STEP 5: Explore Microsoft Defender for Cloud

5.1) Search for `Defender for Cloud` in the portal.

5.2) Look at the overview dashboard: Secure Score, security recommendations, and active alerts.

5.3) Click on your Secure Score — it's a percentage that reflects how many security recommendations you've implemented. Higher is better.

5.4) Go to `Recommendations` and browse the categories: networking, compute, data, identity, and IoT.

5.5) Open any recommendation to see the issue description, affected resources, and step-by-step remediation instructions.

5.6) Check the `Regulatory compliance` dashboard — it shows how your environment maps to standards like ISO 27001, PCI DSS, and SOC 2.

