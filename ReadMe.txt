
### CocoaDVDPlayer ###


DESCRIPTION
===========

The CocoaDVDPlayer sample project demonstrates how to play DVD-Video media in a Cocoa application using DVD Playback Services, the API for the DVD Playback framework introduced in Mac OS X v10.3. The project builds an application with a full set of controls and a resizable video window that maintains the correct aspect ratio. Other features include bookmarks, multiple viewing angles, and a playback timer. The project also shows how to register for and handle DVD events, and how to implement error-handling.

Features

Video window:

	• Resizable with real-time scaling
	• Small/Normal/Maximum sizes
	• Two aspect ratios, standard (4:3) and wide screen (16:9)

Control window:

	• Audio volume slider
	• Bookmarks
	• Elapsed or remaining playback time
	• Next Angle button (for titles with multiple viewing angles)
	• Open Media Folder menu item
	• Play/Pause/Stop/Eject buttons
	• Previous Scene and Next Scene buttons
	• Scan Forward and Scan Reverse (4x) buttons
	• Title and scene information
	• Go to Menu button


BUILDING THE APPLICATION
========================

Mac OS X v10.5 or later is required to build the sample. If you want to use the Xcode project file that comes with the sample, you need to install Xcode 3.1 or later. 


USING THE APPLICATION
=====================

To run CocoaDVDPlayer, you need a system with Mac OS X v10.5 or later, an Apple-supplied internal DVD drive, and display hardware that supports DVD playback.

The DVDPlayback framework can only be used by a single client at a time. If CocoaDVDPlayer is already active and the user inserts a DVD, the user will be presented with an alert when the DVD Player application launches and finds that the framework is already in use. The best approach is to insert the DVD, quit DVD Player when it launches, and then run CocoaDVDPlayer.

There's another reason why this approach is best. If a DVD drive has never been used and you insert a DVD, the region code for the drive must be initialized. CocoaDVDPlayer does not know how to set region codes, but DVD Player does. DVD Player cannot set the drive region code, however, if the framework is already in use.

To use CocoaDVDPlayer, follow these steps:

1. Before launching the CocoaDVDPlayer application, Insert a DVD-Video disc in the DVD drive. Apple's DVD Player application automatically launches and opens the DVD. 

2. If prompted to do so, use DVD Player to set the drive region code.

3. Quit DVD Player.

4. Launch CocoaDVDPlayer. CocoaDVDPlayer writes status and error messages to the console as it runs.

5. Display the File menu and verify that media is open. The menu item should read "Close Media Folder". 

Now you're ready to play the DVD media on the disc.

Note that if you launch CocoaDVDPlayer using the Xcode debugger or with GDB directly, you may find that the application terminates when it calls the DVDInitialize function to start a playback session. This is a security feature to protect the decryption code in the DVD Playback framework.


CHANGES FROM PREVIOUS VERSIONS
==============================

Version 1.0 - First release.

Version 1.1 - Updated for Mac OS X v10.5. Switched from deprecated QuickDraw-based functions to new Core Graphics-based functions. Developers using CocoaDVDPlayer 1.0 are encouraged to migrate to this version.


Copyright (C) 2009 Apple Inc. All rights reserved.

