
[简体中文](README.md)|[English](README_en.md)

# 华硕灵耀2代 Hackintosh 相关文件

这是 **Asus S5300FN** 的相关文件, 这套配置支持 macOS 10.13 - macOS 12.2 上测试通过, 完美度非常高.

⚠️️️注意: 本项目提供的 EFI 不可用于其它机型, 直接覆盖可能会导致各种问题. 建议了解 **OpenCore** 、 **黑苹果驱动** 、**DSDT和SSDT** 等相关知识后再使用. 安装教程在下面, 请仔细阅读后再自行操作! 

## 捐赠

您的支持就是我更新维护的动力!
<br/>
<img src="https://raw.githubusercontent.com/Jie2GG/Image/master/WeChat.png" width="260" height="350" alt="微信二维码"/>
<img src="https://raw.githubusercontent.com/Jie2GG/Image/master/AliPlay.png" width="260" height="350" alt="支付宝二维码"/>

---

## 硬件配置

|名称|型号|备注
:-:|:-:|:-:
|CPU|Intel Core i5 8265U @ 1.6GHz
|主板|X530FN_S5300FN|BIOS版本: 308
|内存|镁光 16G x 2|我自行更换的
|固态|WDC PC SN520 (512GB)
|机械|WDC WD20SPZX-22CRAT0 (2TB)
|网卡|BCM94350ZEN (DW1820A)|原始网卡无解, 自行更换
|显卡|Intel UHD Graphics 620|
|触控板|ELAN1200|

---

## 正常工作的硬件

- [x] CPU睿频
- [x] 显卡硬件加速 (QE/CI)
- [x] HDMI输出 (可输出 4K/50Hz)
- [x] 音频完美 (AppleALC + Layout: 21)
- [x] HDMI音频输出
- [x] USB3.1 & USB3.0 & USB2.0
- [x] WIFI 和 蓝牙
- [x] 电量精准显示
- [x] 触控板
- [x] 睡眠和唤醒
- [x] 屏幕亮度调节
- [x] 键盘灯亮度调节
- [x] Fn按键正常
- [x] 定位正常
- [x] 已经仿冒自动亮度
- [x] SD卡槽

---

## 不正常工作的硬件

- [ ] 风扇传感器 
- [ ] 独立显卡

---

## 关于键盘 Fn 按键的说明

由于这个笔记本的键盘灯在 Windows 下只有一个按键调节, 所以在 macOS 下只能增加亮度, 所以我牺牲了 Fn+F6 (禁用触控板), 来实现降低键盘灯亮度.

---

## 解锁 CFG Lock

⚠️️️注意: 
1. 本操作要修改 BIOS 底层的数据，会有损坏 BIOS 的风险，请谨慎操作。(i7机型的笔记本请自行测试并解锁)
2. 未解锁 CFG Lock 可能引起睡眠唤醒后 CPU 频率只有 0.5GHz 的问题
3. 解锁之前需明确自己机器 BIOS 的 CFG Lock 的**偏移量**，若不清楚请参考<a href='https://dortania.github.io/OpenCore-Post-Install/misc/msr-lock.html#turning-off-cfg-lock-manually'>寻找 CFG Lock 偏移量</a>
4. 按照我的教程修改，需要使用我提供的原版 BIOS 升级

二、修改教程
1. 将 BIOS 升级到 X530FNS.308 版本
2. 准备一个可引导的 USB 驱动器，引导方式: UEFI
3. 打开 USB 驱动器的 EFI 分区，将 RU.efi 放入 EFI/BOOT，并将 RU.efi 改为 BOOTx64.efi
4. 引导 USB 驱动器启动。如果成功你将看到这个画面
<img src="https://raw.githubusercontent.com/Jie2GG/Hackintosh-ASUS-S5300FN/master/Images/01.jpeg">
5. 按下 "Enter" 键
6. 按下 "Alt" + "=" 组合键。如果成功你将看到这个画面
<img src="https://raw.githubusercontent.com/Jie2GG/Hackintosh-ASUS-S5300FN/master/Images/02.jpeg">
---

## 安装教程 (简易版)

1. 解锁 CFG Lock
2. 使用 etcher 将原版的镜像写入U盘
3. 复制 EFI 到镜像 U盘的 EFI 分区
4. 安装 macOS, 直至结束
5. 复制 EFI 到硬盘 EFI 分区
