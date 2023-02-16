## Azure Arc Pricing

### Azure Arc SQL Server 
SQL Server on Arc-enabled Servers brings all the Azure Management capabilities to SQL Server enviorments. 

| | monthly rate | hourly rate |
| --- | --- | --- |
| Standard Eition | 67,34€ | 0,09€ | 
| Enterprise Edition | 252,52€ | 0,35€ |

### Guest Configuration feature of Azure Policy
The Guest Configuration provides compliance and configuration management of the operating system. 
Billing is based on the number of servers registerd with the service that have one or more guest configurations assigned to them. Billing is pro-rated hourly. 
Offline or disconnected machines are not billed.

Azure Arc resources managed by guest configuration are exclueded from billin in the following scenarios.

Azure Automation
- Guest Configuration assignments are not billed, if the machine is already managed by the state configuration of change tracking offered by Azure Automation

Microsoft Defender for Cloud
- Azure Policy assignment of a built-in policy initiative in the "Regulatory Compliance" category creates configuration assignment
- Azure Policy assignment of a custom policy initiative created in Microsoft Defender for Cloud creates configuration assignment

| | Azure Resource | Azure Arc Resource |
| --- | --- | --- |
| Azure control plane factory | free | free |
| Azure Policy guest configuration (includes Azure Automation change tracking, inventory, state configuration | free | 5,53€ per Server/Month |

### Microsoft Defender for Cloud
When you enable MS Defender for Cloud, we automatically enroll and start protecting all your resources unless you explicity decide to opt-out. For any resource that is 
protected by Defender for Cloud, you will be charged per the pricing model below.

MS Defender for Cloud is free for the first 30days. Any usafe beyond 30 days will be automatically charged per the pricing schema below

| Resource Type | Price |
| --- | --- |
| Microsoft Defender for Servers Plan 1 | 0,007€ Server/hour |
| Microsoft Defender for Servers Plan 2 | 0,019€ Server/hour |

more pricing schemas use the following link (https://azure.microsoft.com/en-us/pricing/details/defender-for-cloud/)
