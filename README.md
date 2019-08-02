# SavageEd
A small text editor written in Randal Hyde's high level assembly for Windows

The source is set up as a HIDE project. HIDE binaries can be downloaded from https://sites.google.com/view/androth/home/high-level-assembly
Open the hpr file in HIDE to build.

The editor uses windows richedit DLL.

Binaries are available at
Check the releases section in Github

also older versions may be available at 
https://sites.google.com/view/androth/home/high-level-assembly

Only the source files are guaranteed to be the latest version.

## Features:

- pattern matching search replace using characters '*' for match zero or more and '?' for match one.

- forward or reverse logging

- font, text colour and backgroudn colour selection

- uses local ini file to save options and window position settings. does not alter the windows registry, has no installer.

- AES encryption

## Documention
See SavageEd.md for the manual
See CHANGE_LOG.md for changes between versions

## Development Goals
SavageEd has already exceeded the goals that I originally intended to ship with it.

Everything added since has been quality-of-life improvements such as key bindings
that I consider to be functional for fast editing.

As it is now, it is feature complete.


However, as I find myself using this alsmost as much as my main code editor,
I'm considering continuing with the project even though I have to fight the awful
Windows API every step of the way.

The next major implementation that I'm planning is to add a mini-buffer to extend
the command versatility and start to do away with relying on windows popup dialoges.
