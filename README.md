YATC -- Yet Another Tibia Client
================================
Copyright (C) 2007-2010 Authors

    This program is free software; you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation; either version 2 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program; if not, write to the Free Software
    Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA

## Project is inactive

This project has not been developed since 2010. Last minimal
fixes have been applied in 2011. Any help provided will be minimal.

## Programming

Authors mentioned in no particular order.

- Ivan Vucica       - Khaos
- Nate Fries        - nfries88
- Alexandre Severino - Kilouco
- mips

### Contributors

- mrauter
- Mariusz Gliwinski - shd
- Vindeamatrix510
- FightingElf
- Magnus K.L.       - Smygflik
- Alexandru Pitis   - Ormin
- Adelae

## What is YATC?

YATC is a client for any game that uses Tibia-compatible protocol. It is being
developed as a part of the OpenTibia project. We have chosen the name YATC
since name OpenTibia Client was already taken by a project by another author.

The code has taken shape, but it is still in early development. We develop
support for SDL and OpenGL based drawing engines. GLICT is the current
user interface library. For now we can connect to the login server, display
character list, connect to game world, display basic map, and we can move
around.

This is readme for version 0.3.3SVN.

Do you plan to package our software? If so, make sure you contact
<yatc-contact@vucica.net>

Please visit our site: http://yatc.vucica.net/
 
To report bugs, please visit the GitHub project: https://github.com/opentibia/yatc

To see previously reported bugs, see the archive of our project management
system at OtFans: http://web.archive.org/web/otfans.net/project.php?projectid=3


## Quick logon

If you need compile instructions, please read INSTALL. If you have already
compiled, or you have downloaded a binary, please read on.

Copy Tibia.spr, Tibia.dat and Tibia.pic from another client into YATC. We
currently cannot provide these files due to copyright issues, and we have not
created our own files. Then, start YATC. Go to Options->Network, and enter
the server address. Then go to Enter Game and log on using your account
number and password.

We currently support protocols 8.0 to 8.54. Autodetection will see from which
version of the client you have copied the files and will use the appropriate
protocol. You can manually switch protocol in Options->Network.

Under GNU/Linux, do not forget that caps matter. Tibia.spr is not the same
as tibia.spr.

We have gettext() l10n support but only if you compile from sources. We are
currently unable to provide a consistent UI for all platforms.

## User interface

### Main menu

- Enter Game - Displays login window.
- Options - Shows a window offering General, Graphics,
Console, Hotkeys and Network options, as well as MOTD display.
- Info - Shows info about program.
- Exit Game - Exits the program.

### Enter Game

- Account Number - Enter your assigned account number here.
- Password - Enter the password you have set.
- Create Account - Unused.

### Character list

Click on the character you want to log on with. Then click Ok. If there's
more characters than fits in the list, use the arrows to find the character
you want.

### Game

On the top right you'll find the inventory. Right of it is the map. On the top
right you will find the traffic meter. It measures the amount of bytes
transmitted (TX), received (RX) and total (++). It also measures the same
numbers per hour (in bytes per hour, kibibytes per hour, and mibibytes per
hour).

On the bottom you will find a text box which you can use to chat. Pressing
any letter or number focuses on the textbox automatically.

- Use arrow keys to move.
- Ctrl+click to "Use" item.
- Shift+click to "Look at" item.
- Alt+click to "Attack" creature.

## Configuration file

After you first launch YATC and close it, a file named 'yatc.cfg' will be
generated in the working directory. There are some options that are
inaccessible from the user interface so here's documentation. The options
are as follows:

(Some options may be undocumented.)


### [window]

- engine - This can be either 0 or 1. 0 sets the SDL rendering engine (default), 1 sets
  the OpenGL rendering engine.
- os_cursor - Unused; due to be removed.

### [login]

- account - Specifies your account number that will be entered by default.
- password - Specifies your password that will be entered by default.
- saveaccount - Should the account data be saved.

### [client]

- skin - Unused.
- motdnum - Last number of MOTD that server sent.
- motdtext - Last text of MOTD that server sent.
- ui_compat - Change the UI compatibility settings. If set to 0, UI is maximally compatible with Tibia. If set to 1, UI is enhanced a bit.
 - lang - gettext-style language code. Overrides standard language detected from environment.

### [general]

- classiccontrol - Unused. An option under Options->General
- autochase - Unused. An option under Options->General
- showhints - Unused. An option under Options->General
- shownames - Should names be shown?
- showtexteffects - Should texts be shown?

### [graphics]

- fullscreen - When restarted, YATC will go to fullscreen if this is turned on.
- width - Width part of resolution, or width of window.
- height - Height part of resolution, or height of window.
- bpp - Display color depth. Valid are 8, 16 and 32. 8 gives grayscale.
- maxfps - Limits the maximum framerate. 0 for unlimited.
- stretchgame - Should the game area be strateched or not? 0 or 1.
- smoothstretch - When stretching, should it be smoothed or performed linearly? 0 or 1.
- lighteffects - Type of light effects. 0, 1, 2 or 3 (none, simple, solid, best).

### [console]

- infomsgs - Should informational messages appear? 0 or 1.
- eventmsgs - Should event messages appear? 0 or 1.
- statusmsgs - Should status messages appear? 0 or 1.
- timestamps - Should timestamps be prefixed to messages in console? 0 or 1.
- levels - Should speaker levels be prefixed to messages in console? 0 or 1.
- privatemsgs - Should private messages appear? 0 or 1.

### [network]

- server - Address of server to connect to.
- port - Port of server to connect to.
- otkey - If we're connecting to an OpenTibia server, set to 1, otherwise 0.
- protocol - Protocol version. Valid are 800, 810, 811, 820, 821, 822, 830, 831, 840,
  841, 842, 850, 853, and 854.
- overrideversion - Version to represent to server although another protocol is used. Server
  uses same protocol that's specified under 'protocol', but requires a
  different version sent. (Data files must also have appropriate signatures.)

### [hotkeys]

- ?

### [game]

- battlemode - What battle mode should the game enter with?
- chasemode - What chase mode should the game enter with?
- safemode - Should player be safe against attacking unskulled players? 0 or 1

### [gui]

- inventory_collapsed - Should inventory be collapsed?
- skillsh - Height of skill window. -1 if closed
- battleh - Height of battle window. -1 if closed
- viph - Height of vip window. -1 if closed.
- consoleh - Height of console panel.
- hideofflinevips - Should offline VIPs be visible? 0 or 1.

## Observed issues

* Odd freezes may occur.
* Moving items may fail.
* Linux does not have clipboard support. 

## Reporting bugs

Visit our GitHub project:
 http://github.com/opentibia/yatc

Please include `debugrecord.rec`. Location:

- Windows: YATC folder
- Linux: `~/.yatc`
- Mac OS X: `~/Library/Application Support/OpenTibia/YATC`

