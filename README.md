# 31 Useful tips for cmd and powershell.
Open CMD Line or Powershell and Run as Administrator

1.Check disk for errors and repair them:
 * chkdsk c: /f 

2.Check disk for errors,repair them and recover sectors:
 * chdsk c: /f /r 

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
example (TASKKILL /PID 1230 /PID 1241 /PID 1253 /T)

12. View the routes used:
  * route PRINT

13. Delete the routes used:
  * route /f
	
14. Trace route:
  * tracert -h 100 google.com
	* tracert -j google.com 

15. IP configuration view:
  * ipconfig

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
netsh int ip reset 

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


Have fun!!! If you see a command in cmd prompt or bash terminal just use /? near the command. 
#gimalaji_blake
