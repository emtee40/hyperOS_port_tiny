<div align="center">


# HyperOS 移植项目
### 基于 https://github.com/ljc-fight/miui_port

简体中文&nbsp;&nbsp;|&nbsp;&nbsp;[English](/README_en-US.md) 

</div>

## 简介
- HyperOS 一键自动移植打包

## 测试机型及版本

- 测试机型小米10 底包 (V14.0.4.0.TJBCNXM)
- 测试版本： 当前分支基于小米14Pro基础版和开发版，[fuxi-dev](https://github.com/toraidl/hyperos_port/tree/fuxi-dev)分支基于小米13开发版。
## 正常工作
- 人脸
- 挖孔
- 指纹  
- NFC
- 相机（mi10s 4.5版本可用，需自行下载放入device/umi/overlay/product/priv-app/MiuiCamera/MiuiCamera.apk）
- 自动亮度
- 通话息屏
- 应用双开
- 护眼模式
- 带壳截屏

## BUG

- （shennong分支）息屏解锁时，有几率出现闪屏问题，可尝试在开发者选项中开启“**停用HW叠加层**“选项
- 等你发现

## 说明
- 以上均基于底包小米10正式版(V14.0.4.0.TJBCNXM)测试
- 其他机型需要测试修改

## 如何使用
- 在WSL、ubuntu、deepin等Linux下
```shell
    sudo apt update
    sudo apt upgrade
    sudo apt install git -y
    # 克隆项目
    git clone https://github.com/toraidl/hyperos_port.git
    cd hyperos_port
    # 安装依赖
    sudo ./setup.sh
    # 开始移植
    sudo ./port.sh <底包路径> <移植包路径>
```
- 在macOS下
```shell
    # 安装brew
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

    # 克隆项目
    git clone https://github.com/toraidl/hyperos_port.git
    cd hyperos_port
    # 安装依赖
    sudo ./setup.sh
    # 开始移植
    sudo ./port.sh <底包路径> <移植包路径>
```
- 在Termux上(未测试)
```shell
    pkg update
    pkg upgrade
    pkg install git tsu -y
    # 克隆项目
    git clone https://github.com/toraidl/hyperos_port.git
    cd hyperos_port/
    # 安装依赖
    ./setup.sh
    # 进入root模式
    tsu
    ./port.sh <底包路径> <移植包路径>
```
- 上述代码中，底包路径和移植包路径可以替换为链接，例：
```shell
sudo ./port.sh https://bigota.d.miui.com/V14.0.4.0.TJBCNXM/miui_UMI_V14.0.4.0.TJBCNXM_23fc5ef4ee_13.0.zip https://bigota.d.miui.com/OS1.0.23.11.13.DEV/miui_SHENNONG_OS1.0.23.11.13.DEV_c776cc46d4_14.0.zip
```