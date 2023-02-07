# Extensions with Azure Arc-enabled Servers

## What are extensions?

Azure Arc-enabled servers enables you to deploy, remove, and update Azure VM extensions to non-Azure Windows and Linux VMs, simplifying the management of your hybrid machine through their lifecycle. 
VM extensions can be managed using the following methods on your hybrid machines or servers managed by Arc-enabled servers:

- Azure Portal
- Azure CLI
- Azure Powerhsell during cmdLets

## Azure Arc-enabeld servers extensions 

| Extension | Description | Stored Location Log File | 
| --------- | --------- | --------- |
| Windows Patch Extension | The WindowsPatchExtension is used for the Assessment between Azure Arc and the onboarded Servers. The Extension can find out if Updates are required on the Servers or send Azure the status of the updates | C:\ProgramData\GuestConfig\extension_logs\Microsoft.CPlat.Core.WindowsPatchExtension
| Windows OS Update Extension | The WindowsOSPatchExtension protocolls the installation activity on the Server. If Updates are installed from Azure Arc Update Management Center the log save the prcess the status of the installation. Also the Log protocolls the status of the installed Extensions. | C:\ProgramData\GuestConfig\extension_logs\Microsoft.SoftwareUpdateManagement.WindowsOsUpdateExtension


## Working with PowerShell 

Extensions can also be managed by PowerShell. Therefore you need to Install the Az.ConnectedMachineAgent Module in PowerShell and import it (Import-Module). 
Use Connect-AzAccount to connect your Active Directory User with PowerShell. 
For managing Azure Arc Extensions with PowerShell, you need to have following roles in Azure:
- Azure Contributor Role
- Azure Connected Machine Ressource Administrator

| CmdLet | Description |
| --- | --- |
| Get-AzConnectedMachineExtension -RessourceGroupname 'RessourceGroup' -MachineName 'MachineName' | Get all installed Azure Extensions on the Server |




