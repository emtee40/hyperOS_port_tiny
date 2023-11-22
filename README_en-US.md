<div align="center">


# HyperOS Porting Project
### Based on https://github.com/ljc-fight/miui_port

[简体中文](/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;English

</div>

## Intro
- HyperOS Porting Project for Android 13 devices "Onekey" script

## Tested devices and portroms
- Xiaomi 10 (V14.0.4.0.TJBCNXM)
- Port from Xiaomi Mi 14 Pro Android 14 Stable and Dev CN rom, [fuxi-dev](https://github.com/toraidl/hyperos_port/tree/fuxi-dev) branch is based on Xiaomi mi13 dev 

## Working
- Face unlock
- Fringerprint
- Camera(from leaked mi10s A13 based hyperos)
- Automatic Brightness
- nfc
- etc


## BUG

- (shennong branch) When unlocking device, the screen may flicker , Enabling "Disable HW overlays" in Developer options may help.

## Description
- All the above testing is based on Xiaomi 10 official CN ROM version (V14.0.4.0.TJBCNXM). for V-AB devices, tester needed. 

## How to use
- On WSL、ubuntu、deepin and other Linux
```shell
    sudo apt update
    sudo apt upgrade
    sudo apt install git -y
    # Clone project
    git clone https://github.com/toraidl/hyperos_port.git
    cd hyperos_port
    # Install dependencies
    sudo ./setup.sh
    # Start porting
    sudo ./port.sh <baserom> <portrom>
```
- on macOS (AMD64)
```shell
    # Install brew
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

    # Clone project
    git clone https://github.com/toraidl/hyperos_port.git
    cd hyperos_port
    # Install dependencies
    sudo ./setup.sh
     # Start porting
    sudo ./port.sh <baserom> <portrom>
```
- On Termux Android (not tested)
```shell
    pkg update
    pkg upgrade
    pkg install git tsu -y
    # Clone project
    git clone https://github.com/toraidl/hyperos_port.git
    cd hyperos_port/
    # Install depenencies
    ./setup.sh
    # Enter root mode 
    tsu
    ./port.sh <baserom> <portrom>
```
- baserom and portrom can be a direct download link. you can get the ota download link  from third-party websites. eg:
```shell
    sudo ./port.sh https://bigota.d.miui.com/V14.0.4.0.TJBCNXM/miui_UMI_V14.0.4.0.TJBCNXM_23fc5ef4ee_13.0.zip https://bigota.d.miui.com/OS1.0.23.11.13.DEV/miui_SHENNONG_OS1.0.23.11.13.DEV_c776cc46d4_14.0.zip
```
## Camera
- You need to download camera apk from [here](https://drive.google.com/file/d/1igjsEVG7ermqfDObSn3qXDe-QqyPVd61/view?usp=sharing) ,and place it to devices/device_code/overlay/product/priv-app/MiuiCamera/MiuiCamera.apk. 