$When = ((Get-Date).AddDays(-60)).Date
Get-ADUser -Filter {whenCreated -ge $When} -Properties whenCreated | Select Name, SamAccountName, UserPrincipalName | Export-Csv -Path C:\Users\user\Desktop\ultimos60dias.csv
