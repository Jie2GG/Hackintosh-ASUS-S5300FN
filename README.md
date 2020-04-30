# 华硕灵耀2代 Hackintosh 相关文件

这是 **Asus S5300FN** 的相关文件, 这套配置我仅在 macOS Mojave 10.14.6 和 macOS Catalina 10.15.4 上测试通过, 完美度较高.

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
- [x] HDMI输出
- [x] 音频完美 (AppleALC + Layout: 21)
- [x] HDMI音频输出
- [x] USB3.1 & USB3.0 & USB2.0
- [x] WIFI 和 蓝牙
- [x] 电量精准显示
- [x] 触控板
- [x] 触控板禁用和启用 (prt sc键)
- [x] 睡眠和唤醒
- [x] 屏幕亮度调节
- [x] 键盘灯亮度调节 (10.14下和白果一样, 10.15下不完美)
- [x] Fn按键正常
- [x] 定位正常
- [x] 已经仿冒自动亮度
- [x] SD卡槽

## 关于键盘 Fn 按键的说明

由于这个笔记本的键盘灯在 Windows 下只有一个按键调节, 所以在 macOS 下只能增加亮度, 所以我牺牲了 Fn+F6 (禁用触控板), 来实现降低键盘灯亮度. 所以 PrtSc 这个按键变成了禁用启用触控板的按键

## 安装教程 (简易版)

1. 使用 etcher 将原版的镜像写入U盘
2. 将 OpenCore 复制到 EFI 文件夹下
3. 安装 macOS, 直至结束

## 捐赠

您的支持就是我更新维护的动力!
<br/>
<img src="https://raw.githubusercontent.com/Jie2GG/Image/master/WeChat.png" width="260" height="350" alt="微信二维码"/>
<img src="https://raw.githubusercontent.com/Jie2GG/Image/master/AliPlay.png" width="260" height="350" alt="支付宝二维码"/>

## 更新日志
* V1.4.0

    * 新增 图形GUI, 开机时可以使用图形界面切换磁盘
    * 新增 开机 Duang 音效
    * 优化 核心显卡的 FrameBuffer, 现在支持输出 4K/50Hz 的分辨率 (HDMI 1.4)
    * 更新 VoodooI2C 驱动到 2.4.2 版本, 完美解决触控板问题
    * 更新 OpenCore 版本到 0.5.7 正式版
    * 更新 OpenCore 配置工具与当前 EFI 版本对应
    * 移除 Clover 相关的 EFI

* V1.3.1

    * 修正 HDMI 输出接口, 同时支持热拔插和音频输出 (OpenCore)

* V1.3.0

    * 升级 OpenCore 0.5.6
    * 新增 屏蔽独显补丁, 对独显断电处理. 提升续航
    * 新增 NVMeFix 驱动, 优化 NVMe 耗电
    * 删除 SSDT-EC.aml, 启用机器原有的 EC0

* V1.2.1

    * 新增 USBPower.kext 增加 USB 电源的白果功能
    * 修复 OpenCore 引导无法引导 Windows
    * 更新 Clover 引导同步 OpenCore 的热补丁和驱动列表

* V1.2.0

    * 新增 OpenCore 引导程序

* V1.1.4

    * 为 DSDT 所有更改都替换为热补丁
    * 更换机型为 MBP15,4

* V1.1.3
    
    * 驱动 NVRAM, 并删除模拟 NVRAM 的驱动

* V1.1.2

    * 添加 HiDPI 描述文件

* V1.1.1

    * 优化 FrameBuffer, 现在支持比 1440 x 810 更高的 HiDPI 分辨率 (推荐 1600 x 900)

* V1.1.0

    * 修改 USB仿冒补丁, 驱动 SD卡槽
    * 更新 核显驱动, 支持 HEVC硬解码
    * 更新 核心显卡仿冒 655 核显
    * 更新 触控板驱动
    * 更新 网卡驱动
    * 更新 蓝牙驱动 (支持 10.15 冷启动)
    * 增加 PCI设备的内建
    * 增加 SMBIOS信息, 但是删除三码. 需要苹果应用则自行解决三码问题

* V1.0.0
    
    * 上传 Clover 包
