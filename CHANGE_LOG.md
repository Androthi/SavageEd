# Change Log

## 07/02/2021
	0.6.03	- Changed behavior in where SavageEd looks for SavageEd.ini file.
			  It will look in current folder first, if found, SavageEd will use
			  that .ini profile.
			  If there is no .ini file in the SavageEd folder, it will look
			  for one in "%USERPROFILE%\config\SavageEd.ini"
			  If that file exists, SavageEd will use that file as the profile.
			  If neither exists, SavageEd will create one in the current folder
			  as normal.
			- SavageEd.md documentation is no longer required as an additional file,
			  the documentation is now embedded in the .exe
  

## 06/30/2021
	0.6.02	- fixed command_delete_word to not consume new line
			- added command_copy_word and mapped it to ctrl-shift-w
			  copies the word under the cursor to the clipboard
			  right now it copies all characters except white space
			  this behavior should be changed to copy only words, ignoring
			  other characters lick brackets, math symbols, commas, periods, etc.
			  although a case can be made to keep periods in

## 06/27/2021
	0.6.01	- added command_delete_word and mapped it to ctrl-w
			  deletes the word under the cursor

## 06/19/2021
	0.6.00	- refactor and cleanup
			- added SavageEd.hhf file and moved all definitions there
			  to reduce clutter in the main file
			- changed mark setting behavior. Mark remains active when
			  user resumes typing.
			- increase indent and reduce indent now work with mix of
			  tabs and spaces

## 06/15/2021
	0.5.10	- removed ctrl-shift-j and ctrl-shift-l. it is now ctrl-[ and ctrl-]
			  some unintended behavior fixed.
			- added shift-enter to open line below cursor
			- added ctrl-enter to open line above cursor
			- fixed UNDO selecting all and changing text color back to default when there
			  is nothing to undo.
			- cleaned up some code made it more command oriented for easier expansion

## 05/11/2021
	0.5.8	- added Tab as Spaces option - converts tabs to spaces for any new tab entered
			  not fully implemented. does not work with indent/outdent feature
			  
			  issues:pressing ctrl-z (undo) when there are no more undos selects the entire text, then deletes it forever.

## 8/04/2019
	0.5.7	- added Save Selection As option
			- removed .txt extension assumption. Save As now saves filenames
			  exactly as typed.
			- added shift-tab indent line, ctrl-shift-tab  outdent line.

## 7/31/2019
	0.5.0	- removing printing capability.
			  it was always more of a hack and there are better programs
			- shows changed documents with a * before the title on titlebar
	0.5.x   - added keyboard shortcuts for cursor navigation on ctrl-i,j,k,l
			- added mark command on ctrl-SPC
			- added ctrl-d delete, ctrl-\ kill line, ctrl-shift-j move to start of line
			  ctrl-shift-l move to end of line, ctrl-, move word left, ctrl-. move word right
			- added cursor position information to display on status bar
			- added colorchooser for text font so you're no longer limited to
			  colors in the Font selection dialog.
	
## 7/30/2019
	0.4.3	- refactored some code
			  fixed minor keyboard input bugs

## 7/11/2019
	0.4.0	- added "Remember Position" menu item
				works with "Open Most Recent" and remembers
				the last posiiton in that document.
	0.4.1	- fixted status bar update

## 7/10/2019
	0.3.1	- fixed goto command
			  fixed opening files from command line
	0.3.0	- new versioning system
			- fixed window drifting
## 11/27/2010
	0.02.00 - fixed Save As not renameing properly
	        - added Set Tabs option
	0.01.00 - first public beta release of SavageEd

