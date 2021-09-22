# Change Log

## 09/22/2021
	0.10.00	- remember position now works if file name to open is entered on command line.
			- fixed foreground spelling error
			- v0.10.00 finalized

## 09/15/2021
	0.9.35	- added Replace Sel to Find dialog. Clicking this scopes the replace all to
			  the currently selected block of text.
			- fixed bug in Replace All that was ignoring any selected text.

## 09/09/2021
	0.9.33	- input dialog now shows current value of object being changed
			- fixed tab stops not using proper value

## 09/04/2021
	0.9.31	- added special codes to find dialog
			  while in special codes mode, 
			  entering \n will find/replace line break characters
			  entering \t will find/replace tab characters
			  entering special codes find mode disables incremental find

## 09/01/2021
	0.9.30	- case changing options now maintain selection, and single action case
			  changes no longer advance cursor.
			- fixed ctrl-HOME and ctrl-END to navigate to top and bottom of document
			- fixed Recent Files menu, now updates as soon as you save a new file
			- added copy word and delete word to edit menu
			- fixed a mouse behavior issue when in marked selection mode
			- any insert change should now deactivate marked selection mode as it should

## 08/27/2021
	0.9.20	feature changes:
			- added option for settings Default Extension=
			  allows setting the default extension that SavageEd appends to
			  filenames that don't have extensions from SaveAs dialog.
			- Choosing SaveAs on an Untitled document will insert "*<default_extension>" as
			  a filter to the dialog
			- added menu option to change CRLF/LF line breaks
			- added menu option to toggle Active URLs (activating requires document reload)
			- added menu option to change default extension
			- added menu options to set date and time formats  
			- added menu for edit - case to upper, case to lower.
			- added menu for edit increase and decrease indent

## 08/21/2021
	0.9.13	feature changes:
			- status bar now shows selection size
			internal changes:
			- made pattern find more stable

## 08/19/2021
	0.9.10	feature changes:
			- mark now goes into selection mode and selection is updated real time
			  no longer need to toggle mark again to select.

## 08/16/2021
	0.9.00	feature changes:
			- added ability to show and click on urls to open with default browser
			- added ability to format date and time. see manual on how to use.
			- added ctrl-u upper case selection or character
			- added ctrl-shift-u lower case selection or character

## 07/31/2021
	0.8.10	-shift+end no longer selects line feed character
			 note, selecting the line by clicking on the border
			 and using ctrl-\ to kill line still captures LF
			-added alt+up and alt+down to move the current line up or down
			-added ctrl+e delete to end of line
	0.8.04	-internal changes:
			 -now displays app name on title bar
			 -file not found warning now includes the filename
			 -replaceall now tries to restore relative position
			 -got rid of global strbuf
			 -fixed blank space in temp names

## 07/27/2021
	0.8.00	- features changes:
				- added option to save file with LF line endings
				  this option can only be edited by using the "Edit Options"
				  and changing the .ini file manually
				  by adding a new line under
				  
				  [Settings]
				  Line Break=CRLF
				  or
				  Line Break=LF
				  
			- internals changes:
				- fixed filename mangling bug
				- fixed line/pos not showing correctly on first load

## 07/26/2021
	0.7.17	- features changes:
				- added the option to edit/view the Savage.ini file from an open
				  SavageEd instance.
			- internals changes:
				- began splitting build into units to move more stable procedures
				  and declutter SavageEd.hla
				- fixed ctrl-enter bug introduced during some refactoring

## 07/24/2021
	0.7.1x	- feature changes:
				-find dialog now uses incremental find
			- internals changes:
				-migrated color settings to the window structure
			 	-added range record to replace windows CHARRANGE
				-implemented typeConsts macros
			 	-changed config, no longer saves cpMin/cpMax, now just
				saves Start Position. there is a plan to eventually move
			 	 this to section that saves start position by file rather than
			 	 by last opened file.
			 	-changed various label names to make them more verbose and self-commenting

## 07/19/2021
			- removed AES support. It wasn't working properly with
			  unicode files.

## 07/18/2021
	0.7.xx	- internall changes

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

