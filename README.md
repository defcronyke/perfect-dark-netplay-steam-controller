# Perfect Dark NetPlay with Steam Controller
A working config for playing emulated N64 Perfect Dark on Kaillera (netplay) with steam controllers on Windows.  

This document was created because there were problems with every other set of instructions I found about Perfect Dark netplay. They either had graphics or input bugs, making it unplayable, and I had to 
figure this out on my own after a long night/morning of trial-and-error.  

1. Download [Mupen64++](http://www.emulator-zone.com/doc.php/n64/mupen64plusplus.html) and extract it somewhere.

2. Install [Project64 1.6](http://www.emulator-zone.com/doc.php/n64/project64.html) (yes it needs to be version 1.6 even though it's old).

3. Browse to Project64 1.6 installation directory and go inside the Plugin folder. Copy Jabo_Direct3D6.dll from there into your Mupen64++ plugin folder.

4. Download [Mupen64k](https://github.com/PhoenixInteractiveNL/emuDownloadCenter/wiki/Emulator-mupen64k) and extract it somewhere.

5. Browse to the Mupen64k plugin directory and copy "NRage Input 2.2.2 Beta.dll" to your Mupen64++ plugin folder.

6. Open Steam and configure your Steam controller as a Gamepad.

7. Add Mupen64++ to Steam as a non-Steam game.

8. Open mupen64pp from your Steam library.

9. Go to Options -> Settings -> Plugins:  
  For Video Plugin, choose: Jabo's Direct3D6 1.5.2  
  For Input Plugin, choose: N-Rage's Direct-Input8 V2 2.2 beta  

10. Under Video Plugin, click Configure. Set Windowed Resolution to 1280x960 (or your preferred resolution). Click OK to go back.

11. Under Input Plugin, click Configure. Make sure the Plugged and XInput boxes under all the controller tabs are checked. Click Save to go back.

12. Go to the Directories tab and add a directory which contains the Perfect Dark ROM. Click OK to go to the main Mupen64++ window.

13. Download [Kaillera Server](http://www.kaillera.com/download.php), and extract it somewhere.

14. Open the kaillerasrv.conf file in a text editor. Change the ServerName, Location, Public (set to 0 for LAN-only play), and anything else you want to customize.

15. Go to Windows Defender settings and disable all the firewalls. Adding exceptions isn't good enough for some reason.

16. Open a command prompt or powershell, go to the place where you extracted Kaillera Server, and run the command kaillerasrv.exe.

17. In Mupen64++, click Utilities -> KailleraClient (NetPlay).

18. In the Kaillera client window that just opened, click Add. Put a name for your server, and set the IP to localhost:27888, click OK and it will add your server to the bottom of the server list.

19. Enter your desired nickname, quit message, and connection setting (choose LAN if you're playing on LAN, for example).

20. Double-click your server in the list. It should connect and bring you into the server's lobby.

21. Click Create, and choose your Perfect Dark ROM from the menu.

22. At this point it's a good idea to test your setup with a 1-player game running on your Kaillera server, so click Start, and the game should start. Make sure your controller works and the graphics look okay.

23. Exit your game and get some friends to connect to your Kaillera server IP and port (you can get your LAN IP from the Windows Network Adapter settings). If they are connecting to you over the internet, make 
sure to fill in your public IP address in kaillerasrv.conf IP section, which you can get by Googling the term [IP Address](https://www.google.com/search?q=ip+address). And you'll have to set up port forwarding 
on your router to forward your Kaillera port to your internal IP of the computer you're running the server on.

24. Wait for your friends to join the server lobby, create a Perfect Dark game, get them to join it, then click Start to play.  
  
That was rough! But it should work now. If you have any issues, make sure all players have exactly the same plugins and settings selected in their Mupen64++. And sometimes you just have to reboot Windows and try again.
I've also noticed that Mupen64++ sometimes doesn't like to exit cleanly, so if it crashes or you force quit, just make sure your settings are correct next time. They usually get saved, but not always.
