## Connect On-Prem Server to Azure Arc-enabled Servers

#### Prerequsites
Install or Update Azure CLI to version 2.42.0 or above (https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)
Use the command 'az --version' to check current installed version

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

Azure Arc onboarding is required for on-premises machines.
On-Premise Servers can be onboard to Azure Arc from Azure Portal by using a PowerShell Script. There are different PowerShell Script Options for onboarding 
Servers to Azure Arc

| Options | Details | Prerequisits
| --- | --- | --- |
| Add a single Server | generate a script which runs locally on the targeted system | HTTPS Access to Azure Services and local administrator permissions| 
| Add multiple Server | add multiple server to azure arc by using an service principal Account | HTTPS Access to Azure Services & local admin permissions & Service Principal Account needs the 'Azure Connected Machine Onboarding Role'|

#### Using an Service Principal Account
<h6>(https://learn.microsoft.com/en-us/azure/azure-arc/servers/onboard-service-principal)</h6>

Using an Service Principal Account is safer than using an higher privileged Account like Tenant Administrator. **The Service Principal is used only during onboarding;
it is not used for any other purpose.**

To create Service Principal Account, your Azure Directory Tenant must allow user to register applications. If it does not, your account must be a member of the Application Administrator or Cloud Application Administrator role.
To assign Arc-enabled server roles, your Account must be Member of the owner or user Access Administrator role in the subscription that you want to use for onboarding

## Connect Windows Azure Virtual Machine to Azure Arc 
<h6>https://azurearcjumpstart.io/azure_arc_jumpstart/azure_arc_servers/azure/azure_arm_template_win/#deploy-a-windows-azure-virtual-machine-and-connect-it-to-azure-arc-using-an-arm-template</h6>

Important:
The Connected Machine agent cannot be installed on an Azure virtual machine. The install script will warn you and roll back if it detects the server is running in Azure.

You have multiple options for deploying and configuring Win Azure VM's to Azure Arc:
- Azure Portal
- ARM template vai Azure CLI

The ARM template incl. an Azure VM customs cript which will deploy the 'Install-arc-agent.ps1' PowerShell Script
The Script goes during following steps and configurations to connect successfully zu Azure Arc
- Set local enviorment variables
- Generate a local OS enviorment variables 
  - Generate the LogonScript.log file
  - Stop and disable the "Win Azure Guest Agent"
  - Create new Firewall rule to block Azure IMDS outbound traffic to the remote adress
  - Unregister the logon Script -> one time deployment
- User connect to the Azure VM with RDP or using Azure Bastion which will start the LogonScript and will onboard the VM to Azure Arc

By using RDP, the port 3389 (TCP/UDP) is not allowed on the network security group. You must create an NSG rule to allow inbound 3389. 
Therefore you must open the affected ressource group in Azure portal and click "Add" to add new rule.

