# Wemos: the Clone Wars
List of Wemos and other ESP8266 clone boards


## Introduction
For several of my projects I use a lot of ESP8266 boards like the Wemos D1 Mini.<br>
Aside from the 'original' Wemos D1 Mini from Wemos/Lolin, there are a lot of clones. These are copies of the original.<br>
Usually these clones work just fine for most purposes, but at some point I started to run into specific issues with some of these boards. So I started to investigate why.<br>
<br>

## Possible issues with clone chips
Problems include a non-responsive or slow web interface, intermittent USB connections, bad Wi-Fi reception, underpowered LDO etc.<br>
<br>
If you Google around a lot of people have problems of some sort:<br>
[Problematic Do-It.AM modules](https://geekenargentina.wordpress.com/2019/10/08/esp8266-connectivity-troubleshooting/)<br>
[Underpowered LDO's (Reddit Post)](https://www.reddit.com/r/esp8266/comments/9iizx4/warning_clone_wemos_d1_minis_with_only_150ma_33v/)<br>
etc.

### Connectivity issues, slow or unresponsive web interface or unstable USB connection


### Underpowered LDO
A Wemos normally gets its power via USB. This is a 5V input. The ESP8266 cannot handle 5V. It needs 3.3V.
An on-board voltage regulator (also called a LDO or Low Drop Out regulator) converts this 5V into 3.3V.<br>
Espressif, the manufacturer of the ESP8266, recommends a regulator that can supply 500mA of current. You can find this information the in the [ESP8266 hardware design guidelines, (footnote page 7)](https://www.espressif.com/sites/default/files/documentation/esp8266_hardware_design_guidelines_en.pdf).
Knowing that the average current of an ESP8266 is about 70mA and the all-out stressed consumption is rated by Espressif at about [170mA](https://bbs.espressif.com/viewtopic.php?t=133), this 500mA is a good margin. Real world measurements by others have indicated that although the average power consumption is just 70mA, at boot and on other instances power spikes occur. These spikes are very short but current can be as much as 400mA.<br>
The original Lolin/Wemos D1 Mini boards have a MicrOne ME611 regulator on board that can deliver 500mA. So more than enough for that average 70mA and even enough for those short spikes.<br>
Usually if you are making a clone of the original, you do so in order to make some money. But there a only a few components on a Wemos, so little room for making it cheaper. The ESP chip is always the same, and passive components are already extremely cheap anyway. So the only major difference you can make is by using a different flash chip and a different LDO.<br>
And that is exactly what you see with these clones.<br>
Almost all Wemos D1 Mini clones have a different (Torex) regulator rated at 150mA at 3.3V. If you draw more, the voltage will drop fast.<br>
is this really a problem? This depends on the usage.<br>
My own basic measurements for the Wemos chips with EMS-ESP firmware of [Proddy](https://github.com/proddy/EMS-ESP) show an average current of 70mA. So even with a LDO rated at 150mA this should be OK for non-stressed use cases and indeed I had no problems at all because of this. To be on the safe side I do include an additional capacitor on the output for those short peaks you cannot even measure with a normal multimeter.<br>
The 150mA is already on the lower side for the ESP8266 itself, which means you cannot draw any significant additional current from the 3.3V line of the Wemos.<br> A few mA will be fine, but by adding f.i. a string of LED's you will have a bad time getting reliable results with these boards. In that case add your own 3.3V LDO on the 5V line of the Wemos.


## Buying clone chips
My experience is that even when clones look identical, often they are not. Even if they have the same marking on the RF shield, they might have a different flash chip or LDO. Even if you buy the same article number from the same supplier again and again you might not always get the same boards.<br>
Also if you buy these from Ebay, AliExpress, DX etc you almost never get the exact same board as is in the pictures. Most of the stores show an image of a board with an AI-Thinker module but you never get these. It's usually a 'generic' clone without a vendor ID.
<br>
Again, not all clones are bad. Most are fine for your simple hobby projects. I only had a few that had issues.<br>
But wherever possible, just use the original as its only 1 Euro more expensive.

### List description

With the list below I want to make an overview of those different boards.<br>
<br>
With `esptool.py flash_id` you can get some ID's of the flash. These are listed as below:<br>

Row | Contents (example)
--- | ---
Manufacturer | Winbond
Type | W25Q32FVSS
Size | 4MB (32mbit)
Manufact. ID | 0xEF
Device ID | 4016
<br>
The 3.3V voltage regulator (LDO) on the board is identified as well (if possible).<br>

Row | Contents (example)
--- | ---
Manufacturer | MicrOne
Type | ME6211
Rated output | 500mA
Package marking | S2MD
<br>

## List of Wemos and other ESP8266 dev boards

Board type | Vendor and ESP | Flash | LDO | Purchased | Remarks | Image
--- | --- | --- | --- | --- | --- | ---
|Wemos D1 Mini V3.1.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|Winbond<br>W25Q32FVSS<br>4MB (32mbit)<br>ID 0xEF|MicrOne<br>ME6211<br>500mA<br>marking: S2RY|Q2 2019<br>[AliExpress: Lolin offical store](https://lolin.aliexpress.com/store/1331105)|This is the best original Wemos D1 Mini|
|Wemos D1 Mini V3.1.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|Giga Device<br>GD25Q32C<br>4MB (32mbit)<br>ID 0x|MicrOne<br>ME6211<br>500mA<br>marking: S2RK|Q4 2019<br>[AliExpress: Lolin offical store](https://lolin.aliexpress.com/store/1331105)|This is the best original Wemos D1 Mini|
|Wemos D1 Mini V3.0.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|Winbond<br>W25Q32FVSS<br>4MB (32mbit)<br>ID 0x|MicrOne<br>ME6211<br>500mA<br>marking: S2MD|||
|Wemos D1 Mini V2.2.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|4MB (32mbit)<br>ID 0x|MicrOne<br>ME6211<br>500mA<br>marking: ||ESP shield marking: ESP-12S. Vendor marking: AI|
|Wemos D1 Mini V2.3.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|4MB (32mbit)<br>ID 0x|MicrOne<br>ME6211<br>500mA<br>marking:||ESP shield marking: ESP-12S. Vendor marking: AI|
|Wemos D1 Mini Pro V1.0.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|Winbond<br>W25Q128FVSS<br>16MB (128mbit)<br>ID 0x|Richtek<br>RT9013<br>500mA<br>marking:||These have the option of an external antenna if you resolder a certain 0 Ohm resistor.|
|Wemos D1 Mini Pro V1.1.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|Winbond<br>W25Q128FVSS<br>16MB (128mbit)<br>ID 0x|MicrOne<br>ME6211<br>500mA<br>marking: S2MD||These have the option of an external antenna if you resolder a certain 0 Ohm resistor.|
|Wemos D1 Mini V2<br>**clone**|<br>chip: ESP8266EX|<br>T25S32<br>4MB (32mbit)<br>ID 0x|Torex<br>XC6204D<br>150mA<br>marking: |Q2 2019<br>AliExpress|ESP shield marking: ESP8266MOD. No vendor marking.|
|D1 Mini V2<br>**Clone**|Do-It.AM<br>chip: ESP8266EX|XMC<br>QH32BHIG<br>4MB (32mbit)<br>ID 0x20<br>4016|Torex<br>XC6204B<br>150mA<br>marking: 4B2X|Q1 2019<br>AliExpress|Lots of these are BAD. If the device is unresponsive or slow, throw away or remove a specific cap. [See here](https://geekenargentina.wordpress.com/2019/10/08/esp8266-connectivity-troubleshooting/).<br> ESP shield marking: ESP8266MOD. Vendor marking: Do-It.AM.|
|NodeMCU V0.9<br>**Original**|AI-Thinker<br>chip: ESP8266EX|<br><br>4MB (32mbit)<br>ID 0x0E<br>4016|MaxLinear<br>SPX3819M5<br>500mA<br>marking: S2PC|Q4 2018<br>AliExpress|ESP shield marking: ESP8266MOD. Vendor marking: AI-Thinker|
|Wemos D1 Mini V2<br>**clone**|<br>chip: ESP8266EX|<br><br>4MB (32mbit)<br>ID 0xEF<br>4016|Torex<br>XC6204A<br>150mA<br>4A2D|Q3 2019<br>AliExpress 1|ESP shield marking: ESP8266MOD. No vendor marking.|
|Wemos D1 Mini V2<br>**clone**|<br>chip: ESP8266EX|<br><br>4MB (32mbit)<br>ID 0xEF<br>4016|Torex<br>XC6204B<br>150mA<br>4B2X|Q3 2019<br>AliExpress 2|ESP shield marking: ESP8266MOD. No vendor marking.|
|Wemos D1 Mini V2<br>**clone**|<br>chip: ESP8266EX|<br><br>4MB (32mbit)<br>ID 0x5E<br>4016|Torex<br>XC6204A<br>150mA<br>4A2D|Q3 2019<br>[AliExpress 3](https://www.aliexpress.com/store/4657022)|ESP shield marking: ESP8266MOD. No vendor marking.|
|Wemos D1 Mini V1.0<br>**I think this is a fake copy**|Wemos<br>chip: ESP8266|<br><br>4MB (32mbit)<br>ID 0xEF|Torex<br>XC6204A<br>150mA<br>marking: 4A2D |Q3 2019<br>AliExpress 4|ESP shield marking: ESP-8266. Vendor marking: Wemos.|
|Wemos D1 Mini Pro V1.0.0<br>**clone**|<br>chip: ESP8266EX|Winbond<br>25Q128JVS0<br>16MB (128mbit)<br>ID 0xEF<br>4018|MicrOne<br>ME6211<br>500mA<br>marking: S2RY|Q1 2019<br>AliExpress 5|These have the option of an external antenna if you resolder a certain 0 Ohm resistor.|
|Wemos D1 Mini V2<br>**clone**|<br>chip: ESP8266EX|<br>FT25H32S<br>4MB (32mbit)<br>ID 0x0E<br>4016|Torex<br>XC6204A<br>150mA<br>4A2D|Q1 2019<br>AliExpress 6|ESP shield marking: ESP8266MOD. No vendor marking.|
|Wemos D1 Mini V3<br>**clone**|<br>chip: ESP8266EX|Winbond<br>25Q32JVS10<br>4MB (32mbit)<br>ID 0xEF<br>4016|Torex<br>XC6204A<br>150mA<br>4A2D|Q1 2019<br>AliExpress 7|ESP shield marking: ESP8266MOD. No vendor marking.|
|Wemos D1 Mini V2<br>**clone**|<br>chip: ESP8266EX|XMC<br>QH32BHIG<br>4MB (32mbit)<br>ID 0x20<br>4016|Torex<br>XC6204A<br>150mA<br>4A2D|Q1 2019<br>AliExpress |ESP shield marking: ESP8266MOD. No vendor marking.|
