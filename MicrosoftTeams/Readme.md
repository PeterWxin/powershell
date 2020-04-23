### How to add bulk users in Microsoft Teams?
Please refer to [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/) and follow the instructions below to install the latest PowerShell MicrosoftTeams Cmdlets module:
1. Run the command line:
  > Install-Module -Name MicrosoftTeams

(Note: it may prompt "NuGet provider is required to continue...", so please input "Y" to install it first.)

![Teams Module](https://github.com/PeterWxin/powershell/blob/master/MicrosoftTeams/Screenshots/PowerShell_Teams01.png "Install teams module")

2. Run the command line:
  > Import-Module MicrosoftTeams
  
3. Run the command line and enter Office 365 credentials:
  > Connect-MicrosoftTeams

![O365 Credentials](https://flexmind.co/wp-content/uploads/2020/02/image-11.png "name & password")

Once you provide the credentials, you will able to see the tenant information like:

![O365 Tenant](https://flexmind.co/wp-content/uploads/2020/02/image-12.png "Tenant information")

4. Run the command line to find and copy the GroupId of the team adding bulk users:
  > get-team

5. Please refer to the instructions below to create a CSV file:
  1) Press **Windows** + **R** keys and input: "notepad"
  2) Click **OK** to launch Notepad
  3) Here's an the example content of the CSV file
`Name
name.name@domain.com
name2.name2@domain.com`

---
### TBD: How to create bulk teams in Microsoft Teams?
[To be continued](https://www.jijitechnologies.com/blogs/create-teams-microsoft-teams-powershell)
