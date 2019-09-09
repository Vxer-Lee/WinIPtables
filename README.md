# WinIPtables
使用Powershell 防火墙规则屏蔽某个国家ip段 、fuck！


```PowerShell
$csv = Import-Csv -Path 'C:\Scripts\IPBlockList.csv'
$data = @()
$csv | ForEach-Object { $data += $_.From + "-" + $_.To }
write-host $data
#Set-NetFirewallRule -Name "BlockAllIPsInList" -RemoteAddress $data -Action Allow 

##############IP段地址编写规则例子#######################
#C:\Scripts\IPBlockList.csv
#
#From,To
#220.112.0.0,220.115.255.255
#220.152.128.0,220.152.255.255
#220.154.0.0,220.155.255.255
#220.158.240.0,220.158.243.255
#220.160.0.0,220.207.255.255
#220.231.0.0,220.231.63.255
########################################################
```
