# Azure Storage Solution Design for a Growing E-commerce Company  named Fabulous.com in France

In this case study, we would like to design an Azure storage solution ***Fabulous.com***  by selecting the appropriate storage services, comparing LRS, ZRS, GRS, and GZRS, and defining a migration strategy.

# Problem

 ***Fabulous.com*** A French Ecommerce company is experiencing strong growth and wants to migrate its storage infrastructure to Microsoft Azure in France to improve application performance, ensure data availability, and reduce operating costs.

The company manages several types of data:


- Product images viewed daily by customers on the website;

- Shared documents used by internal teams;

- Regular backups to ensure disaster recovery;

- Archives that must be retained for several years to meet legal requirements.

Each type of data has different requirements in terms of performance, durability, availability, cost, and access frequency.

At the same time, management wants to implement a redundancy strategy to limit data loss in the event of hardware failure or a regional disaster, while staying within a controlled budget. The company also plans to migrate several tens of terabytes of data to Azure and must choose the most suitable tools for each migration scenario.
