# powershell-autocomplete
Configures powershell to auto-complete commands based on the history

```powershell
$powershellProfile=@"
# Shows navigable menu of all options when hitting Tab
Set-PSReadlineKeyHandler -Key Tab -Function MenuComplete

# Autocompletion for arrow keys
Set-PSReadlineKeyHandler -Key UpArrow -Function HistorySearchBackward
Set-PSReadlineKeyHandler -Key DownArrow -Function HistorySearchForward

Import-Module posh-git

Import-Module PSReadLine
Set-PSReadLineOption -colors @{ Default = "Green"}
Set-PSReadLineOption -colors @{ Parameter = "Blue"}
Set-PSReadLineOption -colors @{ Command = "Magenta"}

function prompt {
" $ "
}

Import-Module Terminal-Icons

Clear

pwd

"@

$powershellProfile > $PSHOME\Profile.ps1
```
