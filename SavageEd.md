# SavageEd Documentation

## Quick Start

All you need to run SavageEd is the file SavageEd.exe
	
After the first run, the program will create a settings file in the parent folder called "SavageEd.ini"
If you wish to use your "%USERPROFILE%\config" folder instead,
create a config folder (if one doesn't already exist) in your user profile
folder, and move a SavageEd.ini file there.
	
eg: "c:\user\mako\config\SavageEd.ini"
	
	If there is a SavageEd.ini file in the SavageEd parent folder, SavageEd
	will always prioritise using that ini file.
	If at any time the SavageEd.ini file gets corrupted (by bug or user meddling),
	you can try to restore a backup if you have one, SavageEd.in~ is a backup ini file.
	If no backups exist, you'll have to delete the SavageEd.ini file and SavageEd will
	generate a new one.
	
SavageEd is designed to be a quick editing/note taking program.
As such it:

- opens fast, quickly closes using the escape key
- has options to auto save on exit
- creates a random filename if the current document is untitled
- has option to open the last document you were working on
- has option to remember cursor position in the last opened document

	The saved cursor position is for the last opened document, if a
	different document is opened, SavageEd will try to find the last
	saved index in the new file. This behavior may change in the future.

Most basic functions you would expect in a simple editor (like notepad.exe)
are included in SavageEd.  This short documentation
will cover only items that may differ.

## Keyboard shortcuts

Apart from the standard menu shortcuts, SavageEd has some additional hard coded shortcuts.
	
### Cursor Navigation Shortcuts
		
	- Ctrl-i			Moves the cursor up 1 line
	- Ctrl-k			Moves the cursor down 1 line
	- Ctrl-j			Moves the cursor left 1 character
	- Ctrl-l			Moves the cursor rigtht 1 character
	- Ctrl-,			Move cursor left 1 word
	- Ctrl-.			Move cursor right 1 word
	- Ctrl-[			Move to beginning of line, or beginning of prev line if already there
	- Ctrl-]			Move to end of line, or end of next line if already there
	- Ctrl-e			Delete to end of line
	- Ctrl-u			Uppercase the selection or character
	- Ctrl-Shift-u		Lowercase the selection or character
	
	- Ctrl-Enter		Open line above cursor
	- Shift-Enter		Open line below cursor
	
	- Alt-Up			Move current line up
	- Alt-Down			Move current line down

	- Ctrl-d			Delete 1 char
	- Ctrl-w			Delete 1 word under the cursor
	- Ctrl-Shift-w		Copy word under the cursor (word includes everything except white space)
	- Ctrl-\			Kill line ( line is cut, goes into clipboard )
		
	- Ctrl-SPC			Toggles mark. Shows M on status bar when mark is set.
						Selection will be updated in real time. Toggle mark again to cancel
						
	
	- Shift-TAB			increase indent from anywhere on the line
	- Ctrl-Shift-TAB	decrease indent from anywhere on the line

## File Menu > New Window
This menu option executes another instance of SavageEd.
The new window will be offset slightly from the current window.

	*warning: any new window will have it's own copy of the same
	configuration file "SavageEd.ini" - any changes made to options,
	recent documents, positions, fonts, colors, etc will be saved
	based on the *last* SavageEd window that you close.
	
If you wish to maintain several different configurations, you'll
need several different SavageEd.exe (or hard links to a single one) in separate folders and launch
them by different shortcuts.
	
	To make a hard link, open a command prompt window, and use mklink /H <dest file name> <location of SavageEd.exe> eg:
	mklink /H SavageEd.exe d:\w\tools\savageed\SavageEd.exe
	this will make a hard link called SavageEd.exe in the current folder.


## Edit > Find/Replace
This opens a find/replace dialog that allows searching and replacing.
Options set in find/replace dialog are saved in the configuration file.
Find searches are incremental for normal mode.
There is the added option of "Whole Word".
There is a built in quick find feature:
Pressing F3 without opening find/replace
dialog will find the next instance of the selected word, or the last word that was searched.

## SavageEd has a pattern finding feature which behaves somewhat different
from standard find/replace.  Some things to consider:
	To search for patterns, select the "Match Pattern" check box.
	Pattern searches only works in the 'down' direction
	Pattern searches do not work with whole word option.
	Pattern matching can be case sensitive.
	Pattern matching may or may not function properly with quick find (F3).
	 
To search for patterns, there are two special characters:

	*	Match zero or more characters
	?	Match any one character
	
For example typing in the Find box:
	
	- *e	select every character from the current cursor position to the next 'e' in the document.
	- *	same effect as "select all" after current cursor position.
	- *z*	selects the whole document after the cursor, if there is a 'z' anywhere
	- c*e	find the next 'c' character and match every character until the following 'e'
	- c?t	find the next 'c' character, match any one character and a 't'
		eg: finds "cat" "cot" "cut"
	
Further considerations:
	Patterns searching can be slow in very large files
	Pattern searching may have unusual effects if multiple
	special charactes are clumped together, eg: **?*


## Edit > Insert Date/Time
Enters the date and time at the current position.

SavageEd allows you to customize how the date and time are displayed.
The menu options Edit->Set Date Format and Edit->Set Time Format open
a text entry dialog that allows you to change the date/time format.

In SavageEd.ini, the Settings section contains two keys, Date Format and
Time Format. These allow you to enter special formatting characters.
Eg:
[Settings]
Date Format=dd-MM-yyyy
Time Format= hh:ss:tt

Notice the extra space after the = sign in Time Format, this is to separate
the time from the date. Any text may be entered for this purpose. You may
similarly substitute any character for the dashes or colons.

### Formatting Codes
Formatting the days:
	d    Day of the month as digits without leading zeros for single-digit days.
	dd   Day of the month as digits with leading zeros for single-digit days.
	ddd  Abbreviated day of the week, for example, "Mon" in English
	dddd Day of the week, for example, "Monday" in English

Formatting the months:
	M    Month as digits without leading zeros for single-digit months.
	MM   Month as digits with leading zeros for single-digit months.
	MMM  Abbreviated month, for example, "Nov" in English.
	MMMM Month, for example, "November" in English.
 
Formatting the year:
	y    Year represented only by the last digit.
	yy   Year represented only by the last two digits. A leading zero is added for single-digit years.
	yyyy Year represented by a full four or five digits

Formatting the era:
	g, gg	Period/era, eg "AD" 

Formatting the time:
	h	Hours with no leading zero for single-digit hours; 12-hour clock
	hh	Hours with leading zero for single-digit hours; 12-hour clock
	H	Hours with no leading zero for single-digit hours; 24-hour clock
	HH	Hours with leading zero for single-digit hours; 24-hour clock
	m	Minutes with no leading zero for single-digit minutes
	mm	Minutes with leading zero for single-digit minutes
	s	Seconds with no leading zero for single-digit seconds
	ss	Seconds with leading zero for single-digit seconds
	t	One character time marker string, such as A or P
	tt	Multi-character time marker string, such as AM or PM


## Options > Font
Allows you to select font, point size, effects and color.
Changes will affect the entire document.

## Options > Background Color
Allows you to select a color for the background.
Allows saving up to 16 custom colors.
Click "Define Custom Colors >>" on the dialog to open selection interface. 

## Options > Autosave
With this option selected, SavageEd will save the current document without prompting upon quitting (including quitting via ESC key).
If the document is untitled, SavageEd will create a temporary file name having the form: "Untitledxxxxxxxx.txt" where xxxxxxxx is a pseudo-random number.
This feature is active when quitting or when selecting menu Save.

## Options > Stay on Top
This option makes the SavageEd window a "top" window,
meaning it stays on top of other non-top windows.

## Options > Read Only
Goes into readonly mode, no changes can be made to documents.
Save and SaveAs still function.

## Options > Recent File Options
	
	- Open In New Window
		Opens Recent files in new window.
 
	- Clear On Exit
		Clears the files in the Recent menu on exit.
	 
	- Open Most Recent
		Opens the most recently accessed document when SavageEd starts.
		
	- Remember Position
		Used with Open Most Recent, restors last cursor position

## Options > Set Tabs...
Opens a dialog, enter a new number for tab spacing in number of characters
*warning* the program only checks for valid numbers, if you enter a crazy
value, expect crazy results.
Default tab spacing is 4 characters.

## Options > Tabs As Spaces
Enters a number of white spaces indicated by the tab spacing number, default 4, when the tab key is pressed.

## Options > Auto Indent
Automatically indents the cursor to the previous line whitespace. Not reccommended to mix spaces and tabs as there is no check for this edge case.

## Options > Line Break
Line breaks default to MS/DOS style of CRLF, you can select the LF option to force
SavageEd to save documents with LF line breaks.
	
## Options > Active URLs
Toggles displaying URLs as active links. Setting it on requires a document reload.
This options can be changed manually by editing the .ini file
under [Settings] section, add "Active URL=false/true" (the default is false).
Setting this to true will highlight any URLs in your document, clicking on the URL
will launch the default web browser and open the URL.

	[Settings]
	Active URL=false

If the font size is changed while Active URL is set to true, a document reload 
is required.

## Options > Set Default Extension...
SavageEd defaults to no extension, with the expectation that you will type in
filen names exactly as you want them saved.
You may however set a default extension. When opening a SaveAs dialog on an Untitled
document, your default extension will be used as a pattern and the filename will attach
that extension if none is supplied in the file name.

When entering default extensions, be sure to include the dot. Returning an empty string
will reset to default behavior.

Eg.
.txt

You can also directly edit the config file:
[Settings]
Default Extension=.txt

## Options > Edit Options
Opens SavageEd.ini and allows you to edit it directly instead of using menu items.
Opening this file will set SavageEd into Edit Configuration mode, if you modify and
change this file, the configuration will be reloaded and new options are in effect.
Use with caution. There is no error checking.
A backup file of "SavageEd.in~" is created when this option is selected. 


## Log files.
If you wish to use the log feature, it is compatible to the .LOG
feature of Notepad.exe, with an additional extension.

Type .LOG at the top of your document, on the first line, with
nothing else on that line.  From now on, anytime you open the
file with SavageEd, the current system date/time stamp is appended
to the bottom of the document.

Type .LOG< at the top of your document, on the first line, with
nothing else on that line.  From now on, anytime you open the
file with SavageEd, the current system date/time stamp is inserted
at the top of the document, just below the .LOG< .  So the most
recent updates will appear near the top of the document instead of
the bottom.

## View -> Status Bar
Shows/hides the status bar
The status bar shows the following information:

1st section:
Line / Total lines
Column in current line
Character position in document
Selection size

2nd section:
Readonly Mode	'R'
3th section:
Mark Set	'M'
4th section:
Current mode

## Recent Documents
A list of up to 20 recently opened files are stored in File > Recent menu.
The most recently accessed file will be at the top of the menu.
These files are saved from session to session.  To clear the recent menu,
use the menu Option "Clear Recent On Exit"

## Documents
This document file can be accessed from the Help menu. It will be opened
in an edit window, changing the mode to "View Documentation"

## Kudos and Curses to:

sevag.krikorian@gmail.com

https://sites.google.com/view/androth/home/high-level-assembly

https://github.com/Androthi

https://twitter.com/androth4

## Requirements and further notes:

- This program may be distributed alone (SavageEd.exe) or bundled with the source code. The only required file is "SavageEd.exe"
- There is no installation.  SavageEd does not write to the evil registry.  SavageEd does not read from the evil registry. The only place SavageEd will look outside of it's own folder is in the %USERPROFILE%\config folder for an optional config file.
- At this time, SavageEd does not access the internet, so beware of spooky versions that try to access the internet, I didn't write them.
- SavageEd will create a "SavageEd.ini" file in the same directory. This file will store all the user selected settings and options. After this file is created, you may optionally move it tO %USERPROFILE%\config\SavageEd.ini if you prefer that SavageEd use that folder for configuration.

## Disclaimer:
This software is open source freeware written in a high level assembly
language (HLA).
The author takes no responsibility for the use or misuse of this software
or any damages real, implied or imagined in any form.
It may be re-distributed in whole or in part, with or without sources
bundled or stand alone.

