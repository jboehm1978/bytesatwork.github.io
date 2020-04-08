
# byteWIKI V1.0 
## Introduction
***Welcome to the byteWIKI of bytes at work AG!***
The byteWIKI provides important und helpful information related to our products. The byteWIKI is constantly updated with the newest Software- and Hardware-Versions. The byteWIKI ensures a clear overview of all necessary connections. Furthermore, you will find information how to create a bootable SD-Card with a prebuilt image by bytesatwork and how to install the prebuilt toolchain with an example. It also delivers links to the provided Yocto-layers.
It is splitted into four different sections: ``First Start / Hardware Preparation / Software Development / Hardware Development``
- - - -
| **Rev. History:** |
|:------------------|
| *_30.03.20: First Edition_*|
- - - -
## Table of contents
- [First Start](#first-start)
- [Hardware Preperation](#hardware-preperation)
- [Software Development](#software-development)
  * [1. Where do you get the toolchain?](#1.-where-do-you-get-the-toolchain?)
    + [1.1 byteDEVKIT](#1.1-bytedevkit)
    + [1.2 bytePANEL](#1.2-bytepanel)
  * [2. Where do you get the Image for your SD-Card?](#2.-where-do-you-get-the-image-for-your-sd-card?)
    + [2.1 byteDEVKIT](#2.1-bytedevkit)
    + [2.2 bytePANEL](#2.2-bytepanel)
  * [3. How do you flash the Image?](#3.-how-do-you-flash-the-image?)
    + [3.1 byteDEVKIT](#3.1-bytedevkit)
    + [3.2 bytePANEL](#3.2-bytepanel)
  * [4. How do you build an Image?](#4.-how-do-you-build-an-image?)
    + [4.1 byteDEVKIT](#4.1-bytedevkit)
    + [4.2 bytePANEL](#4.2-bytepanel)
  * [5. How do you build a toolchain?](#5.-how-do-you-build-a-toolchain?)
    + [5.1 byteDEVKIT](#5.1-bytedevkit)
  * [6. How do you install the toolchain?](#6.-how-do-you-install-the-toolchain?)
  	+ [6.1 byteENGINE AM335x](#6.1-byteengine-am335x)
  	+ [6.2 byteENGINE STM32MP1x](#6.2-byteengine-stm32mp1x)
  * [7. How do you use the toolchain?](#7.-how-do-you-use-the-toolchain?)
  	+ [7.1 byteENGINE AM335x](#7.1-byteengine-am335x)
  	+ [7.2 byteENGINE STM32MP1x](#7.2-byteengine-stm32mp1x)
- [Hardware Development](#hardware-development)
  * [byteENGINE AM335x](#byteengine-am335x)
  * [byteENGINE STM32MP1x](#byteengine-stm32mp1x)




## First Start
This describes the initial startup of the SOM, dev-Kit.

## Hardware Preperation
What do I have to do, before starting fort he first time.
* Bild 1: ![Alt-Text](pfad/bild.png)
* Bild 2: ![Alt-Text](pfad/bild.png)
* Bild 3: ![Alt-Text](pfad/bild.png)

<iframe width="560" height="315" src="https://www.youtube.com/embed/F-7W6coaK70" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Software Development
### 1. Where do you get the toolchain?
#### 1.1 byteDEVKIT
* **Yocto 3.0**
MISSING Data

* **Yocto 2.7**
MISSING Data

#### 1.2 bytePANEL
* **Yocto 3.0**
_Downlad LINK_: <https://bytesatwork.ch/downloads/transfer/bytesatwork/poky-bytesatwork-glibc-x86_64-devbase-image-bytesatwork-armv7at2hf-neon-bytepanel-toolchain-3.0.1.sh>

* **Yocto 2.7**
_Downlad LINK_: <https://bytesatwork.ch/downloads/transfer/bytesatwork/poky-bytesatwork-glibc-x86_64-devbase-image-bytesatwork-armv7at2hf-neon-bytepanel-toolchain-2.7.3.sh>

### 2. Where do you get the Image for your SD-Card?

#### 2.1 byteDEVKIT
* **Yocto 3.0**
MISSING Data

* **Yocto 2.7**
MISSING Data

#### 2.2 bytePANEL
* **Yocto 3.0**
_Download LINK_: https://bytesatwork.ch/downloads/transfer/bytesatwork/devbase-image-bytesatwork-bytepanel.wic.gz

* **Yocto 2.7**
_Downlad LINK_: <https://bytesatwork.ch/downloads/transfer/bytesatwork/m2/2.7/devbase-image-bytesatwork-bytepanel-emmc-20190729194430.sdimg.gz>

### 3. How do you flash the Image?

#### 3.1 byteDEVKIT
* **Yocto 3.0**
* **Yocto 2.7**

#### 3.2 bytePANEL
* **Yocto 3.0**
* **Yocto 2.7**

### 4. How do you build an Image?
#### 4.1 byteDEVKIT
* **Yocto 2.7 & Yocto 3.0**
Use repo to download all necessary repositories:
	```
	repo init -u https://github.com/bytesatwork/bsp-platform-st.git -b warrior repo sync
	```

	If those commands are completed successfully, the following command will setup a Yocto Project environment for byteDEVKIT:
	```
	MACHINE=bytedevkit DISTRO=poky-bytesatwork EULA=1 . setup-environment build
	```

	The final command builds the development image:
	```
	bitbake devbase-image-bytesatwork
	```

	The output is found in:
	```
	tmp/deploy/images/bytedevkit
	```

#### 4.2 bytePANEL
* **Yocto 2.7 & Yocto 3.0**
_Use repo to download all necessary repositories:_
``repo init -u https://github.com/bytesatwork/bsp-platform.git -b zeus repo sync``

	_If those commands are completed successfully, the following command will setup a Yocto Project environment for bytePANEL:_
``MACHINE=bytepanel DISTRO=poky-bytesatwork EULA=1 . setup-environment build``

	_he final command builds the development image:_
``bitbake devbase-image-bytesatwork``

	_The output is found in:_
``tmp/deploy/images/bytepanel``

### 5. How do you build a toolchain?

#### 5.1 byteDEVKIT
* **Yocto 2.7**
``repo init -u https://github.com/bytesatwork/bsp-platform-st.git -b warrior repo sync``

	_If those commands are completed successfully, the following command will setup a Yocto Project environment for byteDEVKIT:_
``MACHINE=bytedevkit DISTRO=poky-bytesatwork EULA=1 . setup-environment build``

	_The final command builds an installable toolchain:_
``bitbake devbase-image-bytesatwork -c populate_sdkbytePANEL``

* **Yocto 3.0**
``repo init -u https://github.com/bytesatwork/bsp-platform.git -b zeus repo sync``

	_If those commands are completed successfully, the following command will setup a Yocto Project environment for bytePANEL:_
``MACHINE=bytepanel DISTRO=poky-bytesatwork EULA=1 . setup-environment build``

	_The final command builds an installable toolchain:_
``itbake devbase-image-bytesatwork -c populate_sdk``

### 6. How do you install the toolchain?
#### 6.1 byteENGINE AM335x
* _Download the Toolchain and install it_
`sudo ./poky-bytesatwork-glibc-x86_64-devbase-image-bytesatwork-armv7at2hf-neon-bytepanel-toolchain-3.0.1.sh`

#### 6.2 byteENGINE STM32MP1x
* _Download the Toolchain and install it_
`./poky-bytesatwork-glibc-x86_64-devbase-image-bytesatwork-cortexa7t2hf-neon-vfpv4-bytedevkit-toolchain-2.7.2.sh`

### 7. How do you use the toolchain?
#### 7.1 byteENGINE AM335x
* Source the Toolchain
`source /opt/poky-bytesatwork/3.0.1/environment-setup-armv7at2hf-neon-poky-linux-gnueabi`

* _Check if Cross-compiler is available in environment:_
`echo $CC`
`arm-poky-linux-gnueabi-gcc -march=armv7-a -mthumb -mfpu=neon -mfloat-abi=hard`
`--sysroot=/opt/poky-bytesatwork/3.0.1/sysroots/armv7at2hf-neon-poky-linux-gnueabi`

* _Crosscompile the source code, e.g. by:_
`$CC helloworld.c -o helloworld`

* _Check generated binary:_
`file helloworld`
`helloworld: ELF 32-bit LSB pie executable, ARM, EABI5 version 1`

#### 7.2 byteENGINE STM32MP1x
* _Source the installed Toolchain_
`source /opt/poky-bytesatwork/2.7.2/environment-setup-cortexa7t2hf-neon-vfpv4-poky-linux-gnueabi`

* _Check if Cross-compiler is available in environment:_
`echo $CC`
`arm-poky-linux-gnueabi-gcc -mthumb -mfpu=neon-vfpv4 -mfloat-abi=hard`
`-mcpu=cortex-a7`
`--sysroot=/opt/poky-bytesatwork/2.7.2/sysroots/cortexa7t2hf-neon-vfpv4-poky-linux-gnueabi`

* _Crosscompile the source code, e.g. by:_
`$CC helloworld.c -o helloworld`

* _Check generated binary:_
`file helloworld`
`helloworld: ELF 32-bit LSB pie executable, ARM, EABI5 version 1`

## Hardware Development

### byteENGINE AM335x

* **General Information**: The byteENGINE AM335x is a high performance industrial oriented computing module. It allows a short time-to-market, while reducing development costs and substantial design risks. The system on module (SOM) uses the Texas Instruments AM335x industrial applications processor family. The AM335x features a PowerVRTM SGX Graphics Accelerator Subsystem for 3D graphics acceleration. The Programmable Real-Time Unit and Industrial Communication Subsystem (PRU-ICSS) allows independent operation from the ARM processor. PRU-ICSS enables real-time protocols such as EtherCAT, PROFINET, EtherNet/IP, PROFIBUS, Ethernet Powerlink and Sercos.

	**The byteENGINE AM335x** is a high performance industrial oriented computing module. It allows a short time-to-market, while reducing development costs and substantial design risks.

	**The system on module (SOM)** uses the Texas Instruments AM335x industrial applications processor family. The AM335x features a PowerVRTM SGX Graphics Accelerator Subsystem for 3D graphics acceleration. The Programmable Real-Time Unit and Industrial Communication Subsystem (PRU-ICSS) allows independent operation from the ARM processor. PRU-ICSS enables real-time protocols such as EtherCAT, PROFINET, EtherNet/IP, PROFIBUS, Ethernet Powerlink and Sercos.

* **Pinout AM335x**
<https://www.bytesatwork.io/wp-content/uploads/2019/03/Datasheet_byteENGINE_AM335x-12.pdf>

### byteENGINE STM32MP1x

* **General Information**: The byteENGINE STM32MP1x is a high performance industrial oriented computing module. It allows you a short time-to-market, reducing development costs and substantial design risks.

	**The system on module (SOM)** uses the STM32MP15xxAC devices which are based on the high-performance dual-core ARM® Cortex®-A7 32-bit RISC core operating at up to 650 MHz/800 MHz. The STM32MP15xxAC devices also embed a Cortex®-M4 32-bit RISC core operating at up to 200 MHz frequency. The Cortex®-M4 core features a floating point unit (FPU) single precision which supports ARM® single-precision dataprocessing instructions and data types.

	**Furthermore, the STM32MP15xxAC** devices embed a 3D graphic processing unit (Vivante® - OpenGL® ES 2.0) running at up to 533 MHz, with performances up to 26 Mtriangle/s, 133 Mpixel/s.

* **Fact Sheet STM32MP1**
https://www.bytesatwork.io/wp-content/uploads/2019/04/Fact-Sheet-byteENGINE_STM32MP1x.pdf

+ **Pinout STM32MP1x**
https://www.bytesatwork.io/wp-content/uploads/2019/12/Datasheet_byteENGINE_STM32MP1x-6.pdf

