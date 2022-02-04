
[简体中文](README.md)|[English](README_en.md)

# ASUS VivoBook S5300FN Hackintosh related documents

This is **Asus S5300FN** related documents, This configuration I only in macOS 10.13 - macOS 11.4 in test pass, perfection degree high.

⚠️️️Attention: EFI provided in this project cannot be used for other laptop, Direct use can cause a variety of problems. Please understand OpenCore、macOS Kext and ACPI use of relevant knowledge. The installation tutorial is below, please read carefully befor you operate by youerself!

## Donation

Your support is my power of maintenance
<br/>
<img src="https://raw.githubusercontent.com/Jie2GG/Image/master/WeChat.png" width="260" height="350" alt="WeChatPay QRCode"/>
<img src="https://raw.githubusercontent.com/Jie2GG/Image/master/AliPlay.png" width="260" height="350" alt="AliPay QRCode"/>

---

## Hardware

|Name|Model|Note
:-:|:-:|:-:
|CPU|Intel Core i5 8265U @ 1.6GHz
|Chipset|X530FN_S5300FN|BIOS Version: 308
|RAM|Micron 16GB x 2|Myself replace
|SSD|WDC PC SN520 (512GB)
|HDD|WDC WD20SPZX-22CRAT0 (2TB)
|WIFI|BCM94360CS2(AppleWIFI)|can't use of orginal WIFI 
|GPU|Intel UHD Graphics 620
|Touchpad|ELAN1200

---

## Normal workings Hardware

- [x] CPU Turbo Frequency
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

---

## Not workings Hardware

- [ ] Fan Sensor
- [ ] Independent GPU

---

## About keyboard Fn Key

Due to the laptop keyboard light in Windows only one key adjust. So in macOS use Fn+F6 implementaion reduce the brightness. 

---

## Disabled CFG Lock

⚠️️️Attention: 
1. This operation modifies underlying BIOS data, which may damage the BIOS. Exercise caution when performing this operation. (Please test and unlock the i7 laptop by yourself)
2. An unlocked CFG Lock may cause a CPU frequency of 0.5GHz after sleep
3. Before unlocking the BIOS, determine the **offset** of the CFG Lock in the BIOS. If you do not know the offset, see <a href='https://dortania.github.io/OpenCore-Post-Install/misc/msr-lock.html#turning-off-cfg-lock-manually'>Find the CFG Lock offset</a>
4. Follow my tutorial and use the original BIOS upgrade I provided

Modify the tutorial
1. Upgrade the BIOS to X530FS.308
2. Prepare a bootable USB drive using UEFI
3. Open the EFI partition of the USB drive, will  "ru.efi" copy to "EFI/BOOT" directory, and rename file "ru.efi" to "bootx64.efi"
4. Boot USB drive. If you succeed you will see something like this
<img src="https://raw.githubusercontent.com/Jie2GG/Hackintosh-ASUS-S5300FN/master/Images/01.jpeg">
5. Press "Enter" key
6. Press "Alt" + "=". If you succeed you will see something like this
<img src="https://raw.githubusercontent.com/Jie2GG/Hackintosh-ASUS-S5300FN/master/Images/02.jpeg">
7. Using the arrow keys, look for the "Setup" item (normally you'll get two Setup items), find the item with the most data, and press "Enter" to go to the variable editing screen. If you succeed you will see something like this
<img src="https://raw.githubusercontent.com/Jie2GG/Hackintosh-ASUS-S5300FN/master/Images/03.jpeg">
8. Use the arrow keys to locate (006F, 00), where the value should be 01
9. Press "Enter", change the value to 00, and press "Enter" when you are done
10. Press "Ctrl" + "W" to save the changes
11. Press the "Alt" + "Q" key combination to exit the tool and then shut down the computer (not restart it)

---

## Installation tutorial (Simple)

1. Write the dmg image on the U disk
2. Copy EFI to U disk EFI partition
3. Install macOS
