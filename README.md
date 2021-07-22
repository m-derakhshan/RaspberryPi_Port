# FreeRTOS port for Raspberry Pi 3B:

This repository represent a fork branch of the main repository Forty-Tw0's FreeRTOS ported to raspberry pi 2B
https://github.com/Forty-Tw0/RaspberryPi-FreeRTOS

## How to build FreeRTOS port For Rasbperry pi 3B:
at the first step you need to clone the code located in [RaspberryPi-FreeRTOS](https://github.com/m-derakhshan/RaspberryPi_Port/tree/main/RaspberryPi-FreeRTOS) folder.  these codes are almost as same as the main repository codes. then follow steps bellow to generate port output
 - **step one, generate kernel7.img**
follow this [link](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) from developer.arm.com to download latest version of gcc-arm-none-eabi.
then open the project folder. open MakeFile with any editor you like. At the end of the file, try to edit kernel.elf: LDFLAGS with sutable relative gcc-arm-none-eabi address:
![MakeFile arm-none-eabi](https://s4.uupload.ir/files/screenshot_2021-07-22_084647_5peu.png)
Then open dbuild.config.mk and edit relative address of 'Toolchain' at the end of the file:
![dbuild.config.mk arm_none_eabi](https://s4.uupload.ir/files/screenshot_2021-07-22_085214_tkc.png)
now every thing is ready to build the output port. so open a terminal in the main folder and type 'make'. you should get the output.
 
