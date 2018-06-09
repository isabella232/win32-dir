# win32-dir

[![Gem Version](https://badge.fury.io/rb/win32-dir.svg)](https://badge.fury.io/rb/win32-dir)

A series of extra constants for the Dir class that define special folders on MS Windows systems, as well as methods for creating and detecting junctions, i.e. symlinks for directories.

## Installation

```
gem install win32-dir
```

## Synopsis

```ruby
require 'win32/dir'


# C:\WINNT or C:\WINDOWS
puts Dir::WINDOWS

# C:\Documents and Settings\Daniel\Start Menu\Programs\Administrative Tools     
puts Dir::ADMINTOOLS


Dir.mkdir('C:\from')
Dir.create_junction('C:\to', 'C:\from')
```

## Constants

Not all of these are guaranteed to be defined on your system. Also note that the directories are merely defined. It doesn't necessarily mean they actually exist.

### The following constants should be defined:

#### Dir::ADMINTOOLS

The file system directory that is used to store administrative tools for an individual user. The Microsoft Management Console (MMC) will save customized consoles to this directory, and it will roam with the user.

#### Dir::COMMON_ADMINTOOLS

The file system directory containing administrative tools for all users of the computer.

#### Dir::APPDATA

The file system directory that serves as a common repository for application-specific data. A typical path is C:\Documents and Settings\

<user>\Application Data.</user>

This CSIDL is supported by the redistributable shfolder.dll for systems that do not have the Microsoft Internet Explorer 4.0 integrated Shell installed.

#### Dir::COMMON_APPDATA

The file system directory containing application data for all users. A typical path is C:\Documents and Settings\All Users\Application Data.

#### Dir::COMMON_DOCUMENTS

The file system directory that contains documents that are common to all users. A typical paths is C:\Documents and Settings\All Users\Documents.

#### Dir::COOKIES

The file system directory that serves as a common repository for Internet cookies. A typical path is C:\Documents and Settings\

<user>\Cookies.</user>

#### Dir::HISTORY

The file system directory that serves as a common repository for Internet history items.

#### Dir::INTERNET_CACHE

The file system directory that serves as a common repository for temporary Internet files. A typical path is C:\Documents and Settings\

<user>\Local Settings\Temporary Internet Files.</user>

#### Dir::LOCAL_APPDATA

The file system directory that serves as a data repository for local (nonroaming) applications. A typical path is C:\Documents and Settings\

<user>\Local Settings\Application Data.</user>

#### Dir::MYPICTURES

The file system directory that serves as a common repository for image files. A typical path is C:\Documents and Settings\

<user>\My Documents\My Pictures.</user>

#### Dir::PERSONAL

The virtual folder representing the My Documents desktop item. This is equivalent to Dir::MYDOCUMENTS.

#### Dir::PROGRAM_FILES

The Program Files folder. A typical path is C:\Program Files.

#### Dir::PROGRAM_FILES_COMMON

A folder for components that are shared across applications. A typical path is C:\Program Files\Common.

#### Dir::SYSTEM

The Windows System folder. A typical path is C:\Windows\System32.

#### Dir::WINDOWS

The Windows directory or SYSROOT. This corresponds to the %windir% or %SYSTEMROOT% environment variables. A typical path is C:\Windows.

### The following constants may or may not be defined:

#### Dir::ALTSTARTUP

The file system directory that corresponds to the user's nonlocalized Startup program group.

#### Dir::BITBUCKET

The virtual folder containing the objects in the user's Recycle Bin.

#### Dir::CDBURN_AREA

The file system directory acting as a staging area for files waiting to be written to CD.

#### Dir::COMMON_ALTSTARTUP

The file system directory that corresponds to the nonlocalized Startup program group for all users.

#### Dir::COMMON_DESKTOPDIRECTORY

The file system directory that contains files and folders that appear on the desktop for all users. A typical path is C:\Documents and Settings\All Users\Desktop.

#### Dir::COMMON_FAVORITES

The file system directory that serves as a common repository for favorite items common to all users.

#### Dir::COMMON_MUSIC

The file system directory that serves as a repository for music files common to all users.

#### Dir::COMMON_PICTURES

The file system directory that serves as a repository for image files common to all users.

#### Dir::COMMON_PROGRAMS

The file system directory that contains the directories for the common program groups that appear on the Start menu for all users.

#### Dir::COMMON_STARTMENU

The file system directory that contains the programs and folders that appear on the Start menu for all users.

#### Dir::COMMON_STARTUP

The file system directory that contains the programs that appear in the Startup folder for all users.

#### Dir::COMMON_TEMPLATES

The file system directory that contains the templates that are available to all users.

#### Dir::COMMON_VIDEO

The file system directory that serves as a repository for video files common to all users.

#### Dir::CONTROLS

The virtual folder containing icons for the Control Panel applications.

#### Dir::DESKTOP

The virtual folder representing the Windows desktop, the root of the namespace.

#### Dir::DESKTOPDIRECTORY

The file system directory used to physically store file objects on the desktop (not to be confused with the desktop folder itself).

#### Dir::DRIVES

The virtual folder representing My Computer, containing everything on the local computer: storage devices, printers, and Control Panel. The folder may also contain mapped network drives.

#### Dir::FAVORITES

The file system directory that serves as a common repository for the user's favorite items.

#### Dir::FONTS

A virtual folder containing fonts.

#### Dir::INTERNET

A virtual folder representing the Internet.

#### Dir::MYDOCUMENTS

The virtual folder representing the My Documents desktop item. See also Dir::PERSONAL.

#### Dir::MYMUSIC

The file system directory that serves as a common repository for music files.

#### Dir::MYVIDEO

The file system directory that serves as a common repository for video files.

#### Dir::NETHOOD

A file system directory containing the link objects that may exist in the My Network Places virtual folder. It is not the same as Dir::NETWORK, which represents the network namespace root.

#### Dir::NETWORK

A virtual folder representing Network Neighborhood, the root of the network namespace hierarchy.

#### Dir::PRINTERS

The virtual folder containing installed printers.

#### Dir::PRINTHOOD

The file system directory that contains the link objects that can exist in the "Printers" virtual folder.

#### Dir::PROFILE

The user's profile folder.

#### Dir::PROFILES

The file system directory containing user profile folders.

#### Dir::PROGRAMS

The file system directory that contains the user's program groups (which are themselves file system directories).

#### Dir::RECENT

The file system directory that contains shortcuts to the user's most recently used documents.

#### Dir::SENDTO

The file system directory that contains Send To menu items.

#### Dir::STARTMENU

The file system directory containing Start menu items.

#### Dir::STARTUP

The file system directory that corresponds to the user's Startup program group.

#### Dir::TEMPLATES

The file system directory that serves as a common repository for document templates.

## Developer's Notes

The SHGetFolderPath() documentation on MSDN is somewhat vague about which CSIDL constants are guaranteed to be defined. However, there are 15 which _should_ be defined (see docs above). The rest I cannot vouch for.

Some of these folders are virtual, and the value will be the display name only instead of an actual path.

## Known Bugs

The Dir.create_junction and Dir.read_junction methods do not work with JRuby.

Please log any bug reports on the project page at <http://www.github.com/chef/win32-dir>

## Future Plans

Suggestions welcome.

## Acknowledgements

Shashank Date and Zach Dennis for the suggestion and supporting comments on the mailing list.

Timothy Byrd and Autrijus Tang for help (directly or indirectly) with the junction methods. Timothy provided a pure Ruby version of the junction code that I later borrowed from.

Most of the documentation was copied from the MSDN web site.

## License

Artistic 2.0

## Copyright

(C) 2003-2015 Daniel J. Berger, All Rights Reserved

## Warranty

This package is provided "as is" and without any express or implied warranties, including, without limitation, the implied warranties of merchantability and fitness for a particular purpose.

## Authors

- Daniel J. Berger
- Park Heesob
