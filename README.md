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
|shipping procedures, inventories, supplier documents Invoices, financial reports, budgets, supporting documents etc..|Azure Files|  Provides SMB file shares that employees can access from multiple devices|
|Customer profiles, User events, Delivery tracking, Orders, Inventory data, Recommendation data, etc.. | Table Storage |These are generally large quantities of structured NoSQL data for a rapidly growing website|

