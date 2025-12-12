# Welcome!
Welcome to the Guitar Hero III PS2 Debug Menu Guide! This guide will teach you how to enable the debug menu on an unmodded copy of the game. 

# Step 0 - Requirements

 PCSX2 - Recommended for playtesting, but if you want to test on real hardware or your PC sucks you can skip this, however if you're on real hardware your console needs to be modded in order to play the modded ISO. I also don't recommend you skip playtesting, as shipping an ISO without even knowing if it works is lame and can waste another user's time. At least ask somebody you know to test it for you if you can't test it yourself.

 Honeycomb-GUI - Required for modifying the game and compiling songs

 7-zip or WinRAR - Used to extract the ISO

 UltraISO - Used to replace the unmodded ISO's files, you can use another tool as long as it edits ISO properly

 Step 1 - Extract your game ISO
Go to the directory where your game ISO is in, right click it, then extract it using 7-zip or WinRAR.

# Step 2 - Extract your WAD
Go to where you have extracted your ISO to and you will see a WAD file. This file contains another file that contains the g#ame's code and will need to be extracted. 
To extract your WAD, open Honeycomb-GUI, then click PS2 Archive Tools, then select your WAD file and click extract. Wait until it's done (Honeycomb-GUI will tell you when it's done in the main program window with the Compile a Song and PS2 Archive Tools buttons) and that's it! Your WAD will be extracted to a folder named WAD Extract.

# Step 3 - Extracting the QB file
Inside WAD Extract, there is a folder named pak, and inside it there is two files: a **qb.pak.ps2** and a **qb.pab.ps2**.
Open Honeycomb-GUI, then click PAK tools, then on the Extract tab select the qb.pak.ps2 file inside the pak folder inside WAD Extract, then click extract. 

# Step 4 - Modifying the QB file
After Honeycomb-GUI finishes extracting, there will be a new folder named **qb**.
Enter this folder, then go to scripts, guitar, and double click guitar.q file. 
Then, on your text editing tool, search for "enable_button_cheats" until you see a structure like this:

	if NOT notcd
		change \{enable_button_cheats = 0}
	endif

This basically tells the game that if your copy is retail, disable all debugging features, and we don't want that! So all you really need to do here is to just change the 0 to 1 and save your changes. Changing this 0 to 1 modifies this script so that now if our game is retail, it enables debugging features.

# Step 5 - Recompile your QB file.
On the PAK tools window you opened in Honeycomb-GUI, change to the Compile tab.
Select the qb folder inside the pak folder inside WAD Extract, then click the PS2 option in the console select buttons, then select GH3 on the Select Game box, the check Split PAB, then click Compile. 

# Step 6 - Recompile your WAD
After Honeycomb-GUI finishes compiling your PAK, go back to PS2 Archive Tools, then switch to the Compile tab, select the WAD Extract folder, uncheck the checkbox next to the Compile button and then click Compile.

# Step 11 - Modify your game ISO
Open your game's ISO using UltraISO. You will see several files and folders, but we're only interested in the WAD files.
Next to the WAD Extract folder, there should be a new folder named WAD Compile. Drag all the files from the WAD Compile folder to your ISO's filesystem, replace all files when asked, click the diskette icon to save the changes you've made to the ISO, and wait for it to finish saving the changes.

# Step 12 - Playtest
Now it's time for the fun part! Open the ISO you've modified on PCSX2 (or burn it to a disc/drag it to whatever place you use to load ISOS if you're on real hardware, do note your console needs to be modded to boot any burned games or boot ISOs), wait for the slow ass thing to load, and you should see that there is now a new menu named Debug Menu. If you do see it, congratulations! You've succesfully enabled the Debug Menu on your ISO.
