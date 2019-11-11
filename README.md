# 27 Useful tips for cmd and powershell.
Open CMD Line or Powershell and Run as Administrator

1. Creating a directory :

 * mkdir test

2. Changing to directory :

 * cd test

3. Create a file:
 * type nul> test.txt

 NB! Powershell> 
 * new-item test.txt

4. Listing contents of the directory
 * dir


5. Deleting a file: 
 * del test.txt

6.Viewing all the processes running:
 * tasklist

7.Killing a running process:
* taskkill /PID /T
example (TASKKILL /PID 1230 /PID 1241 /PID 1253 /T)

8.View the routes used:
  * route PRINT

9.Delete the routes used:
  * route /f
	
10.Trace route:
  * tracert -h 100 google.com
	* tracert -j google.com 

11. IP configuration view:
  * ipconfig

12.Release IP configuration:
  * ipconfig /release

13. Renew IP configuration:
  * ipconfig /renew
 
14. Flush DNS 
  * ipconfig /flushdns
15. View TCP/IP connections
  * netstat
  * netstat -a
  * netstat -s
CTRL+C to quit
16.Reset IP Confguration completely on the machine
netsh int ip reset 

17. Lookup DNS 
  * nslookup
 or
  * nslookup google.com 

18. Check for updates:
  * UsoClient StartScan

19.start downloading the updates:
  * UsoClient StartDownload

20.Start installing the downloaded updates:
  * UsoClient StartInstall

21.Restart your device after installing the updates:
  * UsoClient RestartDevice

22.Check, Download and Install Updates:
  * UsoClient ScanInstallWait

NB! For older Windows versions below Windows 10:

  * wuauclt /detectnow /updatenow

23.Ping some stuff on the internet.
  * ping google.com

24.Restart your Windows PC: 
  * shutdown /r 

25.Shut Down your Windows PC:
  * shutdown /s 

26.Log off your computer. 
  * shutdown /l

27.Abort shutdown before timeout 
  * shutdown /a 
Have fun and a tip if you see a command in cmd prompt or bash terminal just use /? near the command. 
#gimalaji_blake
