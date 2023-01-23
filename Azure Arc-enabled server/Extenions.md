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






