### How to add bulk users in Microsoft Teams?
Please refer to [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/) and follow the instructions below to install the latest MicrosoftTeams Cmdlets module:

1. Run the command line:
> Install-Module -Name MicrosoftTeams

*Note: it may prompt "NuGet provider is required to continue...", so please input "Y" to install it first.*

![Teams Module](https://github.com/PeterWxin/powershell/blob/master/MicrosoftTeams/Screenshots/PowerShell_Teams01.png)

2. Run the command line:
> Import-Module MicrosoftTeams

3. Run the command line and enter Office 365 credentials:
> $credentials=Get-Credential

![O365 Credentials](https://github.com/PeterWxin/powershell/blob/master/MicrosoftTeams/Screenshots/PowerShell_Teams04.png)

> Connect-MicrosoftTeams -Credential $credentials

![O365 Credentials](https://flexmind.co/wp-content/uploads/2020/02/image-11.png)

*Note: once you provide the credentials, you will able to see the tenant information like this:*

![O365 Tenant](https://flexmind.co/wp-content/uploads/2020/02/image-12.png)

4. Run the command line to find and copy the GroupId of the team adding bulk users:
> get-team

5. Please refer to the instructions below to create a CSV file:
   
   1) Press **Windows** + **R** keys and input: "notepad",  
   2) Click **OK** to launch Notepad,  
   3) Here's the example content of the CSV file:
      
   ```
   Name
   name.name@domain.com
   name2.name2@domain.com
   ```
   4) Save the file as "addusers.csv" to a folder on the dard drive disk, like: D:\temp.

6. Run this script:

```
Import-Csv 'D:\temp\addusers.csv' | % { 
Add-TeamUser -User $_.Name -GroupId <GroupID>
} 
```

ALL DONE.

Thanks to [Rakesh Pandey](https://flexmind.co/blog/how-to-add-bulk-users-from-csv-file-to-ms-teams-using-powershell/) and [patrick138](https://gist.github.com/patrick138/83ba1745cf162e5e75437ab844fb6783)!

---
### TBD: How to create bulk teams in Microsoft Teams?
[To be continued](https://www.jijitechnologies.com/blogs/create-teams-microsoft-teams-powershell)
