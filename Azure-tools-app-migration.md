# Strategy

You can use tools such as [CloudPilot](https://www.cloudatlasinc.com/cloudpilot-migration-tool/) to create the resport for your applications, and leverage Database migrations tools such as Azure Datafactory ([ADF](https://docs.microsoft.com/en-us/azure/data-factory/scenario-ssis-migration-overview)) or some strategy to host SSRS databases in Azure SQL Managed Instance, as documented in [this article](https://techcommunity.microsoft.com/t5/azure-sql/hosting-ssrs-databases-in-azure-sql-managed-instance/ba-p/1700197). This last recommendation can support you to deal with:

- Integration Services (SSIS) - platform for building data integration and transformation solutions,
- Analysis Services (SSAS) - analytical data engine with tabular and multidimensional mode,
- Rerporting Services (SSRS) - tools and services for creating and managing paginated reports.

## SQL Server Reporting Services in Azure

- Moving your SSRS paginated reports to the Power Bi Premium service
- Deploying SQL Server Reporting Services Virtual machine
  - Two variations to address 1) report server (stateless engine of the SSRS) and 2) report server databases storing metadata and temporary report results.

## Moving your SSRS paginated reports to the Power Bi Premium service

To migrate your existing paginated reports in the Report Definition Language (RDL), you can use RDL Migration Tool [available here](https://github.com/microsoft/RdlMigration
). You can find more detailed guidance at [this location](https://docs.microsoft.com/en-us/power-bi/guidance/migrate-ssrs-reports-to-power-bi). You can find limitations [here.](https://docs.microsoft.com/en-us/power-bi/paginated-reports/paginated-reports-report-builder-power-bi#limitations-and-considerations)

[Useful information](https://powerbi.microsoft.com/en-us/blog/answering-your-questions-around-the-new-power-bi-premium-per-user-license/) about Power BI Premium per user license.

### **Deploying SSRS on SQL Server on Azure Virtual Machine**

Deploy SSRS on Azure Virtual MAchine and used Azure Hybrid Benefit licensing. More info [here.](https://techcommunity.microsoft.com/t5/sql-server/rehost-your-sql-server-to-azure-virtual-machines-for/ba-p/1698452)

### **Hosting report server databases in Azure SQL Managed Instance**

This option leverage PaaS
If your SSRS reports are pulling the data from databases hosted on Azure SQL Managed Instance, consider hosting report server databases on the same instance, thus minimizing the database engine footprint.
