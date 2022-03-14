$When = ((Get-Date).AddDays(-60)).Date
Get-ADUser -Filter {whenCreated -ge $When} -Properties whenCreated | Select Name, SamAccountName, UserPrincipalName | Export-Csv -Path C:\Users\user\Desktop\ultimos60dias.csv



$Days = 90
$Time = (Get-Date).Adddays(-($Days))
Get-ADUser -Filter * -Property whenCreated, Name, Mail, Department | Where {$_.whenCreated -gt $Time} | Select Name, Mail, Department | Export-Csv -Path C:\Users\user\Desktop\ultimos60dias.csv
