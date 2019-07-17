# SavageEd
A small text editor written in Randal Hyde's high level assembly for Windows

The source is set up as a HIDE project. HIDE binaries can be downloaded from https://sites.google.com/view/androth/home/high-level-assembly
Open the hpr file in HIDE to build.

The editor uses windows richedit DLL.

Binaries are available at
https://sites.google.com/view/androth/home/high-level-assembly


## Features:

- pattern matching search replace using characters '*' for match zero or more and '?' for match one.

- forward or reverse logging

- font, text colour and backgroudn colour selection

- uses local ini file to save options and window position settings. does not alter the windows registry, has no installer.

- AES encryption

