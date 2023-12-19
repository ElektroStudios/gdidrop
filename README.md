
# What's this?

This is a modification of the gdidrop program, which converts Dreamcast Redump Images (bin/cue) to GDI Images (bin/raw/gdi), originally developed by @[feitys-tan](https://github.com/feyris-tan):

https://github.com/feyris-tan/gdidrop

# What changes I made to the program?

 - Added basic support for command-line usage. Very helpful to
   automate batch-conversions and catch the exit code.
 - Added basic error-handling features.
 - Now the conversion algorithm will use original filenames instead of
   "track1.bin", "track2.raw", etc.
 - Added a informative message box that will be shown when the
   conversion operation is completed.
 - Changed the window startup location to the center of the screen.
 - Added an icon for the compiled executable.
 - Source-code updated to .NET 4.8.

# Will I do more changes to the program?

Probably not. The modifications I made were made out of personal need to automate the conversion of thousands of bin/cue discs from Redump. So unless a new need arises or there is some critical error that I haven't caught, I won't make any more changes. 

Note that C# is not my main language, so the modifications I made were with the minimum necessary effort, making sure everything worked as expected, but implemented in a dirty and fastest possible way.

# How to use it?
- Either download a release here from Github and run the exe file.
- Or: Clone this repository, open it in Visual Stdio 2017 and just hit run - no dependencies except System.Windows.Forms and mscorlib

Once the program starts, just take a cue File and drag & drop it onto the window. Kinda like oggdropXPd or lamedropXPd.
To exit the program, just right click the window.

# Command-line usage

Simply like this:

    gdidrop.exe "path_to_cue_file"

The program will generate the .gdi file and the track files in the same directory where the cue file is.

The program will return these exit codes:

| Exit Code  | Meaning  |
|---|---|
| 0  | Conversion was successful  |
| 1  | Cue file not found  | 
|  2 | Unexpected error  |  

# Legal stuff
This software contains CueSharp licensed under the 2-clause BSD License found here: [here](https://wyday.com/bsd-license.php)

The character animation playing while the program is busy is taken from easyRPG's RTP Replacement found [here](https://github.com/EasyRPG/RTP) 
This software itself it license under 2-clause BSD as well. I'm not good with legal stuff, but I believe these licenses should be compatible. If you can help me with this stuff, please message me.
