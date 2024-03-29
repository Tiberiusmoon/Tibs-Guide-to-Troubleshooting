# ***Trouble shooting 101 (∩｀-´)⊃━☆ﾟ.*･｡ﾟ***


There are many issues to trouble shoot on Windows 10, knowing where to look and how to deal with them can be a painless experience.
Even if you can't find a fix, providing information to the Developer of the software or game can help them provide a fix by update.


## ***1.Information gathering***  
First we will learn how to gather useful information Developers can use to learn about the issues your having with their software.  

***DxDiag:***
- Hold the Win key and press the R key, then type: ```dxdiag``` and hit enter.  
- If you have a button at the bottom that says "Run 64-bit DxDiag" click that button, if not then skip this bit.  
- Once the green bar at the bottom of the window has loaded click the "Save All Information" and save the .txt file.  
- This .txt file is something you share with the Dev's.  
Some games/software apps are made to generate their own crash logs which you can also share with the Dev's.  

***Windows Event Viewer:***
This type of information can be useful to yourself and Dev's alike!  
- Right click your start button and select Event Viewer.  
- Now click "Event Viewer (Local)" once the middle panel loads you can resize the window to make the "Summary of Administrative Events" panel  visible.  
- You will see a list of event types with + boxes next to them, click them to expand the list. (You will want to focus on "Critical", "Error" and "Warning")  
- This is where you can see some of the logs that are made when there are issues with the system, not all of them are issues that persist some are just notification's.  
Say if you were to turn off the PC from the wall socket without letting the system shut down properly, you would get a Event log (Event ID: 41, Source: Kernel-Power) this is a notification log that the system has turned without shutting down.  

- To the right you can see roughly when a event happened, in the Last hour, 24 Hours and 7 Days.  
- If you had a issue with the PC in the last hour you can view the logs within the hour to see what logs showed.(a number is shown by how many logs were posted within that time)  
- Once you double click on a log you can view more details, if you know the exact time the issue with the PC happened you can check the time of the log in the top panel.  


## 2.***Searching for a fix***
Please make sure you have read the Event Viewer guide or you understand how the Event Viewer Works.  

- When you have a log or a few logs that are showing for your issue open google and type in the Event ID and source like so: >Event ID: 41 Kernel-Power  
- You will find a few results for the issue you have, explore the sites and see what people have tried to fixing the issue.  
- Once you have found a fix try the fix on your system and see if that resolves the issue by trying to replicate the issue.  
- If your having  trouble finding a log you can quote the description text in the general tab to refine your search.  


## 3.***Basic fixes***  
!! These fixes are for basic issues on face value and may not work, you may have underlying issues. !!

***Windows Update not working or OS issues:***
- Hold the Win key and hit R, type cmd then hold Ctrl and Shift together and hit enter. (opening command prompt in Admin mode)  
- Type: ```dism.exe /Online /Cleanup-image /Restorehealth``` Hit enter.  
- Once done type: ```sfc /scannow``` and hit enter again.  

> If these scans fail you may have a virus issue, if your current Antivirus does not detect it you can use this: [Malwarebytes antirootkit](https://www.malwarebytes.com/antirootkit/) or use the regular version of [Malwarebytes](https://www.malwarebytes.com/premium/), Once the virus has been removed redo the commands above to repair the damage the virus did to your system.  

***Unusual Display issues:***
- In your BIOS settings disable the "Fast boot" option and save. (you can re-enable this after the driver install)
- Download and extract [DDU](https://www.guru3d.com/files-details/display-driver-uninstaller-download.html) (download link is at the bottom.)  
- Then download the latest version of your GPU Driver from either [Nvidia](https://www.nvidia.com/Download/index.aspx?lang=en-us) or [AMD/Radeon](https://www.amd.com/en/support)
- Press the win key and type "advanced system settings" and hit enter, select the Hardware tab then click "Device Installation Settings".
- Select no and save changes.
- Open the menu to restart your PC and hold shift while clicking restart, a troubleshoot option will be made avaliable to you.
- Once clicked go to: Advanced options > Startup settings > restart.
- Now that you have restarted press F5 to select option 5 in the list. (safe mode with networking)
- Open the DDU folder and run the DDU .exe.  
- Select the option's relevant to your GPU and click "Clean and Restart".  
- Once done install your GPU driver.   

>Display/Gaming related GPU issues may occur as certain files accumulate and potentially conflict.  

***Network issues:***
- Hold the Win key and hit R, type cmd then hold Ctrl and Shift together and hit enter. (opening command prompt in Admin mode)  
- Type ```ipconfig /registerdns``` and press Enter.  
- Type ```ipconfig /release``` and press Enter.  
- Type ```ipconfig /renew``` and press Enter.  
- Type ```netsh winsock reset``` and press Enter.  
- Restart the PC as followed.  

***Slower than usual network speeds:***
- Check that no other programs are updating like steam, Windows update, Uplay etc and that no one else in your house is using all the bandwidth in the house.  
- Go [here](https://www.speedtest.net/) and do a speed test then take notes of the results.  
- Now go to where you keep your router then turn it off and unplug it from the wall for 10 minutes, then plug it back int and turn it on.  

>This is known as power cycling your router; If you still have issues you may need to update your router firmware, the router manual will tell you how.  
    
Thats about it, to a certain extent reinstalling Windows is the answer but it takes too much time.  

o >o/' *waves*  

More useful guides:  
[Antivirus Combat and Repair](https://tiberiusmoon.github.io/Antivirus-Combat-and-Repair/)  
[Tibs Guide to Windows 10](https://tiberiusmoon.github.io/Tibs-Guide-to-Windows-10/)
