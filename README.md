# Azure Update Management Center PowerShell Module

The Azure Update Management Center (UMC) PowerShell module is based on the UMC REST API documentation for [Azure Compute](https://learn.microsoft.com/en-us/azure/update-center/manage-vms-programmatically) and [Azure Arc Connected Compute](https://learn.microsoft.com/en-us/azure/update-center/manage-arc-enabled-servers-programmatically). This code is intended as a stop-gap for functionality not implemented in the Azure PowerShell module. 

Please, see the [issues](./issues) page for open issues or to open an issue.

## Dependencies

The UMC PowerShell module relies on the latest Azure PowerShell module and was written on PowerShell Core 7.x. Microsoft provides excellent documentation on how to deploy these items at the links below.

1. [Az PowerShell Module](https://learn.microsoft.com/en-us/powershell/azure/install-az-ps)
2. [PowerShell Core](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell)

## Installation

### 1. Download the AUMC PowerShell Module

Download the latest AUMC.psm1 file in the root of this repo or by clicking [here](./AUMC.psm1).

### 2. Install the AUMC PowerShell Module

You have two options for installing the AUMC PowerShell Module. You can manually import the AUMC.ps1 with the command below if you'd like to tinker with the module.

```pwsh
Import-Module <path-to-file>/AUMC.psm1
```

Or you can load the file permanently based on your [PSModulePath](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_psmodulepath). This can be done by getting a list of your PSModulePath's and copying the AUMC.psm1 file to a directory named "AUMC" to the appropriate directory. The module may be submitted to the PowerShell Gallery in the future, at which time you can use [Install-Module](https://learn.microsoft.com/en-us/powershell/module/powershellget/install-module) with the appropriate scope.

```pwsh
PS C:\> $env:PSModulePath -split ';'
C:\Users\<username>\Documents\PowerShell\Modules
C:\Program Files\PowerShell\Modules
c:\program files\powershell\7\Modules
C:\Program Files\WindowsPowerShell\Modules
C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules
C:\Program Files (x86)\Microsoft Azure Information Protection\Powershell
```

### 3. Review Commands and Documentation

If you loaded the module to one of the $env:PSModulePath locations, you can run the following command to get a list of the available commands.

```pwsh
PS C:\> Get-Command -Module AUMC
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Add-AUMCConfigurationAssignment                    0.0        AUMC
Function        Get-AUMCAssessmentPatches                          0.0        AUMC
Function        Get-AUMCAssessmentStatus                           0.0        AUMC
Function        Get-AUMCDeploymentActivities                       0.0        AUMC
Function        Get-AUMCDeploymentHistory                          0.0        AUMC
Function        Get-AUMCDeploymentStatus                           0.0        AUMC
Function        Get-AUMCVMUpdateSettings                           0.0        AUMC
Function        Invoke-AUMCAssessment                              0.0        AUMC
Function        Invoke-AUMCOneTimeDeployment                       0.0        AUMC
Function        New-AUMCMaintenanceConfigurationSchedule           0.0        AUMC
Function        Set-AUMCVMMaintenanceScheduleAssociation           0.0        AUMC
Function        Set-AUMCVMUpdateSettings                           0.0        AUMC
```

Most of the functions can be called with Get-Help to see the associated documentation. I will create example executions in the future.

```pwsh
PS C:\> Get-Help Add-AUMCConfigurationAssignment
```

__NOTE:__ This item is a work in progress and is updated as I have time. Please, see the issues tab for items that need to be done. Feel free to add additional feature requests, make recommendations for restructuring the data, etc.