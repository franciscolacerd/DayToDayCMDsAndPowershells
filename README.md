# DayToDayCMDsAndPowershells
That day to day CMDs And Powershells scripts of salvation!

## Update all programs in Windows machine
```winget upgrade --all```
https://learn.microsoft.com/en-us/windows/package-manager/winget/upgrade

## Restart windows services
```
enter-pssession SERVERNAME
get-service -Name 'SERVICENAME' | ft -a
start-service -Name 'SERVICENAME'
stop-service -Name 'SERVICENAME'
restart-service -Name 'SERVICENAME'
```
 
