# FreeRTOS port for Raspberry Pi 3B:

This repository represent a fork branch of the main repository Forty-Tw0's FreeRTOS ported to raspberry pi 2B
https://github.com/Forty-Tw0/RaspberryPi-FreeRTOS

## How to build FreeRTOS port For Rasbperry pi 3B:
at the first step you need to clone the code located in [RaspberryPi-FreeRTOS](https://github.com/m-derakhshan/RaspberryPi_Port/tree/main/RaspberryPi-FreeRTOS) folder.  these codes are almost as same as the main repository codes. then follow steps bellow to generate port output
 - **Step One, Generate kernel7.img**
follow this [link](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) from developer.arm.com to download latest version of gcc-arm-none-eabi.
then open the project folder. open MakeFile with any editor you like. At the end of the file, try to edit kernel.elf: LDFLAGS with sutable relative gcc-arm-none-eabi address:
![MakeFile arm-none-eabi](https://s4.uupload.ir/files/screenshot_2021-07-22_084647_5peu.png)
Then open dbuild.config.mk and edit relative address of 'Toolchain' at the end of the file:
![dbuild.config.mk arm_none_eabi](https://s4.uupload.ir/files/screenshot_2021-07-22_085214_tkc.png)
now every thing is ready to build the output port. so open a terminal in the main folder and type 'make'. now you should get the output.
 - **Step Two, Raspberry Pi Porting**
now you have the FreeRTOS port for raspberry pi, it is just Kernel7.img. At this step we will see how to install the above mentioned file on Raspberry Pi and boot FreeRTOS.
For this perpuse, first download Raspberry Pi OS from [RaspberryPi.org](https://www.raspberrypi.org/software/operating-systems/#raspberry-pi-os-32-bit).
we recommend you to download lite version of Raspberry Pi OS.
the you need RaspberryPi Imager for booting Raspberry Pi OS. so follow [this link](https://www.raspberrypi.org/software/) and download sutable version of Raspberry Pi Imager based on you operating system.
now you have all necessory tools for booting your SD Card with Raspberry Pi OS.
so Insert your SD Card and open Raspberry Pi Imager.
![Raspberry Pi imager](https://s4.uupload.ir/files/screenshot_2021-07-22_091621_rsjl.png)
first by clicking on Choose OS, select the img file of Raspberry Pi OS Lite. then selecet your SD card. pay attention, the SD card will be formatted so make sure you don't have important info on that. then click on write and wait for process to be completed.

Congratulation! every thing is ready to start your FreeRTOS, copy the Kernel7.img generated in the step one and replace it with the one located in the boot drive of SD Card. power on your Raspberry Pi and your [main.c](https://github.com/m-derakhshan/RaspberryPi_Port/blob/main/RaspberryPi-FreeRTOS/Demo/main.c) programm will start!
