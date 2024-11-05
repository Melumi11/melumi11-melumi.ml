---
layout: post
title: MKWii Item Rain install guide (gecko code)
date: 2024-06-17 11:59:00-0400
description: Get item rain in Mario Kart Wii on Dolphin, USB Loader GX
tags: games
categories: games
giscus_comments: true
related_posts: false
thumbnail: assets/img/item_rain.png
toc:
  beginning: true
---

### Introduction

[Read my cross-posted reddit post here.](https://www.reddit.com/r/MarioKartWii/comments/1diafqnitem_rain_install_guide_dolphin_usb_loader_gx/)

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/item_rain.png" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Luigi targets bullets and stars as items fall in Bowser's castle
</div>

<br>

Want to play Item Rain without CTGP, on Dolphin, or without your disk? This guide will explain how to get Item Rain using Gecko codes. Gecko codes can be used for other mods and cheats as well.

All of the codes below are for NTSC-U (North American version) but you can follow similar steps for other regions and I can help if you leave a comment. I'm using the version of Item Rain which drops bullet bills, stars, shocks, etc. along with the regular items.

<br>

### Dolphin Steps:

* Enable cheats in Config -> General -> Basic Settings
* Right click Mario Kart -> Properties -> Gecko Codes
* Add the codes below
* Play the game

### USB Loader GX Steps:

* Create a "RMCE01.gct" file using [https://mariokartwii.com/gct/](https://mariokartwii.com/gct/) and the codes below. The game ID is RMCE01 (for NTSC-U) and add the codes below before downloading the GCT file.
* Place it at /codes/RMCE01.gct in your Wii's SD card. (/codes/RMCE01.gct is the file path in the SD card, so make a folder called codes.)
* In USB Loader GX (or whatever you're using) turn on Ocarina and make sure it's enabled for Mario Kart Wii.
* Now Item Rain should be enabled in every game. Turn off Ocarina or remove the gct file to turn Item Rain off.
* Your game may crash. Mine does occasionally. Hold the Wii's power button to restart :(

<br>

### Gecko Codes:

* I will paste my Gecko codes below and explain where I got them after.
* ***These codes only work on NTSC-U (North American version).*** For other regions, follow my [explanations](#codes-explanations) for your region. If there is interest in comments, I may help out
* All codes are required except for "No Item Boxes" as is explained below
* Any readable text is not part of the gecko codes, including the names/titles

#### Item Rain: ([explanation](#item-rain))
```
04000A10 00000000
04000A14 80000000
04000A18 BF800000
04000A34 44BB8000
06000A50 00000018
43300000 00000000
3EF00000 42C80000
42480000 C2C80000
06000AA0 00000038
809BD508 80011110
809BD118 809BEE20
8078CDF8 8078D1E4
807959DC 8079A928
8029FD80 8029FDB0
80005F34 8000E7B4
804250D4 8029FD69
C2531134 00000070
901D0048 546307FE
2C030001 40A2036C
3F808000 807C0AA0
80630000 80630000
81030000 2C08006A
41820350 2C08006B
41820348 2C08006E
41820340 2C08006F
41820338 807D0048
80BC0A20 7C032800
41A20328 907C0A20
2C030002 40A2003C
3860FFFF 907C0A70
807C0AA0 80630000
80630000 80630000
2C03002E 41820014
7C8C42E6 908D8038
909C0A68 4800000C
807C0A68 906D8038
807C0AA4 7C6903A6
4E800421 2C031480
39400000 418000B8
2C032900 39400001
418000AC 2C033D80
39400002 418000A0
2C034000 39400005
41800094 2C034280
3940000A 41800088
2C034500 3940000B
4180007C 2C035300
39400007 41800070
2C036100 39400003
41800064 2C036F00
39400009 41800058
2C037100 39400004
4180004C 2C037300
39400006 41800040
2C037900 39400008
41800034 2C037F00
3940000C 41800028
2C037F80 39400008
41800008 3940000C
3C80809C 8884F0B3
2C040001 41820008
3940000D 38800000
909C0A00 809C0AA8
80840000 80840008
80C4FFF4 2C060009
41800018 39200002
80BC0AD0 99250000
80BC0AD4 99250000
1CE60008 38E7FFFF
90FC0A90 80FC0A70
38C6FFFF 7C073000
40800010 38E70001
90FC0A70 4800000C
38E00000 90FC0A70
2C080068 41A00020
2C080077 41810018
811C1500 38C00248
7D0833D6 7C074000
40A20190 1CE70248
7D072214 3D208000
3CA08000 38E00000
C07C0A58 C09C0A5C
C0BC0A60 C0DC0A64
C8E90A50 2C070001
41820044 3C804330
90890A40 807C0AA4
7C6903A6 4E800421
2C034000 41800018
3863C000 90690A44
C8090A40 EC270028
48000010 90690A44
C8090A40 EC203828
D0290A30 80C80024
90C50A04 C0050A04
C0250A30 2C070001
41820030 C0480034
FC022040 4081000C
FC402090 48000010
FC023040 40A00008
FC403090 EC420172
EC2100F2 EC00102A
EC00082A D0050A04
2C070001 41820008
39290008 38E70001
39080004 38A50004
4081FF54 813C0AB0
80DC0A70 38BC0A00
38E50004 809C0AAC
80840000 38840048
1C6A0024 7C632214
38800001 39000000
7D2903A6 4E800421
80BC0AB4 7CA903A6
80BC0AAC 809C0A00
2C040000 4182006C
80640004 80A50000
38A50048 1C630024
7C651A14 4E800421
80BC0AB8 389C0A04
807C0A00 7CA903A6
4E800421 38BC0A10
807C0A00 38800000
80FC0AC4 80DC0AC0
811C0ABC 7D0903A6
4E800421 807C0A00
80A30004 2C050009
40A20010 80A30170
38A50014 90A30170
60000000 00000000
04653A20 28040007
0464EDA0 38600300
C2782B50 00000002
2C030000 4D820020
8003000C 00000000
C2657524 00000006
887B001B 2C030007
41A2001C 2C030003
41A20014 2C030004
41A2000C 386400C8
4800000C 7C832378
48000004 00000000
C2657254 00000007
3C608000 80630A90
2C050007 41A2001C
2C050003 41A20014
2C050004 41A2000C
38C600C8 4800000C
7CC61A14 48000004
387F0004 00000000
C27E4DDC 00000002
3FE08000 93BF1500
3BE00000 00000000
C2655EE4 00000005
80DE0004 7C1F3000
41810018 3CC08000
80C60AC8 7CC903A6
4E800421 48000008
3BE00000 60000000
C2797FE8 00000005
815F0004 2C0A0009
40A20018 2C1C0002
40820010 394037AB
3CA08000 91450AE8
38BF0044 00000000
C2797FFC 00000005
815E0004 2C0A0009
40A20018 2C1D0002
40A20010 394037AB
3CA08000 91450AE8
38BE0044 00000000
C2798C58 00000004
3CA08000 80850AE8
2C0437AB 38800000
90850AE8 41A20008
38800001 00000000
0478E00C 60000000
0479DC68 60000000
C26577DC 0000000F
3CC08000 80C60ACC
7CC903A6 4E800421
2C030000 41A2005C
A0790004 A0970000
7C032000 4181004C
38792400 1C9C0300
7C641850 1C960020
7C641850 1C9C0060
7C632214 1C960004
7C632214 38800000
90830000 88B9001C
3C608000 80630AC8
7C6903A6 7EE4BB78
38790004 4E800421
60000000 00000000
0453B328 60000000
008A126F 00000022
008A0F67 00000022
008A09CF 00000022
008A0D2B 00000019
008A0ACB 00000019
008A1063 00000005
```

#### Disable Item Poof: ([explanation](#disable-item-poof))
```
0478D5B4 60000000
```

#### All Items Can Land v2: ([explanation](#all-items-can-land-v2))
```
06001600 0000008C
38E00008 48000028
38E0000B 48000020
38E0000C 48000018
38E0000D 48000010
38E00004 48000008
38E0000F 9421FFF0
7C0802A6 90010014
3C60809C 8063EE20
80630014 1C980248
7C632214 80830090
38840001 90830090
3C80809B 6084EEB0
1CE7001C 7C84382E
2C040000 4182000C
7C8903A6 4E800421
3860FFFF 80010014
7C0803A6 38210010
4E800020 00000000
0479D6B8 60000000
0478DD24 38600000
08787EE4 39800001
20030004 FFE00000
048B0D80 80001600
048B0D98 80001608
088B0DB0 80001610
2003000C 00000008
```

#### Good Item Limits: ([explanation](#good-item-limits))
```
008CDB6F 0000000C
008CDC47 0000000C
008CE4A7 0000000C
008CE3F7 0000000C
008CE5A7 00000006
008CD6EF 00000006
008CE33F 00000006
```

#### Bad Item Limits: ([explanation](#bad-item-limits))
```
048A1060 00000012
048A0AC8 00000012
048A126C 00000012
048A0F64 00000012
048A0D28 00000012
048A09CC 00000012
```

#### No Item Boxes: ([explanation](#no-item-boxes))
```
04814D68 38800000
```

<br>

## Codes explanations:

### Item Rain:

* Source: [https://mariokartwii.com/showthread.php?tid=1456](https://mariokartwii.com/showthread.php?tid=1456)
* I filled in XXXXXXXX, YYYYYYYY, and ZZZZZZZZ using the values that the author suggests on page 4. (X = 3F400000, Y = 42480000, Z = 44BB8000)
* I **removed the last 2 lines** which prevents a crash when used with "Disable Item Poof" (important), and I move the lines to "Good Item Limiter" where I use different values which crash less.

### Disable Item Poof:

* Source: [https://mariokartwii.com/showthread.php?tid=1716](https://mariokartwii.com/showthread.php?tid=1716)
* Without this code, items will disappear off the ground after a very short period of time. IDK what CLF78 did, but it's good. Feel free to test without it.

### All Items Can Land v2:

* Source: [https://mariokartwii.com/showthread.php?tid=1720](https://mariokartwii.com/showthread.php?tid=1720)

>This code lets every item (except the Thundercloud) land on the floor when dropped. They will activate when a racer drives over them, and their effects will be identical to if the user actually fired the item themselves.

* Without this code, the OP items (bullets, mega mushrooms, etc.) will disappear instantly. Goated code.

### Good Item Limits:
- Source: [https://mariokartwii.com/showthread.php?tid=405](https://mariokartwii.com/showthread.php?tid=405)
- Changes how many of each good item can exist at one time. This is meant to allow more to be on the ground at once. I tweaked these but you can change them if you wish. Having more items means it's more likely for the game to crash or bug out. The numbers are the second half of each line.

Reference:
```
Star
008CDB6F 000000XX
 
Mushroom
008CD63F 000000XX
 
Lightning
008CDC47 000000XX
 
Mega Mushroom
008CE4A7 000000XX
 
Bullet Bill
008CE3F7 000000XX
 
POW Block
008CE5A7 000000XX
 
Golden Mushroom
008CD6EF 000000XX
 
Blooper
008CE33F 000000XX
 
Thundercloud
008A2E7B 000000XX
```

```
Look up decimal to hex for more numbers
9:
00000009
10:
0000000A
12:
0000000C
15:
0000000F
16:
00000010
20:
00000014
```
### Bad Item Limits:
- Source: [https://mariokartwii.com/showthread.php?tid=242](https://mariokartwii.com/showthread.php?tid=242)
- Changes how many of each bad item can exist at one time. Having more items means it's more likely for the game to crash or bug out. Same as above really

Reference:
```
Blue Shell
048A1060 000000XX
Bob-omb
048A0AC8 000000XX
Green Shell
048A126C 000000XX
Red Shell
048A0F64 000000XX
Fake Item Box
048A0D28 000000XX
Banana
048A09CC 000000XX
Thunder Cloud (don't use)
048A2E78 (don't use)
```
### No item boxes:
- Source: [https://mariokartwii.com/showthread.php?tid=169](https://mariokartwii.com/showthread.php?tid=169)
- Doesn't 100% work on some tracks (like Toad's Factory)
- I removed item boxes because I think boxes make the game crash more. Test it yourself if you'd like.

<br>

Thanks for reading my post. Please leave a comment or reach out if you have any questions :)