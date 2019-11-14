# Workstation setup

## Chocolatey script
First install chocolatey (open in Admin mode):
https://chocolatey.org/install
``` ps
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

## Packages

``` powershell
# choco install sqllocaldb -y Localdb is already part of workload in Visual studio
choco install dotnetcore-sdk -y
choco install netfx-4.7.2-devpack -y
choco install sourcetree -y
choco install vscode -y
choco install visualstudio2019community -y
choco install visualstudio2017community -y
choco install resharper -y
choco install jetbrains-rider -y
choco install fiddler -y
choco install git -y
choco install notepadplusplus -y
choco install chromium -y
choco install googlechrome -y
choco install firefox -y
choco install ilspy -y
choco install winmerge -y
choco install seq -y
choco install robo3t -y
choco install putty -y
choco install slack -y
choco install microsoft-teams -y
choco install openvpn -y
```

## Manual setup:
- pretty putty
- lister.exe
- Windows Terminal
- 4K Video Downloader

## TODOs:
- include visual studio extensions
- include visual studio workloads
  - https://docs.microsoft.com/en-us/visualstudio/install/use-command-line-parameters-to-install-visual-studio?view=vs-2019
  - https://docs.microsoft.com/en-us/visualstudio/install/workload-component-id-vs-community?vs-2019&view=vs-2019
  - https://github.com/jberezanski/ChocolateyPackages/blob/master/chocolatey-visualstudio.extension/EXAMPLES.md
- include vscode extensions