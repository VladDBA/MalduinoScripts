#About  
My repository with scripts for Maltronics's Malduino keystroke injection tool.  
Written and tested on Malduino Elite.  
https://maltronics.com/collections/malduinos


#Scripts  
1. [SimpleWallpaperChanger](Scripts/SimpleWallpaperChanger)  
   * Opens the run menu and calls Internet Explorer (the browser can be changed by replacing iexplore with firefox or chrome in the script) passing a link to an image on imgur (link can be replaced with whatever image you need/want)  
   * waits 2.6 seconds for the image to load (delay may vary depending on machine and connection speed)  
   * saves the image as hack1.jpg to C:\Users\CurrentUser\Pictures  
   * closes Internet Explorer  
   * opens hack1.jpg in Paint
   * opens Paint's file menu and sets hack1.jpg as the background image 
   * Closes Paint and displays the Desktop  
   * total runtime (based on sum(delay)) - 8.26 seconds 
