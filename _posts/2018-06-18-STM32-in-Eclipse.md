---
layout: post
title: "STM32 in Eclipse" 
date:   2018-06-18
categories: [general, STM32]
tags: [STM32, C, Nucleo]
description: STM32 in Eclipse.
---

## Install the required software.

You must install the following package:
* STM32CubeMX
* Eclipse-cpp
* Openocd
* Gdb
* Stlink

---

## Create and setting a simple project in STM32CubeMX.

Select the chip you are using:

![STM32CubeMX_ChoseChip](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/STM32CubeMX_ChoseChip.png) 

In the "Pinout->SYS-> Debug" select "Serial Wire":

![STM32CubeMX_Enable_Debug](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/STM32CubeMX_Enable_Debug.png) 

In the "Clock Configuration" set HCLK:

![STM32CubeMX_Clock](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/STM32CubeMX_Clock.png) 

Open "Project->Project Settings", or use hotkey "Alt+P".
Set "Project Name" and "Project Location, select "Makefile" as "Toolchain/IDE".
Press "OK".

![STM32CubeMX_STM32CubeMX_ProjectSetting](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/STM32CubeMX_ProjectSetting.png) 

Press "Ctrl+Shift+G" for generate source code.

---

## Import project in eclipse.

Select "File/New/Makefile Project with Existing Code".

Write "Project Name" and "Existing Code Location".
Languages "C".
Toolchain for indexer Settings "none".
Press "Finish".

![Eclipse_Create_Project](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_Create_Project.png) 

---

## Preparing Eclipse for work.

Select "Help->Eclipse Marketplace->Search->Find"
Find and install "GNU MCU Eclipse"

![Eclipse_Marketplace](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_Marketplace.png) 

Select "Run->External Tools->External Tools Configuration...
Select "New launch configuration"
Create configuration for run openocd, "Openocd" is better to take with "github"
For find locations use command "which"

	[oleg@oleg-pc ~]$ which openocd
	            /usr/local/bin/openocd

![Eclipse_ExternalTools_openocd_0](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_ExternalTools_openocd_0.png) 

![Eclipse_ExternalTools_openocd_1](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_ExternalTools_openocd_1.png) 

![Eclipse_ExternalTools_openocd_2](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_ExternalTools_openocd_2.png) 

![Eclipse_ExternalTools_openocd_3](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_ExternalTools_openocd_3.png) 

![Eclipse_ExternalTools_openocd_4](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_ExternalTools_openocd_4.png) 

Create configuration for run "st-linkv2 erase"

![Eclipse_ExternalTools_st-link_erase_0](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_ExternalTools_st-link_erase_0.png)

Leave the remaining parameters as default.
Create configuration for run "st-linkv2 write"

![Eclipse_ExternalTools_st-link_write_0](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_ExternalTools_st-link_write_0.png)

Leave the remaining parameters as default.
Select "Run->Debug Configurations..."
Select "GDB Hardware Debugging", select "New launch configuration"

![pictures/Eclipse_DebugConfigurations_GDB_0](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_DebugConfigurations_GDB_0.png)

![pictures/Eclipse_DebugConfigurations_GDB_1](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_DebugConfigurations_GDB_1.png)

![pictures/Eclipse_DebugConfigurations_GDB_2](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_DebugConfigurations_GDB_2.png)

![pictures/Eclipse_DebugConfigurations_GDB_3](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_DebugConfigurations_GDB_3.png)

![pictures/Eclipse_DebugConfigurations_GDB_4](http://127.0.0.1:4000/pictures/STM32-in-Eclipse/Eclipse_DebugConfigurations_GDB_4.png)

## Run debugging on the hardware.

Select "Run->External Tools->openocd".
Select "Run-> Debug Configurations...-> GDB Hardware Debugging".
Select the previously created configuration.
Select "Debug".

![Eclipse_Run_Debugging]()

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
