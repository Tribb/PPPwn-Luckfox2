# PPPwn-Luckfox

An alternative low-cost Linux board for exploits PS4 on V11.00 or below.<br>
Original work by theflow <a href=https://github.com/TheOfficialFloW/PPPwn>PPPwn</a> 
and thanks to xfangfang <a href=https://github.com/xfangfang/PPPwn_cpp>PPPwn-CPP</a> for an executable re-write of PPPwn in C++ for Cortex-A7 which is compatible with RV1103/RV1106 rockchip
on the luckfox pico series and SiSTRo for his <a href=https://github.com/GoldHEN/GoldHEN>GoldHen</a>, and lastly <a href=https://github.com/stooged/PI-Pwn>Stooged</a> for his inspiration. <br>

![](https://github.com/0x1iii1ii/PPPwn-Luckfox/blob/main/images/image1.jpg)

## Note

- I made some changes to the installation, if you follow the tutorial from YouTube, you can find the old files <a href=https://drive.google.com/file/d/1wF3EvgBBeNKX5c05TMBPtBvTrYc4oFWb/view>here</a> (only support v11.00)
and manually copy it to `home/root/` folder of your luckfox using <a href=https://sourceforge.net/projects/winscp/ >WinSCP</a> and run cmd in `old cmd.txt` file
- Currently only support PS4 `9.00, 10.00, 10.01, 11.00`
- The average PPPwned time is around `1min - 2min` sometimes it load under `1 minute`
- Using `pppwn` nightly build from xfangfang PPPwn_cpp <be>

## Tested Version
I only have PS4 v11.00 if you have other versions in the list below please test it and let me know thank you!

- [ ] 9.00
- [ ] 10.00
- [ ] 10.01
- [x] 11.00 by @0x1iii1ii
      
## What it does

The goal here is to setup the Luckfox pico to automatically try and PPPwn the console without any input from you, just wait on the home screen until the process completes.<br>
Once it PPPwned the process will stop. <br>

## Requirements

- An SD Card 8GB or above
- Luckfox Pico/Pro/Max/Plus/Mini
- Ethernet Cable
- USB Type-C for power to the board
- A USB drive with exFAT32 formatted (only use for the first time to load GoldHEN)

## Support Boards

- <b>Luckfox Pico Pro</b><br>
- <b>Luckfox Pico Max</b><br>
- <b>Luckfox Pico Plus</b><br>
- <b>Luckfox Pico Mini</b><br>
- <b>Luckfox Pico </b><br>

You can get one from the official site <a href=https://www.luckfox.com>Luckfox</a>  or from <a href=https://www.aliexpress.com/item/1005006083739388.html>Aliexpress</a> at around from 7$ to 15$.

# Special Note for Luckfox Pico/Mini
For these 2 boards, there's no Ethernet port, to make it work you need to solder the LAN Port (RJ45) cable to it, either female or male is fine, and burn the Ubuntu image with pico plus image and follow the same step as other boards.

<br>

<img src="https://github.com/0x1iii1ii/PPPwn-Luckfox/blob/main/images/image.jpg" alt="Luckfox Pico Mini" width="300">

## Installation Software

1. Download <a href=https://drive.google.com/drive/folders/1sFUWjYpDDisf92q9EwP1Ia7lHgp9PaFS>Ubuntu OS </a> After you download, extract one of the zip files according to your Luckfox Pico models. <br>
2. Burn the image onto an SD Card. Download <a href=https://drive.google.com/file/d/1ALo4G7rEaF1GNhUHINoYHT_RGWGddzYw>SocToolKit</a> and unzip the burning tool.
3. Open the software and select your chip type

Luckfox Models  | Chip Type
------------- | -------------
Luckfox Pico Pro/Max  | RV1106
Luckfox Pico/Plus/Mini  | RV1103 

4. Steps to download firmware for Luckfox Pico on Windows: <br>
  a. Choose the SD card tool.<br>
  b. The SD card size will be displayed under USB Disk. If not displayed, reinsert the card reader.<br>
  c. Select SD card booting.<br>
  d. Import the boot file.（Note: The startup files do not include update.img）<br>
  e. Click "Create SD Card".<br>

<img src="https://github.com/0x1iii1ii/PPPwn-Luckfox/blob/main/images/image2.jpg" alt="Luckfox Pico Mini" width="600">

5. After done, eject and place the SD card into the Luckfox, power it using USB Type-C, and connect it to the internet by plugging the LAN cable into the router<br>
6. Loggin to ubuntu:

`Login: pico` <br>
`Password: luckfox` <be>

log in using SSH: connect Luckfox to the internet via LAN cable, using `luckfox.lan` as host name to log in via SSH on <a href=https://putty.org>PuTTY</a>, if it does not work find its IP on your router and try again.

7. After you log in, run the following commands

<br>

```sh
git clone https://github.com/0x1iii1ii/PPPwn-Luckfox.git
cd PPPwn-Luckfox
chmod +x install.sh
sudo ./install.sh
```

<br>

Once the Luckfox reboots pppwn will run automatically.<br>

## Installation Hardware

1. You simply need to connect the LAN cable from Luckfox Pico to the PS4 and power the Luckfox from the PS4 via a USB Type-C cable or other sources.

## On your PS4:<br>

- Go to `Settings` and then `Network`<br>
- Select `Set Up Internet connection` and choose `Use a LAN Cable`<br>
- Choose `Custom` setup and choose `PPPoE` for `IP Address Settings`<br>
- Enter `ppp` for `PPPoE User ID` and `PPPoE Password`<br>
- Choose `Automatic` for `DNS Settings` and `MTU Settings`<br>
- Choose `Do Not Use` for `Proxy Server`<br>

For GoldHen you need to place the goldhen.bin file onto the root of a usb drive and plug it into the console.<br>
Once goldhen has been loaded for the first time it will be copied to the consoles internal hdd and the usb is no longer required.<br>
To update goldhen just repeat the above process and the new version will be copied to the internal hdd<br>

