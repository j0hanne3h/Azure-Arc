### Onboarding Sevrers to Azure Arc
Azure Arc onboarding is required for on-premises machines.
On-Premise Servers can be onboard to Azure Arc from Azure Portal by using a PowerShell Script. There are different PowerShell Script Options for onboarding 
Servers to Azure Arc

| Options | Details | Prerequisits
| --- | --- | --- |
| Add a single Server | generate a script which runs locally on the targeted system | HTTPS Access to Azure Services and local administrator permissions| 
| Add multiple Server | add multiple server to azure arc by using an service principal Account | HTTPS Access to Azure Services & local admin permissions & Service Principal Account needs the 'Azure Connected Machine Onboarding Role' |

### Prerequisits Azure Arc 
The following Windows Opearting Systems are supported for Azure Connected machines.

**OS:**
- Windows Server 2008 R2 SP1
- Windwos Server 2012 R2
- Windows Server 2016
- Windows Server 2019
- Windows Server 2022

**Azure Subscriptions:**
- Limit of 5.000 machines for each ressource Group
- Resource providers enabled 
  - Microsoft.HybridCompute
  - Microsfot.GuestConfiguration
  - Microsft.HybridConnectivity



### Guest Configuration Extension 
- If you using MMA, Defender for Cloud uses this extension to analyse operating system security baseline settings on Win & Linux
- Azure Arc-enabled Servers and the Guest Configuration Extension are free. Guest Configuration Ploicies on Azure Arc servers outside the scope of Defender for Cloud are not priceless

### Defender for Endpoint Extensions 
When you enable Defender for Server, Defender for Cloud automatically deploys a Defender for Endpoint Extension. This extenison runs a script on the server wihich installs 
the sensor on the machine
- Windows machine extension: MDE.Windows

**Minimun Machine requirements:**
- Supported Windows versions (Windows 7 SP1 Pro or higher) 
- Hardware requirements ( Core: 2 min, min 1GB Memory) 

