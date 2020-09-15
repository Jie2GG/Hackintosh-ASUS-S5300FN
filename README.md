
[简体中文](README.md)|[English](README_en.md)

# 华硕灵耀2代 Hackintosh 相关文件

这是 **Asus S5300FN** 的相关文件, 这套配置支持 macOS 10.13 - macOS 11.0 上测试通过, 完美度较高.

⚠️️️注意: 本项目提供的 EFI 不可用于其它机型, 直接覆盖可能会导致各种问题. 建议了解 **OpenCore** 、 **黑苹果驱动** 、**DSDT和SSDT** 等相关知识后再使用. 安装教程在下面, 请仔细阅读后再自行操作! 

## 硬件配置

|名称|型号|备注
:-:|:-:|:-:
|CPU|Intel Core i5 8265U @ 1.6GHz
|主板|X530FN_S5300FN|BIOS版本: 305
|内存|镁光 16G x 2|我自行更换的
|固态|WDC PC SN520 (512GB)
|机械|WDC WD20SPZX-22CRAT0 (2TB)
|网卡|BCM94350ZEN (DW1820A)|原始网卡无解, 自行更换
|显卡|Intel UHD Graphics 620|
|触控板|ELAN1200|

## 正常工作的硬件

- [x] CPU睿频
- [x] 显卡硬件加速 (QE/CI)
- [x] HDMI输出 (macOS 11.0 下无法输出 4K/50Hz)
- [x] 音频完美 (AppleALC + Layout: 21)
- [x] HDMI音频输出
- [x] USB3.1 & USB3.0 & USB2.0
- [x] WIFI 和 蓝牙
- [x] 电量精准显示
- [x] 触控板
- [x] 触控板禁用和启用 (Prtsc 键)
- [x] 睡眠和唤醒
- [x] 屏幕亮度调节
- [x] 键盘灯亮度调节
- [x] Fn按键正常
- [x] 定位正常
- [x] 已经仿冒自动亮度
- [x] SD卡槽
- [x] 风扇传感器

## 关于键盘 Fn 按键的说明

由于这个笔记本的键盘灯在 Windows 下只有一个按键调节, 所以在 macOS 下只能增加亮度, 所以我牺牲了 Fn+F6 (禁用触控板), 来实现降低键盘灯亮度. 所以 PrtSc 这个按键变成了禁用启用触控板的按键

## 关于 macOS 11.0 的问题

由于驱动暂未完全支持 macOS 11.0, 所以 HDMI 接口在接入 4K 屏幕时, 无法使用 4K/50Hz 的分辨率.

## 安装教程 (简易版)

1. 使用 etcher 将原版的镜像写入U盘
2. 将 OpenCore 复制到 EFI 文件夹下
3. 安装 macOS, 直至结束

## 捐赠

您的支持就是我更新维护的动力!
<br/>
<img src="https://raw.githubusercontent.com/Jie2GG/Image/master/WeChat.png" width="260" height="350" alt="微信二维码"/>
<img src="https://raw.githubusercontent.com/Jie2GG/Image/master/AliPlay.png" width="260" height="350" alt="支付宝二维码"/>
