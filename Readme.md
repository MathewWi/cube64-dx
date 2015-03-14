# Cube64-DX #

## Introduction ##

This is a project to build an adaptor for using Gamecube controllers with N64 consoles. The motivation behind this is that the N64 has some really great games, but the controller hardware is rather bad- the joysticks wear out quickly, and the layout is odd. The Gamecube controllers, however, have a superset of the features and a much better joystick.

A secondary goal of this project is to more thoroughly reverse engineer the protocols involved and create reusable libraries for interfacing PIC micro-controllers to N64 and Gamecube devices. The very basics of reverse engineering the two protocols was done before I started this project, but I quickly discovered that there's much more to the protocol. I believe this project may be the first one to completely reverse engineer the protocol used by standard N64 controllers, including peripherals like the memory and rumble paks.

All code here is released under the GPL. This means that if you have basic electronics skills and a way to program the microcontroller, you can build your own cube64 adaptor easily. The hardware is extremely simple, and all the complexity of reverse engineering and writing code is done for you ;)


## Usage ##

The completed adapter plugs into an N64 console, and a regular Gamecube controller or Wavebird (Only for 12f683 version) plugs into the adapter.  The default button mapping is as follows:

| **Gamecube** | **N64** |
|:-------------|:--------|
| Analog stick | Analog stick |
| D-pad | D-pad |
| A | A |
| B | B |
| Z | Z |
| Start | Start |
| R end-stop | R |
| L end-stop | L |
| C-stick | C buttons |
| X | C-down |
| Y | B |

This button mapping is stored in non-volatile memory, and may be modified during gameplay. To change the mapping for one button:

  1. Hold down the L and R buttons down most of the way, but not enough to push the end-stop buttons, and press Start.
  1. If you have the rumble power connected, you should feel a brief rumble.
  1. Press the button you wish to remap. This includes the C-stick and D pad, since they emulate buttons.
  1. Press the button you want to map it to. This button is always interpreted according to the above defaults, so for example pressing Y here would actually map to B. This has the effect that pressing the same button you pressed in step always resets that button to its default mapping.
  1. If the mapping was successful and you have rumble power connected, you should feel a brief rumble.

<br><br>

To reset all mappings of the current active button layout to the above defaults:<br>
<br>
<ol><li>Hold down the L and R buttons down most of the way, but not enough to push the end-stop buttons, and press Z.<br>
</li><li>If you have the rumble power connected and the reset was successful, you should feel a brief rumble.</li></ol>

<br><br>

To toggle between displaying the controller with empty slot and occupied slot (See notes below):<br>
<br>
<ol><li>Hold down the L and R buttons down most of the way, but not enough to push the end-stop buttons, and press X.<br>
</li><li>If you have the rumble power connected and the toggle was successful, you should feel a brief rumble.</li></ol>

Note 1:<br>
<ul><li>This setting is volatile. Adapter alway start as occupied on boot.</li></ul>

Note 2:<br>
<ul><li>This feature is usefull for some game that repport error with a rumble pak. For those games, immediately toggle to empty controller on boot to avoid the error.</li></ul>

<br><br>

It is possible to save up to 4 sets of custom buttons layouts so you can easily use different keys mapping in different games. To change between the preset do the following (Only available in 12F683 version):<br>
<br>
<ol><li>Hold down the L and R buttons down most of the way, but not enough to push the end-stop buttons, and press one of the direction on the Gamecube direction pad.<br>
</li><li>If you have the rumble power connected and the preset change was successful, you should feel a brief rumble.<br>
</li><li>All preset by default hold the default button configuration. Just select one of 4 presets and then change the button configuration using the button mapping key combo described above.<br>
</li><li>When you select a preset it is saved into the eeprom so the next time you power up the adaptor the last used preset will be load automaticaly!</li></ol>

<br><br>

The adaptor handles calibration in almost the exact same way a Gamecube does. If your joystick is drifting or nonresponsive during gameplay, you should be able to recalibrate it by performing any of the following actions without touching the joystick, C-stick, L button, or R button:<br>
<br>
<ol><li>Hold down X, Y, and Start for a couple seconds during gameplay<br>
</li><li>Unplug the controller from the adaptor and plug it back in<br>
</li><li>Unplug the adaptor from the N64 and plug it back in<br>
</li><li>Turn off the N64 then turn it back on. (The reset button won't recalibrate, since the adapter doesn't lose power or get reinitialized)</li></ol>


<h2>Hardware</h2>

There are currently three versions of the Cube64 hardware:<br>
<br>
<blockquote>- The "Cube64 Basic" uses a very common PIC16F84A microcontroller, and requires an external 5V power supply. Just about any electronics hobbyist should be able to build it easily. (Deprecated)</blockquote>

<blockquote>- The "Cube64 Mini" uses a tiny 8-pin PIC12F629 microcontroller, and includes a charge pump that generates the 5V supply for the rumble motor. It is smaller and more convenient than the Cube64 Basic, but it requires a less common microcontroller and a charge pump that's only available in surface mount packages. (Deprecated)</blockquote>

<blockquote>- The "Cube64-DX" uses the PIC12F683 microcontroller. It use exacly the same circuit as the Cube64 Mini. It's the only version who get new feature since it have more flash memory to hold the additional code needed.</blockquote>

Both older versions of the hardware have the same button remapping features and responsiveness, as the only difference in their firmware is a few lines worth of compile-time configuration. You can also of course use the charge pump circuit from the Cube64 Mini with a PIC16F84A- but if you're using tiny chips anyway, might as well go all the way ;)<br>
<br>
The PIC12F683 version include all new feature like multi button mapping layout, Wavebird support and a more accurate joystick value range.<br>
<br>
<br>
<h2>Status</h2>

The protocol used between the N64 and controller, and between the controller and controller pak is well-understood now. An RS-232 to N64 bridge and several Python programs demonstrate just about all of the protocol.<br>
<br>
The necessary subset of the protocol has been implemented in the cube64 firmware to emulate an official N64 controller with rumble pak. If 5V power for the motor can be supplied to the gamecube controller, its rumble motor will be used to emulate the N64 rumble pak.<br>
<br>
It should be possible to emulate the N64 memory pak using the results of my reverse engineering, but a 20 MHz PIC probably isn't fast enough to run the CRC algorithm in time to return a status byte to the N64. If a faster implementation of the CRC is discovered or a processor about twice as fast is used, the memory pak could be emulated easily.<br>
<br>
<br>
<h2>Contents</h2>

<blockquote>firmware:  Source code for the firmware, in PIC assembly. I develop this mostly using the open source "gputils" package, but I occasionally test it with MPLAB. The firmware for the adaptor itself is "cube64.asm", but there are a few additional test programs and libraries.</blockquote>

<blockquote>hardware:  This includes schematics for the adaptor, in PDF and gschem format.</blockquote>

<blockquote>notes:     Utilities and documentation produced while reverse engineering</blockquote>


Micah Dowty <micah@navi.cx><br>
<br>
Jacques Gagnon <darthcloud@gmail.com>