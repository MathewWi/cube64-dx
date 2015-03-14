# Building Cube64-DX adapter #

_This tutorial show an easy way to build the adapter. This is targeted to beginner. This is often how I build my prototype since it's fast to do and avoid wasting PCB and component. More experienced people would prefer going the SMD way with a little PCB so it look better._

_Also I'm voluntary not showing how to add the MAX682 since it's a SMD only chip. Not for beginner at all. What you could do is using a USB cable plug into one of your nearby newer console to provide +5v to the adapter._
<br><br><br>
<h2>Stuff needed</h2>

<h3>Recommend tools</h3>

<i>Don't be cheap! The key to easily build electronic stuff is to have the right tools. Some might look unnecessary but it does make life a lot easier.</i>

<ul><li><a href='http://www.sparkfun.com/products/9507'>Soldering Iron</a>
</li><li><a href='http://www.sparkfun.com/products/8965'>Brass Sponge</a>
</li><li><a href='http://www.sparkfun.com/products/10240'>Solder</a>
</li><li><a href='http://www.sparkfun.com/products/8967'>Flux Pen</a>
</li><li><a href='http://www.sparkfun.com/products/9317'>Third Hand</a>
</li><li><a href='http://www.sparkfun.com/products/8696'>Wire Strippers</a>
</li><li><a href='http://www.sparkfun.com/products/8794'>Cutters</a>
</li><li><a href='http://www.sparkfun.com/products/8793'>Pliers</a>
</li><li><a href='http://www.sparkfun.com/products/9227'>Curved Tweezers</a>
</li><li><a href='http://www.sparkfun.com/products/9141'>Multimeter</a></li></ul>

<h3>Required Component</h3>

<ul><li>1 x PIC12F683 (See how to <a href='http://code.google.com/p/cube64-dx/wiki/FlashingFirmware'>flash the firmware</a>)<br>
</li><li>1 x GameCube controller socket (From extension cable?)<br>
</li><li>1 x N64 controller plug (From controller or extension cable?)<br>
</li><li>1 x 0.1µF Capacitor<br>
</li><li>2 x 15pF Capacitors<br>
</li><li>1 x 20MHz Crystal<br>
</li><li>1 x 1KΩ Resistor<br>
</li><li>1 x 20 pin DIP socket<br>
</li><li>Some wires, 28 or <a href='http://www.sparkfun.com/products/8031'>30 AWG</a>
<br><br><br>
<h2>Some advise for easy soldering</h2></li></ul>

<ul><li>Alway hold what you are going to solder with the third hand. So you can hold the solder and the iron with your own hand.<br>
</li><li>Alway apply some solder onto the two component you want to join before joining then together.<br>
</li><li>Put flux with the flux pen on the surface before applying solder on it.<br>
</li><li>Put some solder (Not much!) on your iron to help making better thermal conduction.<br>
</li><li>Keep your iron tip clear, use the brass sponge to clean it.<br>
</li><li>Heat the component first with the iron and then with the solder touch the component (Not the iron!) to apply the solder.<br>
<br><br><br>
<h2>Building the adapter</h2></li></ul>

<ol><li>First print the schematic located in the <a href='http://code.google.com/p/cube64-dx/downloads/list'>Downloads</a> section.<br>
</li><li>We are going to build the adapter around a 20 pin DIP socket. That way you don't need to solder any component directly!<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020002.jpg' />
</li></ul></li><li>First you need to bend the pins just like on the picture. Then join together with solder the following pins pair: 1 & 2, 6 & 7, 14 & 15 and 19 & 20. You can optionally cut pins 5, 9, 12 and 16.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020004.jpg' />
</li></ul></li><li>Connect together pins 3 and 15 with small wire.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020006.jpg' />
</li></ul></li><li>Connect together pins 4 and 6 with small wire.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020007.jpg' />
</li></ul></li><li>Connect together pins 8 and 13 with small wire.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020008.jpg' />
</li></ul></li><li>Connect together pins 1 and 10 with small wire.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020009.jpg' />
</li></ul></li><li>Connect together pins 11 and 17 with small wire.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020010.jpg' />
</li></ul></li><li>Connect together pins 13 and 20 with small wire.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020011.jpg' />
</li></ul></li><li>Cut your N64 plug from whatever you are taking it from. With the stripper use the 20AWG hole (Biggest) to remove at least 3cm of the external insulator. Then using the 30AWG hole strip 2mm of each cable insulator. Apply solder to the end of each wires.<br>
</li><li>Repeat previous step for the GameCube socket.<br>
</li><li>Using a multimeter and the adapter schematic, identify each cable. <b>Do not trust the color of the following screenshot</b>. Each cable brand have different color coding.<br>
</li><li>Connect the N64 plug to the socket. GND cable go on pin 20, +3.3v one on pin 1 and Data cable on pin 18.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020012.jpg' />
</li></ul></li><li>Connect the GameCube socket to the DIP socket. Data go on pin 11, +3.3v on pin 10 and GNDs cable on pin 13. <i>You can optionally connect the +5v cable of the rumble motor to a little connector so you can use an external +5v source.</i>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020013.jpg' />
</li></ul></li><li>Now you are ready to insert component!<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020014.jpg' />
</li></ul></li><li>Insert 0.1µF capacitor at the top between pin 1 & 20.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020015.jpg' />
</li></ul></li><li>Insert the PIC below the capacitor.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020016.jpg' />
</li></ul></li><li>Insert the 20MHz crystal below the PIC.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020017.jpg' />
</li></ul></li><li>Insert the two 15pF capacitors below the crystal like on following the picture.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020018.jpg' />
</li></ul></li><li>Finally, insert the 1K resistor between pin 10 & 11 at the bottom.<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020019.jpg' />
</li></ul></li><li>Now enjoy playing N64 with working controller!! :D<br>
<ul><li><img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020022.jpg' /> <img src='http://cube64-dx.googlecode.com/svn/wiki/img/10p_P4020024.jpg' />