---
title: "Guide to Updating the Firmware on Your Voxelab Aquila 3D Printer using Alex Custom Firmware"
date: 2022-12-10
slug: "aquila-custom-firmware-guide"
description: "Step-by-step guide on how to update the firmware on your Voxelab Aquila 3D printer using Alex custom firmware. Includes instructions for identifying chip model and downloading appropriate firmware version."
keywords: ["aquila", "custom firmware", "voxelab", "alex firmware","3D printer"]
draft: false
tags: ["3D_Printing"]
math: false
toc: true
---



#### Guide Steps

1. Find out the chip model of your 3D printer
2. Download the right firmware version based on your 3D printer model 
3. Install it

## Find out the chip model of your 3D printer

The same model of the Aquila 3d printer came with a different motherboard chip. For example, the Voxelab Aquila X2 could have the H32 or N32 chip. And in some rare cases of early X2 printersthe G32 chip. Instead, the first model (Voxelab Aquila) could have a G32, N32 or H32 chip. If you want to be 100% sure you could read the text on the black motherboard chip(read NOTE for more). You need to find out what model you have on your machine.  

So you can find yourself in one of these following cases: 

* You have a **sticker** in front of the 3d printer with the model name (**H2** or **N32**)  
	
	>If you are in this situation, you can go to the second part of the guide with the model you just read in mind.
* You don't have a sticker

	>If this is the case, this means that you have a **G32** chip board.

***

NOTE:

&nbsp;&nbsp;&nbsp;&nbsp;It may happen that your motherboard has been replaced in case you bought the printer used or if it is a returned printer. So if        you want to be 100% sure you need to read the text on the black motherboard chip. You should find something like "GD32F103", in this case you have a      G32 chip model(You need to read the first part G[D]32).


## Download the right firmware version based on your 3d printer model

Now that you know what chip model you have, you need to download the printer and display firmware based on your 3d printer setup and preferences (The display firmware is the same for all the 3d printer chip models). Now fisrt follow the steps for the display firmware because it is the same for all chip models, and than follow the printer firmware steps based on your printer chip model:

### Display firmware instruction 

Download the display firmware zip file from this [github repository  direct download link](https://downgit.github.io/#/home?url=https://github.com/alexqzd/Marlin/tree/main/Display%20firmware), extract it on the desktop of your computer. Than you need to open it, and go in the **Display firmware** -> **Firmware Sets** folder, go and copy the ***DWIN_SET (Voxelab Red)*** folder on the desktop. Rename it ***DWIN_SET***. Later, this folder will be put on the SD card to flash the display firmware.

### Printer firmware instruction 
For **N32** and **G32** chips, follow these steps:

* You have a stock machine with no BL Touch (sensor mounted on the hotend to perform auto bed leveling) install. From the factory, it comes without the BL Touch.

	In this case, since you have a stock machine you need to download the **Manual Mesh** firmware file named with the same chip model of your machine(N32 or G32) of the **v1.3.5** firmware release(latest stable verision) from this [github repository](https://github.com/alexqzd/Marlin/releases). For example, if you have a N32 chip machine, you will download the ***ManualMesh-5x5-N32.bin*** file. Now if you have follow all the steps, on your desktop you should have the **.bin** file and the **DWIN_SET** folder. If this is the case, go to the final part of the guide.

* You have install a Bl Touch sensor

	In this case, since you have a stock machine you need to download the **BLTouch** firmware file named with the same chip model of your machine(N32 or G32) of the **v1.3.5** firmware release(latest stable verision) from this [github repository](https://github.com/alexqzd/Marlin/releases). For example, if you have a N32 chip machine, you will download the ***BLTouch-5x5-N32.bin*** file. Now if you have follow all the steps, on your desktop you should have the **.bin** file and the **DWIN_SET** folder. If this is the case, go to the final part of the guide.

For the **H32** chip, follow these steps:

* You have a stock machine with no BL Touch (sensor mounted on the hotend to perform auto bed leveling) installed. From the factory, it comes without the BL Touch.

	In this case, since you have a stock machine you need to download the **Manual Mesh** firmware file named with the same chip model of your machine(N32 or G32) of the **v1.3.6** firmware release(latest stable verision) from this [github repository](https://github.com/alexqzd/Marlin-H32/releases). For example, if you have a N32 chip machine, you will download the ***ManualMesh-5x5-H32.bin*** file. Now if you have follow all the steps, on your desktop you should have the **.bin** file and the **DWIN_SET** folder. If this is the case go to the final part of the guide.
  

* You have install a Bl Touch senosr


	In this case, since you have a stock machine you need to download the **BLTouch** firmware file named with the same chip model of your machine(N32 or G32) of the **v1.3.6** firmware release(latest stable verision) from this [github repository](https://github.com/alexqzd/Marlin-H32/releases). For example, if you have a N32 chip machine, you will download the ***BLTouch-5x5-H32.bin*** file. Now if you have follow all the steps, on your desktop you should have the **.bin** file and the **DWIN_SET** folder. If this is the case, go to the final part of the guide.

***

NOTE:
- If you are installing the same firmware as already previously installed, this can cause the chip to skip the update. In this case you can simply change the .bin file name.
- If you are installing the firmware on a Creality motherboard then the bootloader looks for the .bin file in the root folder instead of the firmware folder.

TERM DICTIONARY:
- Default = firmware version does not contain any mesh or level functionality.
- Manual Mesh = firmware version let you moves the nozzle to each point of the gird and you let the printer know when the nozzle is a the right distance from the bed using a paper sheet.
- UBL = stand for Unified Bed Leveling, is a new advanced leveling system that lets you edit and tilt the mesh using the same technique as manual mesh. Also if you have a BLTouch you can combine it with manual level and fine tune the unreachable area of the bed.
- HS = stand for Hight Speed(In this firmware version the BLTouch keeps the pin extended between probes to save time).

## Install it

Plug in the 3d printer SD card into your computer.
Format the SD card in FAT32 format, and make sure the unit size is set to **4096**.
Drag and drop into the SD card the **DWIN_SET** folder.
Now on the SD card, you need to create a folder named **firmware** in lower case, and inside it you are going to put the firmware **.bin** file that you previously downloaded. You should have on the SD card two folders, one named ***firmware*** and the second one named ***DWIN_SET***.
Now with the 3d printer turn OFF, insert the SD card in the 3d printer's front SD card reader, and then power ON the 3d printer. Now wait until you see a check mark on the screen. After this, you can turn OFF the printer.
Now you need to plug the SD card on the back of the display, where there is the SD reader. To access it, you will have to remove the display from the printer and remove all the screws on the back of the display. Once you've done that, turn ON the printer and wait until you see an orange screen.
After you see the orange screen, turn OFF the printer and remove the SD card from the display. Put the display back together  without the SD card. After this, you can finally turn ON the printer, and you should have the brand new custom firmware running on your 3d printer.


Enjoy printing!
