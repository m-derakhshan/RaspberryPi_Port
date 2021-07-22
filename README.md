# FreeRTOS port for Raspberry Pi 3B:

This repository represent a fork branch of the main repository Forty-Tw0's FreeRTOS ported to raspberry pi 2B

https://github.com/Forty-Tw0/RaspberryPi-FreeRTOS

## How to build FreeRTOS port For Raspberry pi 3B:
At the first step, you need to clone the code located in [RaspberryPi-FreeRTOS](https://github.com/m-derakhshan/RaspberryPi_Port/tree/main/RaspberryPi-FreeRTOS) folder. These codes are almost as same as the primary repository codes. then follow the steps below to generate port output
 - **Step One, Generate kernel7.img**

Follow this [link](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) from developer.arm.com to download the latest version of gcc-arm-none-eabi.
Then open the project folder. Open MakeFile with any editor you like. At the end of the file, try to edit kernel.elf: LDFLAGS with suitable relative gcc-arm-none-eabi address:

![MakeFile arm-none-eabi](https://s4.uupload.ir/files/screenshot_2021-07-22_084647_5peu.png)

Then open dbuild.config.mk and edit the relative address of 'Toolchain' at the end of the file:

![dbuild.config.mk arm_none_eabi](https://s4.uupload.ir/files/screenshot_2021-07-22_085214_tkc.png)

now everything is ready to build the output port. So open a terminal in the main folder and type 'make'. Now you should get the output.
 - **Step Two, Raspberry Pi Porting**
 
Now you have the FreeRTOS port for raspberry pi; it is just Kernel7.img. At this step, we will see how to install the file as mentioned above on Raspberry Pi and boot FreeRTOS.
For this purpose, first, download Raspberry Pi OS from [RaspberryPi.org](https://www.raspberrypi.org/software/operating-systems/#raspberry-pi-os-32-bit).
We recommend you download the lite version of Raspberry Pi OS.
It would help if you had RaspberryPi Imager for booting Raspberry Pi OS. so follow [this link](https://www.raspberrypi.org/software/) and download a suitable version of Raspberry Pi Imager based on your operating system.
Now you have all the necessary tools for booting your SD Card with Raspberry Pi OS.
So Insert your SD Card and open Raspberry Pi Imager.

<p align="center">
<img src="https://s4.uupload.ir/files/screenshot_2021-07-22_091621_rsjl.png" alt="drawing" width="500"/>
</p>


First, by clicking on Choose OS, select the img file of Raspberry Pi OS Lite. then selecet your SD card. Be aware your SD card will be formatted, so make sure you don't have important info on that. Then click on write and wait for the process to be completed.

Congratulations! Everything is ready to start your FreeRTOS, copy the Kernel7.img generated in step one and replace it with the one located in the boot drive of the SD Card. Power on your Raspberry Pi, and your [main.c](https://github.com/m-derakhshan/RaspberryPi_Port/blob/main/RaspberryPi-FreeRTOS/Demo/main.c) program will start!
