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
