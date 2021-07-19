# SavageEd Documentation

# Quick Start
	All you need to run SavageEd is the file SavageEd.exe
	
	After the first run, the program will create a settings file in
	the parent folder called "SavageEd.ini"
	If you wish to use your "%USERPROFILE%\config" folder instead,
	create a config folder (if one doesn't already exist) in your user profile
	folder, and move the SavageEd.ini file there.
	
	eg: "c:\user\mako\config\SavageEd.ini"
	
	If there is a SavageEd.ini file in the SavageEd parent folder, SavageEd
	will always prioritise using that config instead.

	Reading anything beyond this point is optional.
	
SavageEd is designed to be a quick editing/note taking program.
As such it:

	- opens fast, quickly closes using the escape key
	- has options to auto save on exit
	- creates a random filename if the current document is untitled
	- has option to open the last document you were working on
	- has option to remember cursor position in that document

Most basic functions you would expect in a simple editor (like notepad.exe)
are included in SavageEd.  This short documentation
will cover only items that may differ.

## Keyboard shortcuts
	Apart from the standard menu shortcuts, SavageEd has some additional
	hard coded shortcuts.
	
### Cursor Navigation Shortcuts
		
	- Ctrl-i	Moves the cursor up 1 line
	- Ctrl-k	Moves the cursor down 1 line
	- Ctrl-j	Moves the cursor left 1 character
	- Ctrl-l	Moves the cursor rigtht 1 character
	- Ctrl-,	Move cursor left 1 word
	- Ctrl-.	Move cursor right 1 word
	- Ctrl-[	Move to beginning of line, or beginning of prev line if already there
	- Ctrl-]	Move to end of line, or end of next line if already there
	
	- Ctrl-Enter	Open line above cursor
	- Shift-Enter	Open line below cursor

	- Ctrl-d		Delete 1 char
	- Ctrl-w		Delete 1 word under the cursor
	- Ctrl-Shift-w	Copy word under the cursor (word includes everything except white space)
	- Ctrl-\		Kill line ( line is cut, goes into clipboard )
		
	- Ctrl-SPC	Toggles mark. Shows M on status bar when mark is set.
				Press again to select marked text.
	
	- Shift-TAB			increase indent from anywhere on the line
	- Ctrl-Shift-TAB	decrease indent from anywhere on the line

## File Menu > New Window
	This menu option executes another instance of SavageEd.
	The new window will be offset slightly from the current window.

*warning: any new window will have it's own copy of the same
configuration file "SavageEd.ini" - any changes made to options,
recent documents, positions, fonts, colors, etc will be saved
based on the *last* SavageEd window that you close.

If you want to maintain several different settings, you'll need
to have multiple copies of SavageEd in different directories.


## Edit > Find/Replace
	This opens a find/replace dialog that allows searching and replacing.
	Options set in find/replace dialog are saved in the configuration file.
	There is the added option of "Whole Word".
	There is a built in quick find feature:
	  Pressing F3 without opening find/replace
	  dialog will find the next instance of the selected word.

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
	
	- *e
	  select every character from the current cursor position to the next 'e'
	  in the document.
	- *
	  same effect as "select all" after current cursor position.
	- *z*
	  selects the whole document after the cursor, if there is a 'z' anywhere
	- c*e
	  find the next 'c' character and match every character until the following 'e'
	- c?t
	  find the next 'c' character, match any one character and a 't'
	  eg: finds "cat" "cot" "cut"
	
Further considerations:
	Patterns searching can be slow in very large files
	Pattern searching may have unusual effects if multiple
	special charactes are clumped together, eg: **?*
	

## Options > Font
Allows you to select font, point size, effects and color.
Changes will affect the entire document.

## Options > Background Color
Allows you to select a color for the background.
Allows selection of up to 16 custom colors.
Click "Define Custom Colors >>" on the dialog to open selection interface. 

## Options > Autosave
With this option selected, SavageEd will save the current
document without prompting upon quitting (including quitting
via ESC key).
If the document is untitled, SavageEd will create a temporary
file name having the form: "Untitledxxxxxxxx.txt" where
xxxxxxxx is a pseudo-random number.  This feature is active when
quitting or when selecting menu Save.

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
	current line number		'Line: xx'
	current column number	'Column: xx'
	cursor position			'Pos: xx'
	total number of lines	'Lines: xx'
2nd section:
	insert/overwrite mode 	'INS'/'OVR'
3rd section:
	readonly mode 			'R'
4th section:
	mark set				'M'
		

## Recent Documents
A list of up to 20 recently opened files are stored in File > Recent menu.
The most recently accessed file will be at the top of the menu.
These files are saved from session to session.  To clear the recent menu,
use the menu Option "Clear Recent On Exit"


## Kudos and Curses to:

androth.pro@gmail.com

https://sites.google.com/view/androth/home/high-level-assembly


## Requirements and further notes:

	- This program may be distributed alone (SavageEd.exe) or 
	  bundled with the source code. The only required file is "SavageEd.exe"
	- Some options may require other files to be present, but will function without them.
	- There is no installation.  SavageEd does not write to the evil registry.  SavageEd does not read from the evil registry.
	  The only place SavageEd will look outside of it's own folder is in the
	  %USERPROFILE%\config folder for an optional config file.
	- At this time, SavageEd does not access the internet, so beware of spooky versions that try to access the internet, I didn't write them.
	- SavageEd will create a "SavageEd.ini" file in the same directory.
	  This file will store all the user selected settings and options.
	  After this file is created, you may optionally move it tO
	  %USERPROFILE%\config\SavageEd.ini if you prefer that SavageEd use that
	  folder for configuration.

## Disclaimer:
This software is open source freeware written in a high level assembly
language (HLA).
The author takes no responsibility for the use or misuse of this software
or any damages real, implied or imagined in any form.
It may be re-distributed in whole or in part, with or without sources
bundled or stand alone.

