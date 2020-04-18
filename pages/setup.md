# Workstation setup

## Chocolatey script
First install chocolatey (open in Admin mode):
<https://chocolatey.org/install>
``` ps
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

## Packages

``` powershell
# choco install sqllocaldb -y LocalDB is already part of workload in Visual studio
choco upgrade dotnetcore-sdk -y
choco upgrade netfx-4.7.2-devpack -y
choco upgrade sourcetree -y
choco upgrade vscode -y
choco upgrade visualstudio2019community -y
choco upgrade visualstudio2017community -y
choco upgrade resharper -y
choco upgrade jetbrains-rider -y
choco upgrade fiddler -y
choco upgrade git -y 
choco upgrade notepadplusplus -y
choco upgrade chromium -y
choco upgrade googlechrome -y
choco upgrade firefox -y
choco upgrade ilspy -y
choco upgrade winmerge -y
choco upgrade seq -y
choco upgrade robo3t -y
choco upgrade putty -y
choco upgrade slack -y
choco upgrade microsoft-teams -y
choco upgrade openvpn -y
choco upgrade nodejs -y
choco upgrade docker-desktop -y
choco upgrade notepadplusplus.install -y
choco upgrade 7zip.install -y
choco upgrade vlc -y
choco upgrade sql-server-management-studio -y
choco upgrade winscp.install -y
choco upgrade ruby -y
choco upgrade dropbox -y
choco upgrade youtube-dl -y
choco upgrade sublimetext3 -y
choco upgrade spotify -y
choco upgrade powershell-core -y --install-arguments='"ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 REGISTER_MANIFEST=1 ENABLE_PSREMOTING=1"'
```

## Manual setup:
- pretty putty
- lister.exe
- Windows Terminal (in store)

## TODOs:
- include visual studio code extensions
- include visual studio extensions
- include visual studio workloads
  - <https://docs.microsoft.com/en-us/visualstudio/install/use-command-line-parameters-to-install-visual-studio?view=vs-2019>
  - <https://docs.microsoft.com/en-us/visualstudio/install/workload-component-id-vs-community?vs-2019&view=vs-2019>
  - <https://github.com/jberezanski/ChocolateyPackages/blob/master/chocolatey-visualstudio.extension/EXAMPLES.md>
- include vscode extensions