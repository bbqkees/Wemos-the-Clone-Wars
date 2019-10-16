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


Board type | Vendor and ESP | Flash | LDO | Purchased | Remarks | Image
--- | --- | --- | --- | --- | --- | ---
|Wemos D1 Mini V3.1.0<br>**Original**|Lolin/Wemos<br>ID 0x<br>chip: ESP8266EX|Winbond<br>W25Q32FVSS<br>4MB (32mbit)<br>ID 0x|MicrOne<br>ME6211<br>500mA<br>marking: S2MD|Q2 2019<br>[AliExpress: Lolin offical store](https://lolin.aliexpress.com/store/1331105)|This is the best original Wemos D1 Mini|
|Wemos D1 Mini V2<br>**clone**|<br>ID 0x<br>chip: ESP8266EX|<br>T25S32<br>4MB (32mbit)<br>ID 0x|<br><br>500mA<br>marking: |Q2 2019<br>AliExpress|ESP shield marking: ESP8266MOD. No vendor marking.|
|Wemos D1 Mini V2<br>**clone**|<br>ID 0x<br>chip: ESP8266EX|XMC<br>QH32BHIG<br>4MB (32mbit)<br>ID 0x|<br><br>500mA<br>marking: |Q3 2019<br>AliExpress|ESP shield marking: ESP8266MOD. No vendor marking.|
|Wemos D1 Mini V2<br>**clone**|<br>ID 0x<br>chip: ESP8266EX|<br><br>4MB (32mbit)<br>ID 0x|<br><br>500mA<br>marking: |Q3 2019<br>AliExpress||
|Wemos D1 Mini V1.0<br>**I think this is a fake copy**|Wemos<br>ID 0x<br>chip: ESP8266|<br><br>4MB (32mbit)<br>ID 0x|<br><br>500mA<br>marking: |Q3 2019<br>AliExpress|ESP shield marking: ESP8266MOD. Vendor marking: Wemos.|
|D1 Mini V2<br>**Clone**|Do-It.AM<br>ID 0x<br>chip: ESP8266EX|XMC<br>QH32BHIG<br>4MB (32mbit)<br>ID 0x|<br><br>150mA<br>marking: 4ABC|Q1 2019<br>AliExpress|Lots of these are BAD. If the device is unresponsive or slow, throw away or remove a specific cap. [See here](https://geekenargentina.wordpress.com/2019/10/08/esp8266-connectivity-troubleshooting/).<br> ESP shield marking: ESP8266MOD. Vendor marking: Do-It.AM.|
|NodeMCU V0.9<br>**Original**|AI-Thinker<br>ID 0x<br>chip: ESP8266|<br><br>4MB (32mbit)<br>ID 0x|MaxLinear<br>SPX3819M5<br>500mA<br>marking: S2PC|Q4 2018<br>AliExpress|ESP shield marking: ESP8266MOD. Vendor marking: AI-Thinker|
