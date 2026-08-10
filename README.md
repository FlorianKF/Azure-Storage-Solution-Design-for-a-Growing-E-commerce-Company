# Azure Storage Solution Design for a Growing E-commerce Company  named Fabulous.com in France

In this case study, we would like to design an Azure storage solution for ***Fabulous.com***  by selecting the appropriate storage services, comparing LRS, ZRS, GRS, and GZRS, and defining a migration strategy.

# Problem

 ***Fabulous.com*** A French Ecommerce company is experiencing strong growth and wants to migrate its storage infrastructure to Microsoft Azure to improve application performance, ensure data availability, and reduce operating costs.

The company manages several types of data:

- Product images viewed daily by customers on the website;

- Shared documents used by internal teams;

- Regular backups to ensure disaster recovery;

- Archives that must be retained for several years to meet legal requirements.

Each workload has different requirements in terms of performance, durability, availability, cost, and access frequency.

In addition, Mr. Dupont, the CEO, wants to implement a storage redundancy strategy that minimizes the risk of data loss in the event of hardware failures or regional outages while remaining within budget.
Finally, the company plans to migrate several tens of terabytes of data to Azure and must determine the most appropriate migration tools for each scenario.

### Objective

Design a secure, scalable, and cost-effective Azure Storage solution that meets the company's business and technical requirements.

# Proposed solutions

We will meet the Fabulous.com's technical and commercial requirements by offering Azure storage solutions based on selecting the storage services best suited to each workload, implementing an appropriate redundancy strategy, and choosing the best data migration solution to Azure.

## 1. The Appropriate Azure Storage Services

| Workload |Azure Account Services | Reasons|
|----------|--------------|--------|
|Product images, log files, Regular backups | Azure Blob Storage |Optimized for unstructured data, scalable, cost-effective, and accessible via HTTP/HTTPS|
|Shipping procedures, current invoices, current budgets, current financial report, current supplier documents etc..|Azure Files|  Provides SMB file shares that employees can access from multiple devices|
|Customer profiles, user events, delivery tracking, orders, inventory data, Recommendation data, etc.. | Table Storage |These are generally large quantities of structured or semi-structured NoSQL data for a rapidly growing website|

## 2. Let's choose the appropriate access tiers for Fabulous.com

|Data | Access Tiers | Reasons|
|-----|---|---|
|Product images| Hot|Accessed frequently by website visitors and regular customers|
|Regular backups and log files| cool |If they are primarily kept for analysis or compliance purposes and rarely consulted|
|Old invoices, old financial reports, old budgets, supporting documents etc...|Archive| Historical documents rarely consulted, kept mainly for legal, accounting or compliance reasons|

## 3. Redundancy Recommendation
To address Mr. Dupont's specific concerns, we will propose different Azure Storage redundancy options to provide the best possible solution for Fabulous.com. Assuming that Fabulous.com selects the FranceCentral Azure region as its primary region, we will evaluate the available options based on their level of protection, availability, and cost.


|Options |Redundancy mechanisms |Protection level| Cost |
|-------|---------------------|-----------------|---|
|LRS|Fabulous.com's data will be replicated three times within a single datacenter in the FranceCentral region|Low (Datacenter failure)| Low|
|ZRS|Fabulous.com's data will be replicated across three availability zones within the France Central region, ensuring that a copy of the data is maintained in each zone|Medium (Availability Zone failure)| Medium|
|GRS|Fabulous.com's data will be replicated three times in the primary region, FranceCentral, and asynchronously replicated three additional times in the secondary region, FranceSouth| High (Regional disaster)|High|
|GZRS|Three copies of Fabulous.com's data are replicated across three availability zones in the primary France Central region, while three oders copies are asynchronously replicated in three availability zone in secondary region FranceSud|Higher (Zone + Regional disaster)| Higher|

Therefore, GZRS clearly appears to be the best option for Mr. Dupont because:

- High availability across multiple Availability Zones
- Geo-replication to a secondary Azure region
- Excellent durability for business-critical workloads
- Very low Recovery Point Objective (RPO)
- Suitable for an e-commerce platform where downtime directly impacts revenue
  
Although GZRS is more expensive than LRS or ZRS, but it provides the best balance between resilience and business continuity for Fabulous.com.


# 4. So, how can we migrate Fabulous.com's existing backup data to Azure Storage?
