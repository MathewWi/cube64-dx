# Compiling from source. #

## Stuff needed ##
  * Download [TortoiseSVN](http://tortoisesvn.net/downloads.html)
  * Download [MinGW](http://sourceforge.net/projects/mingw/files/Automated%20MinGW%20Installer/mingw-get-inst/)
  * Download [gputils](http://sourceforge.net/projects/gputils/files/gputils-win32/0.13.7/)

## Retrieving source code from SVN repository ##
  1. First install TortoiseSVN on your machine and then reboot.
  1. Create a folder named "cube64-dx" somewhere on your computer.
  1. Right click on the folder and select "SVN Checkout..."
  1. Put "http://cube64-dx.googlecode.com/svn/" as URL and click OK.
  1. You should now download content of the whole repository.

## Installing compilation environment ##
  1. Install MinGW
  1. On the "Select Components" section of the installer select at the bottom both MSYS Basic system and MinGW Developper toolkit.
  1. Install gputils with default setting.
  1. You should be ready to compile now.

## Compiling the program ##
  1. Open MinGW terminal.
  1. Your C:\ is avaialble under /c/
  1. So do "cd /c/path\_to\_your\_folder/cube64-dx/firmware/"
  1. Type "make" and the .hex file for programming the PIC will be build for each supported micro-controllers.