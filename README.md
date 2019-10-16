# Wemos: the Clone Wars
List of Wemos and other ESP8266 clone boards


## Introduction
For several of my projects I use a lot of ESP8266 boards like the Wemos D1 Mini.<br>
Aside from the 'original' Wemos D1 Mini from Wemos/Lolin, there are a  of clones. These are copies of the original.<br>
Usually these clones work just fine for most purposes, but at some point I started to run into specific issues with some of these boards.<br>
<br>
Problems include a non-responsive or slow web interface, intermittent USB connections, bad Wi-Fi reception, underpowered LDO etc.<br>
<br>
If you Google around a lot of people have problems of some sort:<br>
[Problematic Do-It.AM modules](https://geekenargentina.wordpress.com/2019/10/08/esp8266-connectivity-troubleshooting/)<br>
[Underpowered LDO's (Reddit Post)](https://www.reddit.com/r/esp8266/comments/9iizx4/warning_clone_wemos_d1_minis_with_only_150ma_33v/)<br>
etc.<br>
<br>
My experience is that even when clones look identical, often they are not. Even if they have the same marking on the RF shield, they might have a different flash chip. Even if you buy the same article number from the same supplier you might not always get the same boards.<br>
Also if you buy these from Ebay, AliExpress, DX etc you almost never get the exact same board as is in the pictures. Most of the stores show an image of a AI-Thinker module but you never get these. It's usually a 'generic' clone without a vendor ID.
<br>
With the list below I want to make an overview of those different boards.<br>
<br>
With `esptool.py flash_id` you can get all parameters of the flash. These are listed as below:<br>

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


Board type | Vendor and ESP | Flash | LDO | Purchased | Remarks | Image
--- | --- | --- | --- | --- | --- | ---
|Wemos D1 Mini V3.1.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|Winbond<br>W25Q32FVSS<br>4MB (32mbit)<br>ID 0xEF|MicrOne<br>ME6211<br>500mA<br>marking: S2RY|Q2 2019<br>[AliExpress: Lolin offical store](https://lolin.aliexpress.com/store/1331105)|This is the best original Wemos D1 Mini|
|Wemos D1 Mini V3.0.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|Winbond<br>W25Q32FVSS<br>4MB (32mbit)<br>ID 0x|MicrOne<br>ME6211<br>500mA<br>marking: S2MD|||
|Wemos D1 Mini V2.2.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|4MB (32mbit)<br>ID 0x|MicrOne<br>ME6211<br>500mA<br>marking: ||ESP shield marking: ESP-12S. Vendor marking: AI|
|Wemos D1 Mini V2.3.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|4MB (32mbit)<br>ID 0x|MicrOne<br>ME6211<br>500mA<br>marking:||ESP shield marking: ESP-12S. Vendor marking: AI|
|Wemos D1 Mini Pro V1.0.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|Winbond<br>W25Q128FVSS<br>16MB (128mbit)<br>ID 0x|Richtek<br>RT9013<br>500mA<br>marking:||These have the option of an external antenna if you resolder a certain 0 Ohm resistor.|
|Wemos D1 Mini Pro V1.1.0<br>**Original**|Lolin/Wemos<br>chip: ESP8266EX|Winbond<br>W25Q128FVSS<br>16MB (128mbit)<br>ID 0x|MicrOne<br>ME6211<br>500mA<br>marking: S2MD||These have the option of an external antenna if you resolder a certain 0 Ohm resistor.|
|Wemos D1 Mini V2<br>**clone**|<br>chip: ESP8266EX|<br>T25S32<br>4MB (32mbit)<br>ID 0x|Torex<br>XC6204D<br>150mA<br>marking: |Q2 2019<br>AliExpress|ESP shield marking: ESP8266MOD. No vendor marking.|
|D1 Mini V2<br>**Clone**|Do-It.AM<br>chip: ESP8266EX|XMC<br>QH32BHIG<br>4MB (32mbit)<br>ID 0x20|Torex<br>XC6204B<br>150mA<br>marking: 4B2X|Q1 2019<br>AliExpress|Lots of these are BAD. If the device is unresponsive or slow, throw away or remove a specific cap. [See here](https://geekenargentina.wordpress.com/2019/10/08/esp8266-connectivity-troubleshooting/).<br> ESP shield marking: ESP8266MOD. Vendor marking: Do-It.AM.|
|NodeMCU V0.9<br>**Original**|AI-Thinker<br>chip: ESP8266EX|<br><br>4MB (32mbit)<br>ID 0x0E<br>4016|MaxLinear<br>SPX3819M5<br>500mA<br>marking: S2PC|Q4 2018<br>AliExpress|ESP shield marking: ESP8266MOD. Vendor marking: AI-Thinker|
|Wemos D1 Mini V2<br>**clone**|<br>chip: ESP8266EX|<br><br>4MB (32mbit)<br>ID 0xEF<br>4016|Torex<br>XC6204A<br>150mA<br>4A2D|Q3 2019<br>AliExpress 1|ESP shield marking: ESP8266MOD. No vendor marking.|
|Wemos D1 Mini V2<br>**clone**|<br>chip: ESP8266EX|<br><br>4MB (32mbit)<br>ID 0xEF<br>4016|Torex<br>XC6204B<br>150mA<br>4B2X|Q3 2019<br>AliExpress 2|ESP shield marking: ESP8266MOD. No vendor marking.|
|Wemos D1 Mini V2<br>**clone**|<br>chip: ESP8266EX|<br><br>4MB (32mbit)<br>ID 0x5E<br>4016|Torex<br>XC6204A<br>150mA<br>4A2D|Q3 2019<br>[AliExpress 3](https://www.aliexpress.com/store/4657022)|ESP shield marking: ESP8266MOD. No vendor marking.|
|Wemos D1 Mini V1.0<br>**I think this is a fake copy**|Wemos<br>chip: ESP8266|<br><br>4MB (32mbit)<br>ID 0xEF|Torex<br>XC6204A<br>150mA<br>marking: 4A2D |Q3 2019<br>AliExpress 4|ESP shield marking: ESP-8266. Vendor marking: Wemos.|
|Wemos D1 Mini Pro V1.0.0<br>**clone**|<br>chip: ESP8266EX|Winbond<br>25Q128JVS0<br>16MB (128mbit)<br>ID 0xEF<br>4018|MicrOne<br>ME6211<br>500mA<br>marking: S2RY|Q1 2019<br>AliExpress 5|These have the option of an external antenna if you resolder a certain 0 Ohm resistor.|
|Wemos D1 Mini V2<br>**clone**|<br>chip: ESP8266EX|<br>FT25H32S<br>4MB (32mbit)<br>ID 0x0E<br>4016|Torex<br>XC6204A<br>150mA<br>4A2D|Q1 2019<br>AliExpress 6|ESP shield marking: ESP8266MOD. No vendor marking.|
|Wemos D1 Mini V3<br>**clone**|<br>chip: ESP8266EX|Winbond<br>25Q32JVS10<br>4MB (32mbit)<br>ID 0xEF<br>4016|Torex<br>XC6204A<br>150mA<br>4A2D|Q1 2019<br>AliExpress 7|ESP shield marking: ESP8266MOD. No vendor marking.|
