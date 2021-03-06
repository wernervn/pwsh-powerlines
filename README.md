# pwsh-powerlines #
Taken from [Tutorial: Set up Powerline in Windows Terminal](https://docs.microsoft.com/en-us/windows/terminal/tutorials/powerline-setup)
Also: [How to change default font face on Windows Terminal](https://pureinfotech.com/change-font-face-windows-terminal)

### Install Posh-Git and Oh-My-Posh ###

```powershell
Install-Module posh-git -Scope CurrentUser
Install-Module oh-my-posh -Scope CurrentUser
```

If you are using PowerShell Core, install PSReadline:

```powershell
Install-Module -Name PSReadLine -Scope CurrentUser -Force -SkipPublisherCheck
```

### Powershell profile update ###

| Description                | Path                                                             |
|----------------------------|------------------------------------------------------------------|
| All Users, All Hosts       | $PSHOME\Profile.ps1                                              |
| All Users, Current Host    | $PSHOME\Microsoft.PowerShell_profile.ps1                         |
| Current User, All Hosts    | $Home\[My ]Documents\PowerShell\Profile.ps1                      |
| Current user, Current Host | $Home\[My ]Documents\PowerShell\Microsoft.PowerShell_profile.ps1 |

Add the following to $PSHOME\Profile.ps1
```powershell
Import-Module posh-git
Import-Module oh-my-posh
Set-PoshPrompt -Theme Theme-Name
```
Add the following to $Home\[My ]Documents\PowerShell\Microsoft.PowerShell_profile.ps1 (C:\Users\Werner\Documents\PowerShell\Microsoft.PowerShell_profile.ps1)
```powershell
Set-PoshPrompt -Theme ~/.wvn.omp.json
```
### (Alternative) Install using choco ###
Taken from:[Setup your terminal](https://ohmyposh.dev/docs/windows)
```powershell
choco install oh-my-posh
```
In the powershell init file, add the following command:
```powershell
oh-my-posh --init --shell pwsh --config ~/wvn-dotnetV2.omp.json | Invoke-Expression
```

### Install Nerd Font ###
https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/Meslo/L/Regular

### Creating custom powerlines ###

[Docs](https://ohmyposh.dev/docs/)

Existing themes located at: C:\Users\Werner\Documents\PowerShell\Modules\oh-my-posh\3.144.0\themes

Show all available themes:
```powershell
Get-PoshThemes
```
Add custom theme file in ~/, edit, then run ```. $profile``` to reload profile and custom theme.

### Extras ###

**1. Markdown table generator**

[How to Easily Format Tables in Markdown](https://ardalis.com/how-to-easily-format-tables-in-markdown)

[Tables Generator](https://www.tablesgenerator.com/markdown_tables)
