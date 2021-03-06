# Workstation setup

## Chocolatey script
First install chocolatey (open in Admin mode):
<https://chocolatey.org/install>
``` ps
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

## Packages

``` powershell
# choco install sqllocaldb -y  #LocalDB is already part of workload in Visual studio, and there can be version mismatch
# choco upgrade dotnetcore-sdk -y
# choco upgrade netfx-4.7.2-devpack -y
# choco upgrade sourcetree -y  # for some reason the automated install is not working (maybe the required login from atlassian)
choco upgrade vscode -y
choco upgrade visualstudio2019community -y
# choco upgrade visualstudio2017community -y
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
choco upgrade 7zip -y
choco upgrade vlc -y
choco upgrade sql-server-management-studio -y
choco upgrade winscp -y
choco upgrade ruby -y
choco upgrade dropbox -y
choco upgrade youtube-dl -y
choco upgrade sublimetext3 -y
choco upgrade spotify -y
choco upgrade powershell-core -y --install-arguments='"ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 REGISTER_MANIFEST=1 ENABLE_PSREMOTING=1"'
choco upgrade rabbitmq -y
choco upgrade greenshot -y
choco upgrade postman -y
choco upgrade github -y
choco upgrade kubernetes.cli -y
```

## Manual setup:
- pretty putty
- lister.exe
- Windows Terminal (in store)
- R# strcutured plugin https://plugins.jetbrains.com/plugin/12083-structured-logging

- dnSpy https://github.com/0xd4d/dnSpy/releases
- superBenchamerker


# Windows setup (remove bloat, set basic settins)
upstream: https://github.com/Disassembler0/Win10-Initial-Setup-Script
my own fork: https://github.com/videokojot/Win10-Initial-Setup-Script

## TODOs:
- include visual studio code extensions
- include visual studio extensions
- ruby jekyll setup