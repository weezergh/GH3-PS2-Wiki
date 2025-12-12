Welcome to the Guitar Hero III for PS2 Customs Songs guide! This guide will help you install custom songs on an unmodded copy of Guitar Hero III for PS2.

# Song Limit
Since Guitar Hero 3 only has 70 songs (not counting tutorial, boss battles and other songs that don't appear in quickplay), that's your Song Limit. If you want more songs, you'll need two or more ISO's depending on your setlist's size.

# Step 0 - Requirements

**PCSX2** - Recommended for playtesting, but if you want to test on real hardware or your PC sucks you can skip this, however if you're on real hardware your console needs to be modded in order to play the modded ISO. I also don't recommend you skip playtesting, as shipping an ISO without even knowing if it works is lame and can waste another user's time. At least ask somebody you know to test it for you if you can't test it yourself.

**Honeycomb-GUI** - Required for modifying the game and compiling songs

**7-zip or WinRAR** - Used to extract the ISO

**UltraISO** - Used to replace the unmodded ISO's files, you can use another tool as long as it edits ISO properly

**ffmpeg** - Honeycomb-GUI needs this to convert audio.

# Step 1 - Get the chart you want to convert
Download the chart you want to convert (if you're downloading from chorus select zip) and extract it to a folder.

# Step 2 - Install ffmpeg to the Honeycomb-GUI folder.
Extract the ffmpeg zip, then copy the three exe files inside bin to the folder where Honeycomb-GUI's exe is in. Make sure to not download the source code, but the program binaries.

# Step 3 - Compile the song
Open Honeycomb-GUI. Click Compile a Song, then click the Compile tab and select PS2. If the PS2 option is not clickable, click Tools, then Settings, then click Enable GH3+ settings for PC, close the Compile a Song window and open it again, then go back into Settings and uncheck the box you checked.
After selecting PS2 in the Compile tab, go back to the tab you were before and select Import data from Clone Hero folder, then select your chart folder. On the "Checksum" field, erase all text on it and replace it with one of the checksums listed here: https://github.com/weezergh/GH3-PS2-Wiki/blob/main/all_valid_checksums.txt. Remember what checksum you used, because if you want to import more songs later, two songs cannot have the same checksum.
After doing that, click the red Compile All button. It will ask you where you want to save your .ghproj file, so save it to the directory you'd like (this file won't be needed after the compile process finishes so you can delete it after the compile finishes), and after selecting your directory/path,  wait for the compile process to finish.
If you're getting an error during audio compilation with something along the lines of "ffmpeg.exe" not found, you haven't installed ffmpeg correctly. If it's an error relating to path1, make sure the first box to the left of Compile Song PAK isn't blank and has a valid directory/path.

# Step 4 - Extract your game ISO
Go to the directory where your game ISO is in, right click it, then extract it using 7-zip or WinRAR.

# Step 5 - Extract your WAD
Go to where you have extracted your ISO to and you will see a WAD file. This file contains another file that contains the game's code and will need to be extracted. 
To extract your WAD, open Honeycomb-GUI, then click PS2 Archive Tools, then select your WAD file and click extract. Wait until it's done (Honeycomb-GUI will tell you when it's done in the main program window with the Compile a Song and PS2 Archive Tools buttons) and that's it! Your WAD will be extracted to a folder named WAD Extract.

# Step 6 - Modifying the WAD file
Remember the song we compiled 3 steps earlier? Honeycomb-GUI generates a folder named PS2 Compile on your chart folder after it finishes compilation, which we will need right now. 
Go to your chart folder and you should see the PS2 Compile folder. Inside it, there will be a folder named WAD, enter it, then drag the folders inside the WAD folder to WAD Extract. When Windows tell you the file already exists, click **Replace all files in the destination.**

# Step 7 - Extracting the QB file
(ignore this if you've edited a tutorial song, I do not recommend editing tutorial songs as it could break a lot of stuff)
Inside WAD Extract, there is a folder named pak, and inside it there is two files: a **qb.pak.ps2** and a **qb.pab.ps2**.
Open Honeycomb-GUI, then click PAK tools, then on the Extract tab select the qb.pak.ps2 file inside the pak folder inside WAD Extract, then click extract. 

# Step 8 - Modifying the QB file
(ignore this if you've edited a tutorial song, I do not recommend editing tutorial songs as it could break a lot of stuff)
After Honeycomb-GUI finishes extracting, there will be a new folder named **qb**.
Enter this folder, then go to scripts, guitar, then scroll all the way to the bottom and double click the songlist.q file. 
Then, search for the checksum you edited until you see a structure like this:

```
anarchyintheuk = {
		checksum = anarchyintheuk
		name = 'anarchyintheuk'
		title = 'Anarchy in the U.K.'
		artist = 'The Sex Pistols'
		year = ', 2007'
		artist_text = $artist_text_by
		original_artist = 1
		version = gh3
		leaderboard = 1
		gem_offset = 0
		input_offset = 0
		singer = male
		keyboard = false
		countoff = 'sticks_huge'
		band_playback_volume = 0.0
		guitar_playback_volume = 2.25
		rhythm_track = 0
	}
```


Do not edit the checksum, name or any other values, only edit the title, artist, and year values, and don't remove the space and comma from the year value. 
Make sure to not accidentally delete any lines, as that could corrupt the structure and lead to your custom song being unplayable. After you've edited those, save the changes.

# Step 9 - Recompile your QB file.
(ignore this if you've edited a tutorial song, I do not recommend editing tutorial songs as it could break a lot of stuff)
On the PAK tools window you opened in Honeycomb-GUI, change to the Compile tab.
Select the qb folder inside the pak folder inside WAD Extract, then click the PS2 option in the console select buttons, the click Split PAB, then select GH3 on the Select Game box, then click Compile. 

# Step 10 - Recompile your WAD
Oh wow, ten steps. Anyways, after Honeycomb-GUI finishes compiling your PAK, go back to PS2 Archive Tools, then switch to the Compile tab, select the WAD Extract folder, uncheck the checkbox next to the Compile button and then click Compile.

# Step 11 - Modify your game ISO
Open your game's ISO using UltraISO. You will see several files and folders, but we're only interested in the WAD files and the MUSIC folder. 
Drag the MUSIC folder from your chart's PS2 Compile folder to the UltraISO window's ISO filesystem, and replace all files when asked. 
Then, next to the WAD Extract folder, there should be a new folder named WAD Compile. Drag all the files from the WAD Compile folder to your ISO's filesystem, replace all files when asked, click the diskette icon to save the changes you've made to the ISO, and wait for it to finish saving the changes.

# Step 12 - Playtest
Now it's time for the fun part! Open the ISO you've modified on PCSX2 (or burn it to a disc/drag it to whatever place you use to load ISOS if you're on real hardware, do note your console needs to be modded to boot any burned games or boot ISOs), wait for the slow ass thing to load, head over to the Options menu, then go to to the Cheats menu and do the unlock all songs cheat, which is YO, RB, RO, GB, RY, YO, RY, RB, GY, GY, YB, YB, YO, YO, YB, Y, R, RY, R, Y, O by the way, G = Green, R = Red, Y = Yellow, B = Blue, O = Orange (keep in mind you need to strum everything), then head over to Quickplay and look for your custom song in the Setlist or Bonus tabs (do note that if you edited a tutorial song or  calibration song you need to look for it using the debug menu) and it should appear and work fine!


# Conclusion 
Now you might be thinking this right now: "Wow, all this work for ONE song?" and I have the answer to your question: Yes, that's what you get for being a broke bitch (/j). It's important to note that you don't need to reextract your QB and WAD files for every single time you want to add a custom.
