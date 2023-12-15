# Laptop Acer Aspire 7 Gaming (supported: R6ZR, R05G, R4ST, R4XX)

![alt tag](/images/laptopacergamingaspire.png)

## SYSTEM

|                   |                                |
| ----------------- | ------------------------------ |
| Processor:        | AMD Ryzen 5 5500U (APU Mobile) |
| Memory:           | 8GB x 2                        |
| Graphics:         | AMD Radeon RX Vega 7 (Renoir)  |
| Wireless Network: | Intel AX210                    |
| Strorage:         | WD SN530                       |
| Audio:            | Realtek ALC255                 |
| Camera:           | HD User Facing                 |

## Setup EFI

1. Setup rEFInd  (Optional) \
   1.1. Edit the `refind.conf` configuration in `EFI/BOOT/refind.conf` according to the EFI partition on your computer \
   1.2. repace reFEInd/BOOT to EFI/BOOT \
3. If your Aspire 7 has `"R4XX"` after the codename then please add `keepsyms=1 debug=0x100 swd_panic=1` to `boot-args` to fix the bootloop issue (Required)

## Installation Instructions

1. Setup bios: Disable fast boot, disable secure boot
2. Disable kext "NootedRed.kext", after the setup process after installing MacOS and then turning it back on
3. Install HoRNDIS-9.2.pkg (used to share ethernet from android phone) (Optional)
4. Fix headphones and internal microphone error
   - https://github.com/longluuly/AppleALC
5. Fix External microphone (Headphone microphone) (Optional) \
   5.1. Add VerbStub.kext \
   5.2. Extract ComboJack-master.zip \
   5.3. Open ComboJack_Installer \
   5.4. Run `./install` in Terminal \
   5.5. After every time you plug in a headphone, a notification will appear. Please select "Headset" for the headphone microphone to work
6. Increase nvram using https://github.com/DavidS95/Smokeless_UMAF (Optional) 
7. Fix sleep:
   run `sudo pmset -a hibernatemode 0` in Terminal

## What's working:

- Wi-Fi/Bluetooth (Intel AX210)
- USB Ports, USB-C
- Keyboard
- Trackpad I2C, gestures ~~(works in polling mode~~, support full now, kext get from nootedred)
- Audio
- Headphones
- Internal Microphone: working with fork of https://github.com/qhuyduong/AppleALC, my fork fix headphones https://github.com/longluuly/AppleALC
- External Microphone (headphone micro) woking with https://github.com/hackintosh-stuff/ComboJack
- Internal graphics acceleration (vcn is currently disabled for bug fixes, kext get from nootedred)
- Control brightness, sound and touchpad via keyboard keys
- Battery Status
- Inbuilt Camera
- CPU, iGPU
- Monitor CPU, GPU temperature
- HDMI: (working, connected to iGPU not GTX1650)
- Sleep: Fixed

## What's Not Working:

- ~~GTX 1650:~~ (Not supported in MacOS)
- ~~Internal Microphone: (currently not working)~~ Fixed -> working
- ~~Fans control:~~ (currently not working)
- ~~Wake:~~ The screen cannot be turned back on if it is asleep for too long

## Unknown things:

- Headphones: ~~(I didn't test it)~~ Fixed -> working
- Sleep: ~~(same as above)~~ -> fixed

## Thanks all tester
- R4XX: Phạm Sáng Tỏ: [sangto2906](https://github.com/sangto2906)
- R05G: Phạm Khôi Nguyên

## Thanks
https://github.com/Seey6/CpuTscSync \
https://github.com/ChefKissInc/NootedRed \
https://github.com/acidanthera

## SCEENSHOTS:ß

![](images/img12.png)
![](images/img11.png)
![](images/img7.png)
