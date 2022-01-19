$When = ((Get-Date).AddDays(-60)).Date
Get-ADUser -Filter {whenCreated -ge $When} -Properties whenCreated | Select Name, SamAccountName, UserPrincipalName | Export-Csv -Path C:\Users\cristian.souza\Desktop\ultimos60dias.csv
