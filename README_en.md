
[简体中文](README.md)|[English](README_en.md)

# ASUS VivoBook S5300FN Hackintosh related documents

This is **Asus S5300FN** related documents, This configuration I only in macOS 10.13 - macOS 11.4 in test pass, perfection degree high.

⚠️️️Attention: EFI provided in this project cannot be used for other laptop, Direct use can cause a variety of problems. Please understand OpenCore、macOS Kext and ACPI use of relevant knowledge. The installation tutorial is below, please read carefully befor you operate by youerself!

# Hardware

|Name|Model|Note
:-:|:-:|:-:
|CPU|Intel Core i5 8265U @ 1.6GHz
|Chipset|X530FN_S5300FN|BIOS Version: 305
|RAM|Micron 16GB x 2|Myself replace
|SSD|WDC PC SN520 (512GB)
|HDD|WDC WD20SPZX-22CRAT0 (2TB)
|WIFI|BCM94350ZEN (DW1820A)|can't use of orginal WIFI 
|GPU|Intel UHD Graphics 620
|Touchpad|ELAN1200

## Normal workings Hardware

- [x] CPU Turbo Frequency (There are some problems with frequency conversion)
- [x] GPU (QE/CI)
- [x] HDMI Output (output 4K/50Hz)
- [x] Aodio (AppleALC + Layout:21)
- [x] USB3.1 & USB3.0 & USB2.0
- [x] WIFI & Bluetooth
- [x] Battery
- [x] TouchPad
- [x] Sleep and Wake up
- [x] Screen light
- [x] Keyboard light
- [x] Fn Key Normal
- [x] Positioning Normal
- [x] Fake auto brightness
- [x] SD Card
- [x] Optimized fan strategy

## Not workings Hardware

- [ ] Fan Sensor
- [ ] Independent GPU

## About keyboard Fn Key

Due to the laptop keyboard light in Windows only one key adjust. So in macOS use Fn+F6 implementaion reduce the brightness. 

## Installation tutorial (Simple)

1. Write the dmg image on the U disk
2. Copy EFI to U disk EFI partition
3. Install macOS

## Donation

Your support is my power of maintenance
<br/>
<img src="https://raw.githubusercontent.com/Jie2GG/Image/master/WeChat.png" width="260" height="350" alt="WeChatPay QRCode"/>
<img src="https://raw.githubusercontent.com/Jie2GG/Image/master/AliPlay.png" width="260" height="350" alt="AliPay QRCode"/>
