# 华硕灵耀2代 Hackintosh 相关文件

这是 **Asus S5300FN** 的相关文件, 这套配置我仅在 macOS Mojave 10.14.6 和 macOS Catalina 10.15.2 上测试通过, 完美度较高.

⚠️️️注意: 本项目提供的 EFI 不可用于其它机型, 直接覆盖可能会导致各种问题. 建议了解 **Clover** 、 **黑苹果驱动** 、**DSDT和SSDT** 等相关知识后再使用. 安装教程再最下面, 请阅读后再自行操作! 

## 硬件配置

|名称|型号|备注
:-:|:-:|:-:
|CPU|Intel Core i5 8265U @ 1.6GHz
|主板|X530FN_S5300FN|BIOS版本: 305
|内存|镁光 16G x 2|我自行更换的
|固态|WDC PC SN520 (512GB)
|机械|WDC WD20SPZX-22CRAT0 (2TB)
|网卡/蓝牙|BCM94350ZEN|原始网卡无解, 自行更换
|显卡|Intel UHD Graphics 620

## 正常工作的硬件

- [x] CPU睿频
- [x] 显卡硬件加速 (QE/CI)
- [x] 音频完美 (AppleALC + CodecCommander + Layout: 21)
- [x] USB3.1 & USB3.0 & USB2.0
- [x] WIFI 和 蓝牙
- [x] 电量精准显示
- [x] 触控板 (手势全部可用, 但是有问题)
- [x] 触控板禁用和启用 (prt sc键)
- [x] 睡眠和唤醒
- [x] 屏幕亮度调节
- [x] 键盘灯亮度调节 (10.15下不完美, 等驱动更新)
- [x] Fn按键正常
- [x] 定位正常
- [x] 已经仿冒自动亮度
- [x] SD卡槽

## 不正常工作的硬件

- [ ] HDMI输出 (已找到总线, 但是黑屏, 等待修复)

## 能工作的更好的硬件

* 开启HiDPI

    推荐开启HiDPI让屏幕显示效果更好. 建议的分辨率: <br/>
    
    |实际分辨率|HiDPI分辨率|说明
    :-:|:-:|:-:|
    |3840 x 2160|1920 x 1080|屏幕原始分辨率, 不能解决模糊问题
    |3200 x 1800|1600 x 900|最佳分辨率, 不花屏, 睡眠唤醒完美
    |2880 x 1620|1440 x 810|
    |2560 x 1440|1280 x 720|

    [一键开启HiDPI (xzhih)](https://github.com/xzhih/one-key-hidpi)
    <br/>
    [手动注入HiDPI (黑果小兵)](https://blog.daliansky.net/Use-HIDPI-to-solve-sleep-wake-up-black-screen,-Huaping-and-connect-the-external-monitor-the-correct-posture.html)

## 关于键盘 Fn 按键的说明

由于这个笔记本的键盘灯在 Windows 下只有一个按键调节, 所以在 macOS 下只能增加亮度, 所以我牺牲了 Fn+F6 (禁用触控板), 来实现降低键盘灯亮度. 所以 PrtSc 这个按键变成了禁用启用触控板的按键

## 安装教程 (简易版)

1. 使用 etcher 将原版的镜像写入U盘
2. 将 Clover 文件夹复制到 EFI 分区的文件夹下.
3. 安装 macOS, 直至结束
4. 重启两次后将 触控板驱动 放入 kext\Other 下, 再次重启直到触控板可用
5. 将DSDT.aml放入 ACPI\patched\ 下重启, 随后测试键盘灯, 触控板等功能

## 捐赠

您的支持就是我更新维护的动力!
<br/>
<img src="https://raw.githubusercontent.com/Jie2GG/Image/master/WeChat.png" width="260" height="350" alt="微信二维码"/>
<img src="https://raw.githubusercontent.com/Jie2GG/Image/master/AliPlay.png" width="260" height="350" alt="支付宝二维码"/>

## 更新日志

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
