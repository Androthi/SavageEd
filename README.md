![SavageEd](https://user-images.githubusercontent.com/46191274/124263707-966b5980-db01-11eb-985d-5ea1ef24feaa.png)
# SavageEd
A text editor written in Randal Hyde's high level assembly for Windows.
While the original SavageEd was around 20-25k in size, the latest SavageEd
is over 120k in size and I feel it can no longer be called a "small" text editor.

Feel free to open an issue if you encounter bugs or have suggestions for QOL improvements.


The source is set up as a HIDE project. HIDE binaries can be downloaded from https://github.com/Androthi/HIDE/releases

Open the hpr file in HIDE to build.

The editor uses windows richedit DLL.

Binaries are available at:
https://github.com/Androthi/SavageEd/releases

Older versions may be available at:

https://sites.google.com/view/androth/home/high-level-assembly

Only the source files are guaranteed to be the latest version.

## Features:

- forward or reverse logging

- font, text colour and background colour selection

- uses local ini file to save options and window position settings. does not alter the windows registry, has no installer.

- Many keyboard shortcuts for 'mouse free' editing

- Autosave, quick load and quick exit with esc. key. Ability to maintian relative position in last opened file.

- Customizable format Date/Time insertion

- Save files in DOS or UNIX line endings ( CRLF or LF )

- pattern matching search replace using characters '*' for match zero or more and '?' for match one.

- Ability to search for line ending or tab characters, ability to limit replace all command to the selection.

## Documention
See SavageEd.md for the manual, this is also available in the SavageEd help menu.

See CHANGE_LOG.md for changes between versions. Some versions may add features
that aren't included in your current configuration file. It is possible to manually
add these features, or delete the .ini file and have SavageEd create a new one.

## Development Goals
SavageEd has already exceeded the goals that I originally intended to ship with it.

Everything added since has been quality-of-life improvements such as key bindings
that I consider to be functional for fast editing, and any new features suggested by
SavageEd users that I find interesting.

As it is now, it is feature complete.

However, as I find myself using this alsmost as much as my main code editor,
I'm considering continuing with the project even though I have to fight the awful
Windows API every step of the way.

## Future of SavageEd -- Roadmap to v0.11.00

Things under consideration for the roadmap to version 0.11. These are tentative
as I have limited time and other projects to work on. Some require significant
internal restructuring of code which will be a slow process (already underway).

- Customizable keyboard shortcuts

- Multiple buffers (with or without a tab bar)
    - Extend Find to search through all open buffers

- Autofill Find edit box with frequent searched items
