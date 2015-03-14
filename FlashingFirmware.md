# Programming The PIC #

## Stuff needed ##
  * .hex for the right PIC model
  * JDM Programmer (Get one cheap on [eBay](http://shop.ebay.com/i.html?_trkparms=65%253A12%257C66%253A2%257C39%253A1%257C72%253A4726&rt=nc&_nkw=jdm+programmer&_sticky=1&_trksid=p3286.c0.m14&_sop=15&_sc=1))
  * Download [WinPic800](http://www.winpic800.com//index.php?option=com_content&task=blogcategory&id=18&Itemid=64&lang=en)

## Setting up WinPic800 ##
  1. Install WinPic800 and his driver.
  1. Click on "Idioma" on the top menu and put it in whatever language you understand ;).
  1. Install your micro-controller into your programmer socket with the first pin of the chip at the top of the socket.
  1. Plug your JDM programmer into the serial port of your computer.
  1. In WinPic800 go into Setting => Hardware and select JDM Programmer and click "Apply edits".
  1. Go into Device => Test Hardware, this should say "Harware Ok". If not check you are using the right COM port. Also using 64bits OS give often trouble. Try programming with 32bits OS instead.

## Flashing the PIC ##
  1. On the top right corner of the application select the PIC series and PIC model you want to program.
  1. Click on the Open icon and load the .hex file corresponding to the micro-controller you are using.
  1. Click on the "Program All" icon to flash the PIC.
  1. Your PIC should now contain Cube64-DX!!