

# What's this?

This is a modification of the gdidrop program, that converts Dreamcast Redump Images (bin/cue) to GDI Images (bin/raw/gdi), and which was originally developed by @[feitys-tan](https://github.com/feyris-tan): https://github.com/feyris-tan/gdidrop

⚠️ This program is not intended to convert **Redump**'s bin/cue of unlicensed CD-ROM images (e.g. 'Dux', 'Hermes', 'Irides', 'Pier Solar', 'Sturmwind', etc). You should use **Redump2CDI** to do that: https://dreamcast.wiki/Redump2CDI

# What changes I made to the program?

 - Added basic support for command-line usage. Very helpful to
   automate bulk file conversions.
 - Added basic error-handling features.
 - Now the program will preserve original filenames instead of
   "track1.bin", "track2.raw", etc.
 - Added a informative message box that will be shown when the
   conversion operation is completed.
 - Changed the window startup location to the center of the screen.
 - Added an icon for the compiled executable.
 - Source-code updated to .NET 4.8.

# Will I do more changes to the program?

Probably not. The modifications I made were made out of personal need to automate the conversion of thousands of bin/cue discs from Redump. So unless a new need arises or there is some critical error that I haven't caught, I won't make any more changes. 

Note that C# is not my main language, so the modifications I made were with the minimum necessary effort, making sure everything worked as expected, but implemented in a dirty (ugly) and fastest possible way.

# How to use it?
- Either download a release here from Github and run the exe file.
- Or: Clone this repository, open it in Visual Stdio 2017 and just hit run - no dependencies except System.Windows.Forms and mscorlib

Once the program starts, just take a cue File and drag & drop it onto the window. Kinda like oggdropXPd or lamedropXPd.
To exit the program, just right click the window.

# Command-line usage

Simply like this:

    gdidrop.exe "path_to_cue_file"

The program will generate the .gdi file and the track files in the same directory where the cue file is.

The program will return one of these exit codes:

| Exit Code  | Meaning  |
|---|---|
| 0  | Conversion was successful  |
| 1  | Cue file not found  | 
|  2 | Unexpected error  |  

# Additional Information

This program will preserve the source track filenames and add a suffix to the end of the file name. 

For example, having this folder structure for **Seaman** game from **Redump**:

    📁Seaman (USA)
      📄 Seaman (USA) (Track 1).bin 
      📄 Seaman (USA) (Track 2).bin 
      📄 Seaman (USA) (Track 3).bin 
      💿 Seaman (USA).cue

**gdidrop** will generate output files with these names:

    📁Seaman (USA)
      📄 Seaman (USA) (Track 1) [gdidrop].bin
      📄 Seaman (USA) (Track 2) [gdidrop].raw
      📄 Seaman (USA) (Track 3) [gdidrop].bin
      💿 Seaman (USA).gdi

And the content of the generated .gdi file will look like this:

    3
    1 0 4 2352 "Seaman (USA) (Track 1) [gdidrop].bin" 0
    2 1744 0 2352 "Seaman (USA) (Track 2) [gdidrop].raw" 0
    3 45000 4 2352 "Seaman (USA) (Track 3) [gdidrop].bin" 0

This file name formatting will work as expected (at least for all the converted GDI games that I tried) with DEMUL, Flycast and redream emulators, but it may be incompatible with other software.

Note: I decided to add the '[gdidrop]' suffix to the file names for two reasons, the first is to place an indicator to easy identify disc images generated with **gdidrop**, which will be of help to keep track the cause of the problem if in the future a converted GDI image presents any issue in a emulator, and the second reason is to avoid file name collisions since the generated output files shares the .bin file extension.

# Legal stuff
This software contains CueSharp licensed under the 2-clause BSD License found here: [here](https://wyday.com/bsd-license.php)

The character animation playing while the program is busy is taken from easyRPG's RTP Replacement found [here](https://github.com/EasyRPG/RTP) 
This software itself it license under 2-clause BSD as well. I'm not good with legal stuff, but I believe these licenses should be compatible. If you can help me with this stuff, please message me.
