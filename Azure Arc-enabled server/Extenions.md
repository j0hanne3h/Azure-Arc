# Extensions with Azure Arc-enabled Servers

## What are extensions?

Azure Arc-enabled servers enables you to deploy, remove, and update Azure VM extensions to non-Azure Windows and Linux VMs, simplifying the management of your hybrid machine through their lifecycle. 
VM extensions can be managed using the following methods on your hybrid machines or servers managed by Arc-enabled servers:

- Azure Portal
- Azure CLI
- Azure Powerhsell during cmdLets

## Azure Arc-enabeld servers extensions 

| Extension | Description |
| --- | --- |
| Windows Patch Extension | The WindowsPatchExtension is used for the Assessment between Azure Arc and the onboarded Servers. The Extension can find out if Updates are required on the Servers or send Azure the status of the updates | 


## Troubleshoot Azure Arc-enabled servers VM extension issues on Windows Server

| Log File | Description | Server Location | OS | 
| --- | --- | --- | --- | 
| Guest Agent Log | Installation and Updating of the Extensions | %SystemDrive%\ProgramData\GuestConfig\ext_mgr_logs | Windows | 
| Detailed Extensio Log | All installed Extensions on the Server have stored here the Logs | %SystemDrive%\ProgramData\GuestConfig\extension_logs\ | Windows |



