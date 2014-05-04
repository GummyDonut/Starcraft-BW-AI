==================================================================================
0. PREREQUISITES
==================================================================================

- You need the StarCraft: Brood War game, ver. 1.16.1
- This package is prepared for the use with Eclipse IDE for JAVA developement.

==================================================================================
I. INSTALLATION
==================================================================================

1. Run "install.bat". This should execute the installation script, that will do 
   everything necessary. If the script doesn't work, please read section IV (part A). 
   (There should be the "BWAPI" shortcut on your Desktop now. If there isn't one,
   script didn't work.)

2. (optional) Modify the StarCraft\bwapi-data\bwapi.ini file:
   - Set the "race" setting to the race of your bot (by default it's Terran).
   - Change the "enemy_race" if you want to play against different race.
   - You can change the "auto_menu" setting to OFF or LAN if you don't want to 
     play against native SC computer player.
   - Change the "map" setting in order to load specific maps (by default it's 
     random map).
3. Now we will open our bot in Eclipse...

==================================================================================
II. COMPILING THE BOT
==================================================================================

These instructions apply, if you are using the Eclipse IDE.

1. Open Eclipse. 
2. File > Import > General > Existing Projects into Workspace (The "Copy projects
   into workspace" option should be UNchecked)
3. Select root directory > (navigate to "jnibwapi" folder)
   The "JniBot" project should be selected. Press "Finish".
4. In Package Explorer open JniBot > src > javabot > JavaBot.java 
   This is the file you should edit (your bot).

==================================================================================
III. RUNNING THE BOT
==================================================================================

- When you have the JniBot project open in Eclipse, you can 
  simply click Run > Run (or press Ctrl+F11). 
- In the console below, you should see following 2 lines:

  Bridge: BWAPI Client launched!!!
  Bridge: Connecting...

- If you get the "Native code library failed to load" error, refer to section IV-B.
- This means, that your bot is running, and waiting for a StarCraft game 
  to connect to.
- Now run the ChaosLauncher (click the "BWAPI" shortcut on
  your Desktop), and make sure that 2 plugins, "BWAPI Injector (1.16.1) RELEASE"
  and "W-MODE 1.02", are enabled.
- Click "Start" and the StarCraft single player game should start. The bot will 
  connect to it and start issuing orders to your units. 

==================================================================================
IV. TROUBLESHOOTING
==================================================================================

A. INSTALLATION SCRIPT BROKEN:
==============================

On some machines, the installation script doesn't work. If that's your case, 
you need to do the following steps to install manually:

1. Go to "BWAPI_3.7.4" folder. You will find 3 important directories there: 
   "WINDOWS", "Starcraft" and "Chaoslauncher"
2. Copy all the files from the "WINDOWS" directory into your Windows installation
   location (e.g. C:\Windows\) or to any other location from your system's PATH 
   variable.
3. Copy everything from "Starcraft" folder into the location of your StarCraft 
   installation.
4. Create a desktop shortcut to the "Chaoslauncher\Chaoslauncher.exe" file and
   run it.
5. Sometimes, you might be asked to specify the path to your Starcraft.exe in 
   ChaosLauncher's settings. In that case  click the "Settings" tab set it in the
   "InstallPath" field. Click "OK" and "Ja" and ChaosLauncher will restart.


B. ERROR: "Native library failed to load" when RUNNING the bot: 
===============================================================

If you get the "Native code library failed to load" error when running your bot
in Eclipse, you are probably trying to run it with 64bit JRE (which is not possible
right now). You need to tell Eclipse to use some 32bit JRE (you may need to install
it first). 
You can do it in: Run > Run Configurations > "JRE" tab > Installed JREs

C. LAG at the BEGINNING OF MATCH:
=================================

If the game freezes for one or two minutes at the beginning of the match, it is 
probably because you're running some new map for the first time. The bot needs 
some time to analyze the map file. This should only happen once on every map.

D. ERROR: "Failed to load AI module NULL" in SC MATCH:
======================================================

This means, that your bot was unable to connect to the SC game. First check if it is
really running. Then try starting the game again (this sometimes happens for no 
apparent reason). 
Finally (if you're running Windows 7) check your admin privileges: 
- Chaoslauncher.exe should NOT have admin privileges (you can also uncheck the
  "Warn about missing adminprivileges" option in the Settings tab.
- JRE should also NOT have admin privileges.
If nothing else helps, you may try to temporarily disable your Firewall.


**Peter Edit- Note you actually run both eclipse and chaoslauncher in admin mode




