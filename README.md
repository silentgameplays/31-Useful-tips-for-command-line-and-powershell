# 31 Useful tips for cmd and powershell.
Open CMD Line or Powershell and Run as Administrator

1.Check disk for errors and repair them:
  
  * chkdsk c: /f 

2.Check disk for errors,repair them and recover sectors:
  
  * chkdsk c: /f /r 

3.Check disk for errors and repair them,recover sectors,unmount disk drive if necessary:
  
  * chkdsk c: /f /r /x

4.Check RAM memory for errors and fix them:
  
  * mdsched

5. Creating a directory :

  * mkdir test

6. Changing to directory :

  * cd c:\ test

7. Create a file:
  
  * type nul> test.txt

 NB! Powershell> 
  
  * new-item test.txt

8. Listing contents of the directory
  
  * dir


9. Deleting a file: 
  
  * del test.txt

10. Viewing all the processes running:

  * tasklist

11. Killing a running process:

  * taskkill /PID /T

  * example (TASKKILL /PID 1230 /PID 1241 /PID 1253 /T)

12. View the routes used:
  
  * route PRINT

13. Delete the routes used:
  
  * route /f
	
14. Trace route:
  * tracert -h 100 google.com
  * tracert -j google.com 

15. IP configuration view:
  
  * ipconfig
  * ipconfig /all

16. Release IP configuration:
  * ipconfig /release

17. Renew IP configuration:
  
  * ipconfig /renew
 
18. Flush DNS 
 
  * ipconfig /flushdns

19. View TCP/IP connections
  * netstat
  * netstat -a
  * netstat -s

20.Reset IP Confguration completely on the machine
 
 * netsh int ip reset 

21. Lookup DNS 
  
  * nslookup
 
 or
  
  * nslookup google.com 

22. Check for updates:
  
  * UsoClient StartScan

23. Start downloading the updates:
  
  * UsoClient StartDownload

24. Start installing the downloaded updates:
  
  * UsoClient StartInstall

25. Restart your device after installing the updates:
  
  * UsoClient RestartDevice

26. Check, Download and Install Updates:
  * UsoClient ScanInstallWait

NB! For older Windows versions below Windows 10:

  * wuauclt /detectnow /updatenow

27. Ping some stuff on the internet.
  
  * ping google.com

28. Restart your Windows PC: 
  
  * shutdown /r 

29. Shut Down your Windows PC:
  
  * shutdown /s 

30. Log off your computer. 
  * shutdown /l

31. Abort shutdown before timeout 
  * shutdown /a 

32. Delete Windows Updates Leftovers:
  * dism /online /Cleanup-Image /StartComponentCleanup
33.List and delete Windows restore points:
  * vssadmin list shadows
  * vssadmin delete shadows /Shadow={shadow copy ID}
  * vssadmin delete shadows /all
34. List and remove,hide bloatwareapps via Powershell:
  * DISM /Online /Get-ProvisionedAppxPackages | select-string Packagename
Remove:
  * DISM /Online /Remove-ProvisionedAppxPackage /PackageName:PACKAGENAME
# NB in order to waste less time on Windows 10 bloatware use the debloater script:
* https://github.com/Sycnex/Windows10Debloater
Hide:
  * DISM /Online /Get-ProvisionedAppxPackages | select-string Packagename
35.Installing Net 3.5 Framework offline.Insert a Windows 10 USB or mount an ISO (D:\drive can be an E:\ drive basiclaly whatever letter USB/ISO drive with Windows install is assigned.)
  * dism /online /enable-feature /featurename:NetFX3 /All /Source:D:\sources\sxs /LimitAccess
36.Scan Windows Installed for errors and repair them:
Easy level:
  * sfc /scannow
  * sfc /verifyonly
  * sfc /scannow /f
37.Analog for lsblk bash command for the bloated Windows 10 mess is ofc done jumping through whoola hoops:
  * diskpart
  * list volume
Online:
  * DISM.exe /Online /Cleanup-image /Restorehealth
# NB!Offline requires Windows 10 mounted ISO or USB replace C:\ with E:\D:\ Whatever the Drive letter is:\
  * DISM.exe /Online /Cleanup-Image /RestoreHealth /Source:C:\RepairSource\Windows /LimitAccess
# 38.Installing chocolatey package manager to install actually useful stuff instead of Windows bloat
# Powershell:
  * Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
# CLI:
  * @"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "[System.Net.ServicePointManager]::SecurityProtocol = 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
# 39.Install directx and all net. libraries:
  * choco install directx
  * choco install vcredist-all
# 40. Installing a bunch of stuff and chocolatey via powershell or a cli script(use .bat format and change stuff you need for your purposes in script below):
  * @powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin
# Add/Remove packages.Use chocolatey to 'search' for packages matching a term to get the proper name or head over to https://chocolatey.org/packages
# Recommended optional packages include: libreoffice steam adobeair ffmpeg mpv youtube-dl directx cygwin babun transmission-qt audacity cdrtfe obs syncthing keepass epicgameslauncher obs-studio googlechrome
  * @powershell -NoProfile -ExecutionPolicy Bypass -Command "choco install -y --force --allow-empty-checksums firefox vlc 7zip open-shell jpegview vcredist-all directx onlyoffice goggalaxy steam origin uplay qbittorrent gimp shotcut"
:: reg add "HKEY_CLASSES_ROOT\Directory\shell\Open with MPV" /v icon /t REG_SZ /d "C:\\ProgramData\\chocolatey\\lib\\mpv.install\\tools\\mpv-document.ico" /f
:: reg add "HKCR\Directory\shell\Open with MPV\command" /v @ /t REG_SZ /d "mpv \"%1\"" /f

# NB!FUN BONUS:
Enable Telnet:
  
  * dism /online /Enable-Feature /FeatureName:TelnetClient

Watch an ASCII version of the Star Wars movie:

  * telnet towel.blinkenlights.nl

 
Have fun!!! If you see a command in cmd prompt or bash terminal just use /? near the command. 
#gimalaji_blake
