# Chocolatey のインストール方法
Windows 向けのパッケージ管理ツール Chocolatey のインストール方法などを説明する。

Chocolatey は Scoop で管理できない、管理者権限がからむようなアプリの管理に使いたい。

ユーザ単位でアプリを管理できるものは Scoop を利用する。

Scoop とは（メリットと使い方：  
https://github.com/fs5013-furi-sutao/explain.scoop

インストールなどの参考サイトは以下。

ChocolateyでWindows環境を管理する：  
https://rimever.hatenablog.com/entry/2019/09/03/070000  

デフォルトのインストールパスは[C:\ProgramData\chocolatey\lib\sysinternals]となる。  

ログ
```console
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
```
Getting latest version of the Chocolatey package for download.
Getting Chocolatey from https://chocolatey.org/api/v2/package/chocolatey/0.10.15.
Extracting C:\Users\N_HASH~1\AppData\Local\Temp\chocolatey\chocInstall\chocolatey.zip to C:\Users\N_HASH~1\AppData\Local\Temp\chocolatey\chocInstall...
Installing chocolatey on this machine
Creating ChocolateyInstall as an environment variable (targeting 'Machine')
  Setting ChocolateyInstall to 'C:\ProgramData\chocolatey'
WARNING: It's very likely you will need to close and reopen your shell
  before you can use choco.
Restricting write permissions to Administrators
We are setting up the Chocolatey package repository.
The packages themselves go to 'C:\ProgramData\chocolatey\lib'
  (i.e. C:\ProgramData\chocolatey\lib\yourPackageName).
A shim file for the command line goes to 'C:\ProgramData\chocolatey\bin'
  and points to an executable in 'C:\ProgramData\chocolatey\lib\yourPackageName'.

Creating Chocolatey folders if they do not already exist.

WARNING: You can safely ignore errors related to missing log files when
  upgrading from a version of Chocolatey less than 0.9.9.
  'Batch file could not be found' is also safe to ignore.
  'The system cannot find the file specified' - also safe.
chocolatey.nupkg file not installed in lib.
 Attempting to locate it from bootstrapper.
PATH environment variable does not have C:\ProgramData\chocolatey\bin in it. Adding...
警告: Not setting tab completion: Profile file does not exist at
'C:\Users\N_hashimoto\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1'.
Chocolatey (choco.exe) is now ready.
You can call choco from anywhere, command line or powershell by typing choco.
Run choco /? for a list of functions.
You may need to shut down and restart powershell and/or consoles
 first prior to using choco.
Ensuring chocolatey commands are on the path
Ensuring chocolatey.nupkg is in the lib folder
```

```console
choco install chocolateygui
```
```
Chocolatey v0.10.15
Installing the following packages:
chocolateygui
By installing you accept licenses for the packages.
Progress: Downloading ChocolateyGUI 0.17.2... 100%
Progress: Downloading chocolatey-core.extension 1.3.5.1... 100%
Progress: Downloading DotNet4.5.2 4.5.2.20140902... 100%

chocolatey-core.extension v1.3.5.1 [Approved]
chocolatey-core.extension package files install completed. Performing other installation steps.
 Installed/updated chocolatey-core extensions.
 The install of chocolatey-core.extension was successful.
  Software installed to 'C:\ProgramData\chocolatey\extensions\chocolatey-core'

DotNet4.5.2 v4.5.2.20140902 [Approved]
dotnet4.5.2 package files install completed. Performing other installation steps.
The package DotNet4.5.2 wants to run 'ChocolateyInstall.ps1'.
Note: If you don't run this script, the installation will fail.
Note: To confirm automatically next time, use '-y' or consider:
choco feature enable -n allowGlobalConfirmation
Do you want to run the script?([Y]es/[A]ll - yes to all/[N]o/[P]rint): Y

Microsoft .Net 4.5.2 Framework is already installed on your machine.
 The install of dotnet4.5.2 was successful.
  Software install location not explicitly set, could be in package or
  default install location if installer.

ChocolateyGUI v0.17.2 [Approved]
chocolateygui package files install completed. Performing other installation steps.
The package ChocolateyGUI wants to run 'chocolateyInstall.ps1'.
Note: If you don't run this script, the installation will fail.
Note: To confirm automatically next time, use '-y' or consider:
choco feature enable -n allowGlobalConfirmation
Do you want to run the script?([Y]es/[A]ll - yes to all/[N]o/[P]rint): Y

Installing ChocolateyGUI...
ChocolateyGUI has been installed.
Added C:\ProgramData\chocolatey\bin\chocolateygui.exe shim pointed to 'c:\program files (x86)\chocolatey gui\chocolateygui.exe'.
Added C:\ProgramData\chocolatey\bin\chocolateyguicli.exe shim pointed to 'c:\program files (x86)\chocolatey gui\chocolateyguicli.exe'.
  chocolateygui may be able to be automatically uninstalled.
 The install of chocolateygui was successful.
  Software installed as 'msi', install location is likely default.

Chocolatey installed 3/3 packages.
 See the log for details (C:\ProgramData\chocolatey\logs\chocolatey.log).
 ```


a5m2 を入れてみた。  
https://kai2nenobu.github.io/my-chocolatey-packages/

```console
PS C:\WINDOWS\system32> choco source add --name kai2nenobu --source https://www.myget.org/F/kai2nenobu
Chocolatey v0.10.15
Added kai2nenobu - https://www.myget.org/F/kai2nenobu (Priority 0)
PS C:\WINDOWS\system32> choco install a5m2
Chocolatey v0.10.15
Installing the following packages:
a5m2
By installing you accept licenses for the packages.
Progress: Downloading a5m2 2.15.1... 100%

a5m2 v2.15.1
a5m2 package files install completed. Performing other installation steps.
The package a5m2 wants to run 'chocolateyInstall.ps1'.
Note: If you don't run this script, the installation will fail.
Note: To confirm automatically next time, use '-y' or consider:
choco feature enable -n allowGlobalConfirmation
Do you want to run the script?([Y]es/[A]ll - yes to all/[N]o/[P]rint): y

Downloading a5m2 64 bit
  from 'https://a5m2.mmatsubara.com/download/a5m2_2.15.1_x64.zip'
Progress: 100% - Completed download of C:\Users\N_hashimoto\AppData\Local\Temp\chocolatey\a5m2\2.15.1\a5m2_2.15.1_x64.zip (15.2 MB).
Download of a5m2_2.15.1_x64.zip (15.2 MB) completed.
Hashes match.
Extracting C:\Users\N_hashimoto\AppData\Local\Temp\chocolatey\a5m2\2.15.1\a5m2_2.15.1_x64.zip to C:\ProgramData\chocolatey\lib\a5m2\a5m2...
C:\ProgramData\chocolatey\lib\a5m2\a5m2
 The install of a5m2 was successful.
  Software installed to 'C:\ProgramData\chocolatey\lib\a5m2\a5m2'

Chocolatey installed 1/1 packages.
 See the log for details (C:\ProgramData\chocolatey\logs\chocolatey.log).
PS C:\WINDOWS\system32>
```
