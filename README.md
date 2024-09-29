# WaveShare Gameboy HAT Project x Raspberry Pi 🎮 

<p align="center">
<img src="https://user-images.githubusercontent.com/74038190/212751381-b0b2320e-6ef6-4041-a77a-de279fe5d3ae.gif" width="500">
<br><br>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/build-passing-brightgreen" alt="Build Status"/>
  <img src="https://img.shields.io/badge/Raspberry%20Pi-B%2B%20%7C%202B%20%7C%203B%20%7C%204B-lightgrey" alt="Raspberry Pi"/>
  <img src="https://img.shields.io/badge/Made%20with-Love-red.svg" alt="Made with Love"/>
  <img src="https://img.shields.io/badge/Fun%20Factor-Over%209000!-red" alt="Fun Factor"/>
</p>

<p align="center">
  
</p>
<div align="center">
  <a href="https://github.com/ailynux/WaveShare-Gameboy-HAT-Project">
    <img src="https://img.shields.io/badge/Made%20with-Recalbox-brightgreen?style=for-the-badge&logo=recalbox" alt="Made with Recalbox"/>
  </a>
  <a href="https://github.com/ailynux/WaveShare-Gameboy-HAT-Project">
    <img src="https://img.shields.io/badge/Made%20with-Raspberry%20Pi-A22846?style=for-the-badge&logo=raspberry-pi" alt="Made with Raspberry Pi"/>
  </a>
</div>

## About This Project    <img src="https://github.com/Anmol-Baranwal/Cool-GIFs-For-GitHub/assets/74038190/a2605358-6b87-44ab-87fb-20dcdc5f9ef2" width="55">&nbsp;
Hey everyone! Welcome to a guide on turning a Raspberry Pi into a super cool retro gaming console using the WaveShare Gameboy HAT. I had a blast making this, and it was so easy that I ended up helping three of my friends make their own too!    <img src="https://cultofthepartyparrot.com/parrots/hd/60fpsparrot.gif" width="25" height="25"/>

So, this whole thing started as a fun experiment with Raspberry Pi's, and it turned out to be a total win. I figured out a bunch of neat tricks along the way and I’ve put them all in this guide. If you’re looking to have some fun and get into gaming with the Pi, you’re in the right place.

<p align="center">


</p>

### Assembly Process <img src="https://user-images.githubusercontent.com/74038190/226127927-3feb953e-cc01-482e-b732-311b2907991f.gif" width="100">

Here’s what it looked like when I was putting it together:

![work in progress](https://github.com/user-attachments/assets/707e92cb-ee9c-4bd1-9a18-bd8776cc526a)

*Putting it all together was a breeze and a lot of fun!*

And here’s the finished setup, ready for some serious gaming!

![full assembled](https://github.com/user-attachments/assets/787a10fa-42c8-4c94-8eea-6ef5cbb896da)

*Ready to play and enjoy!*

The best part? It was super straightforward. I’ll walk you through what I did, step by step, from snapping the parts together to firing it up with Recalbox. It’s really that easy, and trust me, it’s a lot of fun.

### What’s Cool About This Guide?

- **Keep It Simple**: I’ve made the instructions clear and easy to follow. You’ll be up and running in no time.
- **Extra Tips**: I’ll share some custom tweaks that can help you get more out of your console.

<p align="center">
  <img src="https://user-images.githubusercontent.com/74038190/212257468-1e9a91f1-b626-4baa-b15d-5c385dfa7ed2.gif" width="200"/>
</p>

### Connect with Me

<p align="center">
  <a href="https://www.linkedin.com/in/ailyn-diaz-802943225?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app" alt="LinkedIn">
    <img src="https://img.shields.io/badge/-LinkedIn-0e76a8?style=flat-square&logo=LinkedIn&logoColor=white"/>
  </a>
</p>

## Parts needed
1. Game HAT for Raspberry Pi - https://www.waveshare.com/game-hat.htm
2. 2nd Computer to program the Pi's OS beforehand 
3. 18650 lithium battery
4. SD Card for Raspi (minimum 64gb so you aren't limited on ROM storage!)
5. Raspberry pi - Model's allowed A+/B+/2B/3B/3B+/4B
   - Optional
     * STL printed case
       
# Assembling the WaveShare Game HAT and Raspberry Pi

## Overview
This is a quick guide to assembling the WaveShare Game HAT with your Raspberry Pi.

**Snap the Game HAT onto the Raspberry Pi**:
   - Gently press the Game HAT down so that the GPIO pins slide into the Game HAT's connector.
   

## Features as included on the Waveshare Wiki

- **3.5inch IPS Screen**: 480 × 320 resolution ensures clear and vibrant visuals.
- **60 FPS Gameplay**: Experience smooth and responsive gameplay with no frame loss.
- **Compatibility**: Supports Raspberry Pi A+/B+/2B/3B/3B+/4B models. Raspberry Pi Zero variants require an additional HDMI cable.
- **Portable Gaming**: Powered by an 18650 lithium battery (not included), allowing for gaming anywhere, anytime.
- **Built-in Audio**: Includes onboard speaker and earphone jack.

## Installation Guide For RecalBox OS

### Setting Up Recalbox:

1. **Download the Recalbox Image**:
   - Obtain the latest Recalbox image for your Raspberry Pi model from [Recalbox Official Download](https://download.recalbox.com/en/#step3allimages).

2. **Write the Image to an SD Card**:
   - Use Balena Etcher or the Raspberry Pi imaging app or a similar tool to write the Recalbox image to your SD card.

3. **Modify the `config.txt` File**:
   - Add the following configurations to enhance compatibility with the Game HAT:
     ```
     hdmi_force_hotplug=1
     hdmi_group=2
     hdmi_mode=4
     hdmi_drive=2
     display_rotate=0
     avoid_warnings=1
     ```

4. **Install the SD Card and Start Your Raspberry Pi**:
   - Insert the SD card into your Raspberry Pi.
   - Connect the Raspberry Pi to the Game HAT and then connect the HDMI adapter.
   - Power on the device using the switch on the Game HAT.

### Configuring GPIO Pins and Recalbox:

1. **Access the System via SSH**:
   - Ensure your Raspberry Pi is connected to the Internet.
   - Use SSH to log into your system with the default credentials:
     - **Username**: root
     - **Password**: recalboxroot
   - Retrieve your IP address using `ifconfig`.

2. **Modify the Recalbox Configuration**:
   - Execute the following commands to enable write access:
     ```
     mount -o remount,rw /
     mount -o remount,rw /boot
     ```
   - Edit the `recalbox.conf` file using nano:
     ```
     nano /recalbox/share/system/recalbox.conf
     ```
   - Update the GPIO controller settings:
     ```
     controllers.gpio.enabled=1
     controllers.gpio.args=map=5 gpio=5,6,13,19,21,4,26,12,23,20,16,18,-1
     ```

3. **Save and Reboot**:
   - Save your changes in nano and reboot your Raspberry Pi to apply the new settings.
     
4. **How to add ROMS using SSH**:
   - SSH Setup on Windows and Mac
   - Accessing your Raspberry Pi via SSH allows you to control and configure your system remotely. Here's how to set it up on both Windows and macOS.
   - Windows SSH Setup
     
## Windows SSH Setup

1. **Install PuTTY**:
   - Download and install [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html).

2. **Obtain Raspberry Pi IP Address**:
   - Connect your Raspberry Pi to a monitor and keyboard, then use `ifconfig` to find the IP.

3. **Connect Using PuTTY**:
   - Open PuTTY, enter your Raspberry Pi's IP address, and select "SSH" as the connection type.
   - Default username: `root`, password: `recalboxroot`.

4. **Access the Recalbox Configuration**:
   - Run the following commands to enable write access and edit the configuration:
```bash
mount -o remount,rw /
nano /recalbox/share/system/recalbox.conf
```
5. **Tip**:
   - If you go to the file explorer and click in the serach you can //192.168.100 (example) and it will take you directly to the RecalBox config files and you can easily access the ROMS folder there.
   - Drag and drop your ROMS and you should be set!
     
## macOS SSH Setup

1. **Use Terminal**:

   Open Terminal and connect to your Raspberry Pi using the following command:

```bash
ssh root@<Your_Raspberry_Pi_IP>
Example:
```

```bash
ssh root@192.168.1.100
Default password: recalboxroot.
```


```bash
reboot
```

## Support and Contact
- **Username**: [@ailynux](https://github.com/ailynux)
- **Project Link**: [GitHub - GameHat](https://github.com/ailynux/GameHat-Waveshare)

## Acknowledgements  <img src="https://github.com/Anmol-Baranwal/Cool-GIFs-For-GitHub/assets/74038190/7cc5988c-f607-4d4f-ab01-360a4f9321eb" width="75">&nbsp;    
- Raspberry Pi Foundation
- All contributors to the Recalbox community
- https://www.waveshare.com/wiki/Game_HAT
  

### Connect with Me <img src="https://github.com/Anmol-Baranwal/Cool-GIFs-For-GitHub/assets/74038190/2c0eef4b-7b75-42bd-9722-4bea97a2d532" width="75">&nbsp;

<a href="https://www.linkedin.com/in/ailyn-diaz-802943225?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app" alt="LinkedIn">
  <img src="https://img.shields.io/badge/-LinkedIn-0e76a8?style=flat-square&logo=LinkedIn&logoColor=white"/></a>
