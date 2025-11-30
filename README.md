# Windows Terminal Setup

![TerminalPreview](https://github.com/ahmadthakur/windows_terminal_config_files/blob/main/showcase.png?raw=true)

This is my setup for a minimal and aesthetic look for the windows terminal. 

## Install Nerd Fonts

1.  Go to: https://www.nerdfonts.com
2.  Download your preferred NF (I use **MesloLGM Nerd Font**)
3.  Extract & install
4.  Set in Windows Terminal: **Profiles → PowerShell → Appearance → Font face →`MesloLGM Nerd Font`**
    
## Install Winfetch

Winfetch is a command-line system information utility for Windows written in PowerShell. It's just like Neofetch.

```
Install-Script winfetch
```

## Install Oh My Posh

Oh My Posh is a custom prompt engine for any shell.

```
winget install JanDeDobbeleer.OhMyPosh --source winget
```

## Terminal Utilities
### Install Terminal Icons

```
Install-Module -Name Terminal-Icons -Repository PSGallery -Force
```

### Install PSReadLine Enhancements

```
Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck
```

Open your powershell profile config in notepad, usually at `C:\Users\[Username]\Documents\PowerShell` or open from the terminal:

```
notepad $PROFILE
```

Then paste the following lines in your config:

```
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH/montys.omp.json" | Invoke-Expression

Import-Module Terminal-Icons

Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView
```

Save and exit.

Once added, reload your profile for the changes to take effect.

```
. $PROFILE
```

To try out a different Oh My Posh theme, go to https://ohmyposh.dev/docs/themes, copy the name of the theme you like, and change the `--config` parameter [theme] in the Oh My Posh line in your profile config.

```
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH/[theme].omp.json" | Invoke-Expression
```