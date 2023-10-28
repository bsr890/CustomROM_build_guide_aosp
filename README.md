# Custom Rom Build #
This is the Custom Rom build guide for Redmi Note 11 (spes/spesn)

```bash

#Requirements
1. A cloud server
2. Minimum 8-core & 16 GB RAM
3. 500 GB+ storage
4. Device: Redmi Note 11
5. Codename: spes/spesn
6. Stable internet connection
7. OS Ubuntu 20.4 LTS or latest

```

## Build Environment ##

Installing required packages

OS: Ubuntu 18.04 and higher

Version: 64-bit

```bash

sudo apt-get install git-core gnupg flex bison build-essential zip curl zlib1g-dev libc6-dev-i386 libncurses5 x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig

```
<br>

Setting Up Build Environment

```bash

sudo su

```


```bash

add-apt-repository ppa:openjdk-r/ppa && apt-get update && sudo apt-get install git-core gnupg flex bison build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 libncurses5 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig && exit

```
<br>

Cloning Akhil Narang Scripts

```bash

mkdir ~/bin && PATH=~/bin:$PATH && cd ~/bin && curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo && chmod a+x ~/bin/repo && git clone https://github.com/akhilnarang/scripts.git scripts && cd scripts && bash setup/android_build_env.sh && cd

```
Directly Copy Paste these commands


## Device Tree ##

```bash
#Device tree contains

1. device_xiaomi_spes
2. kernel_xiaomi_spes
2. vendor_xiaomi_spes

spes is my device codename
It varies phone to phone

```

Cloning Pre merged Device Tree

```bash
mkdir rom_name
```

```bash
cd rom_name
```
<br>
Here,


-b stands for branch

13 stands for branch name and

device/xiaomi/spes for targeted path

```bash

git clone https://github.com/ProjectBlaze-Devices/device_xiaomi_spes.git -b 13 device/xiaomi/spes

```

```bash

git clone https://github.com/LineageOS/android_hardware_xiaomi.git -b lineage-20 hardware/xiaomi

```


Now navigate to this path 👇

```bash

cd device/xiaomi/spes

```

```bash

ls

```

<br>


## Bring Up ##

Now, you must have to modify these 2 files on device tree named

1. AndroidProducts.mk
2. blaze_spes.mk

Different rom use different code names likes

Pixel Experience use: aosp

LMODroid use: lmodroid

PixelOS use: aosp

Project Elixir use: aosp

it's available either on their GitHub manifest pages or in Telegram group

Suppose, i am building LMODroid rn

So, my code name is lmodroid

now, open AndroidProducts.mk using nano command

```bash

nano AndroidProducts.mk

```

Where you can see blaze, change it to lmodroid


Now, to save the AndroidProducts.mk press

"ctrl+o"

"enter"

"ctrl+x"

After pressing ctrl+x it will revert back to your current path.

