#About  
My repository with scripts for Maltronics's Malduino keystroke injection tool.  
Written and tested on the [Maltronics](https://maltronics.com/collections/malduinos) Malduino Elite, but most (if not all) of them should also be compatible with [Hak5's](https://shop.hak5.org/) Rubber Ducky   



#Scripts  
1. [Simple Wallpaper Changer](Scripts/SimpleWallpaperChanger)  
   * Opens the run menu and calls Internet Explorer (the browser can be changed by replacing iexplore with firefox or chrome in the script) passing a link to an image on imgur (link can be replaced with whatever image you need/want)  
   * waits 2.6 seconds for the image to load (delay may vary depending on machine and connection speed)  
   * saves the image as 1hack.jpg to C:\Users\CurrentUser\Pictures  
   * closes Internet Explorer  
   * opens hack1.jpg in Paint
   * opens Paint's file menu and sets hack1.jpg as the background image 
   * Closes Paint and displays the Desktop  
   * total runtime (based on sum(delay)) - 8.26 seconds 
 
2. [Simple Wallpaper Changer via PowerShell](Scripts/SimpleWallpaperChangerPS)  
 Requirements:  
   * Access to PowerShell  
   * Adjust the delays as needed to match your target machine  
 Workflow:  
   * Opens PowerShell and chains commands to download the image from the URL as $Home\Pictures\1hack.jpg, open the image in Paint, and exit PowerShell  
   * Executes the command and then waits 1.6 seconds (sufficient time for PowerShell to complete the commands and for Pait to open the image)  
   * Once in Paint, it sets the image as background via the file menu and then exits Paint  
   * Calls again PowerShell to delete $Home\Pictures\1hack.jpg and exit  
   * Displays the Desktop

3. [Exfiltrate Firefox Profile As Image To Network Share](Scripts/Exfil/ExfilFirefoxProfileAsImageToNetworkShare)  
 Requirements:  
   * A network shared directory where you are able to write without having to type in credentials  
   * Built for and tested on Windows 10
   * Replace ImageUrlHere with the URL of the jpg you want to use  
   * Replace NetworkShareHere with your network shared directory  
   * Adjust the delays as needed to match your target machine  
  Workflow:  
   * Opens Firefox and navigates to about:profiles from where it opens the location of the default profile  
   * Closes the default profile directory after copying the path to clipboard  
   * Starts PowerShell, kills firefox using taskkill  
   * And then chains the commands to download the image as $Home\Pictures\wall032.jpg, zip the default profile as $Home\Music\FFPrfl.zip, binary copy wall032.jpg and FFPrfl.zip into $Home\Music\wall033.jpg, move it to the network shared directory, remove the leftover files (wall032.jpg, FFPrfl.zip), and exit PowerShell  
   * Executes the command and minimizes PowerShell
