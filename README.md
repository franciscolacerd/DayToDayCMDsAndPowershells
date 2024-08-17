# Day To Day CMDs And Powershells
That day to day CMDs And Powershells scripts of salvation!

## Update all programs in Windows machine
https://learn.microsoft.com/en-us/windows/package-manager/winget/upgrade

CMD
```CMD
winget upgrade --all --include-unknown
```

## Restart windows services
Powershell
```Powershell
enter-pssession SERVERNAME
get-service -Name 'SERVICENAME' | ft -a
start-service -Name 'SERVICENAME'
stop-service -Name 'SERVICENAME'
restart-service -Name 'SERVICENAME'
```
 
## Restart IIS
CMD
```CMD
iisreset
```

Powershell
```Powershell
$remoteServer = "SERVERNAME"
$username = "USERNAME"
$password = ConvertTo-SecureString -String "PASSWORD" -AsPlainText -Force
$credential = New-Object System.Management.Automation.PSCredential($username, $password)
Invoke-Command -ComputerName $remoteServer -Credential $credential -ScriptBlock { Get-Service -Name "W3SVC" | Stop-Service -Force }
Invoke-Command -ComputerName $remoteServer -Credential $credential -ScriptBlock { Get-Service -Name "W3SVC" | Start-Service }
```

https://learn.microsoft.com/en-us/sysinternals/downloads/pstools

CMD com pstools
```CMD
psexec \\SERVERNAME -u USERNAME -p PASSWORD iisreset
```
