//Privacy Ghost//2300Z MARCH 11, 2025//  
//Raspberry Pi-hole//  
//**BLUF**: This walkthrough will cover the required hardware, software, and configuration for installing a Pi-hole on a local network.//


# //OVERVIEW//

## What is a Pi-hole?

Pi-hole is a **free, open-source, and privacy respecting software**.

*"The Pi-hole® is a [DNS sinkhole](https://en.wikipedia.org/wiki/DNS_Sinkhole)⁸ that protects your devices from unwanted content, without installing any client-side software."*

By using a Pi-hole on your network, you can block ads over IPV4 and IPV6. Ad traffic that is picked up by the Pi-hole is sent to a DNS sinkhole, meaning the ad traffic never hits your network! This speeds up the feel of everyday browsing by caching those DNS queries.
# //START WALKTHROUGH//

---
## Pre-requisites

---
### Required Hardware:

- [Raspberry Pi Zero 2w](https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/)  ¹* 
- USB-C cable 
- [MicroSD card](https://www.amazon.com/SanDisk-Endurance-microSDXC-Adapter-Monitoring/dp/B07NY23WBG/ref=sr_1_1?crid=5P9J3H3O4WNP&sprefix=Sanddisk+high+enduran%2Caps%2C195&sr=8-1)⁷

### Required Software:

- [Raspberry Pi Imaging software](https://www.raspberrypi.com/software/) ²

---

🎉 **Congrats!** You are all done with the pre-requisites! 🎉 Up next will be getting your MicroSD card imaged with the Raspberry Pi OS Lite(x64)! You can close this section.

---


## Getting Started

---

**Step 1:** Connect your MicroSD to your device and open the Raspberry Pi(RPi) Imager.

**Step 2:** Install Raspberry Pi OS Lite (64-bit) onto your MicroSD. Click **NEXT**.

**Step 3:** When prompted with the window *”Would you like to apply OS customization settings?* Click **EDIT SETTINGS**.

**Step 4:** Under the **General** tab, Set your host name to **Pi-hole**

**Step 5:** Set your username and password

**Step 6:** Configure the Wireless LAN settings. Input your SSID and password for your Wi-Fi network.

- *Your SSID is the name of your network, for example: “JohnDoeWifi”*

**Step 7:** Set your settings for your locale.

**Step 8:** Under the **Services** tab, enable the check box for **SSH**. 

**Step 9:** Click **SAVE**, 2X click **YES**, wait until the software is done imaging the MicroSD card, click **CONTINUE**.

---

🎉 **Congrats!** You successfully reimaged your MicroSD card to run RPi OS Lite (x64)! 🎉 Up next will be getting your RPi up and running! You can close this section.

---


## Configuring the RPi

---

**Step 1:** Take your newly imaged MicroSD card and insert it into your RPi.

**Step 2:** Plug in your MicroUSB to the **LEFT** socket. This socket is the one that provides power to the device. 

- *A green light will begin to flash, this signals that your device is successfully going into the boot sequence. After a few minutes it should be ready to connect to.*

**Step 3:** Return to your main device and open up a an instance of the terminal. We now want to connect to your RPi. In the terminal type the following command:

`ssh username@Pi-Hole.local`

- *Use the username you entered while imaging your MicroSD!*

**Step 4:** When prompted with *”Are you sure you want to continue connecting (Yes/No)?”* Type **Yes**

**Step 5:** Enter the password you set previously.

- *Your terminal should now show you connected to your RPi, it would look something like this:  JohnDoe@Pi-hole: *

**Step 6:** Enter this command block to your terminal:

`curl -sSL https://install.pi-hole.net | bash`

The Pi-hole software will now run and add the necessary packages.

**Step 7:** Once completed you’ll be greeted to a blue window. This is the **Pi-hole Automated Installer**. 

**Step 8:** Follow the on screen prompts until you get to the section on setting a **Static IP** address. 
- *This can be done just in your network settings on your device.*

**Step 9:** Once you have set the Static IP you can continue with the installer. For your upstream DNS provider, use the **Cloudflare** option.

**Step 10:** Click **YES** and include the StevenBlacks blocklist.

**Step 11:** If you want to have logging enabled click **YES**. Then **Hide Domains and Clients**. If you do not wish to have logging enabled see→**Step 12:** 

- *This will show you what ads were blocked and similar information.*

When you get to the **Installation Completed** window, **DO NOT CLOSE IT** we will want to come back to this information.

**Step 12:** Head to your Pi-Hole admin page → open your browser of choice and type: 

**Pi-hole.local/admin**

Use the forget password option and set a new personal password. *(You are given a password on the completed installation page, but I recommend you set your own)*

**Step 13:** Now that you are logged into your admin panel go back to your network settings and configure your home network DNS, to the IPV4 provided in the **Installation Complete** window.

---

🎉**Congrats!** You have now successfully configured your Pi-Hole! Up next will be extra blocklists and a regex rule you can use! You can close this section.

--- 

## Blocklists & regex rules

---

For a list of additional blocklists see this git!

> [DNS Blocklists - For a better internet!](https://github.com/hagezi/dns-blocklists?tab=readme-ov-file#pro)⁶

Inside the admin panel of your Pi-Hole, add this regex rule:

`diproton-ads-[^\.]*\.hulu\.com\.akadns\.net`

This will block the ad services from Disney+ and Hulu.

---


# Analyst Comments: 

You can also just use a [RPi Zero W](https://www.raspberrypi.com/products/raspberry-pi-zero-w/)³ or even a just an [RPI Zero](https://www.raspberrypi.com/products/raspberry-pi-zero/)⁴ if you didn’t want to slow down your Wi-Fi network. Make sure you have a [Micro-USB to Ethernet](https://www.amazon.com/Smays-Micro-B-Ethernet-compatible-Raspberry/dp/B01AT4C3KQ/ref=mp_s_a_1_3?crid=2EK2IAJT2DHN5&dib=eyJ2IjoiMSJ9.qLbfgmPIojtNLm5-m4LrI_ugoG_tW6WI70oG-soS7tYc7OnCky_kZyI_G1jMMA1b1a4X-N8ipBa2bmkdwxxQL18PfwfTAaoNAK0TNMfAfobPXyoLDR9d58i13G9_PoUS6Xbi2bc1VMN9x4uO1LT7pnNXR5THw2tnAILO90orcayIjvOKl5dB9SLERvfHBu3Epd8Wlq2pdXIBEnHf2sc6Cg.PlzAFO1ukCv-lcsbh9y8Xo4uchdZKaET3OofXoGDaoA&dib_tag=se&keywords=micro+usb+to+ethernet+adapter&qid=1773245899&s=electronics&sprefix=microUSB+to+Ethern%2Celectronics%2C189&sr=1-3)⁵ adapter then hard wire directly into your router.* 

Protecting yourself from unwanted traffic on a network **you** pay for is not a crime. 

Analyst: **Echo**  

*No LLMs were used in the creation of this walkthrough.*
# //END WALKTHROUGH// 

##  Sources, and Research - 

[Pi-Hole Documentation](https://docs.pi-hole.net/main/basic-install/)

[https://www.reddit.com/r/pihole/](https://www.reddit.com/r/pihole/comments/1k5zxxf/blocking_ads_on_disney_plus/)

[https://www.youtube.com/@wesops](https://www.youtube.com/watch?v=d_3h5n9mPdI)


#### Links:  

¹ [https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/](https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/)  

² https://www.raspberrypi.com/software/

³ https://www.raspberrypi.com/products/raspberry-pi-zero-w/

⁴ https://www.raspberrypi.com/products/raspberry-pi-zero/

⁵ [https://www.amazon.com/Smays-Micro-B-Ethernet-compatible-Raspberry](https://www.amazon.com/Smays-Micro-B-Ethernet-compatible-Raspberry/dp/B01AT4C3KQ/ref=mp_s_a_1_3?crid=2EK2IAJT2DHN5&dib=eyJ2IjoiMSJ9.qLbfgmPIojtNLm5-m4LrI_ugoG_tW6WI70oG-soS7tYc7OnCky_kZyI_G1jMMA1b1a4X-N8ipBa2bmkdwxxQL18PfwfTAaoNAK0TNMfAfobPXyoLDR9d58i13G9_PoUS6Xbi2bc1VMN9x4uO1LT7pnNXR5THw2tnAILO90orcayIjvOKl5dB9SLERvfHBu3Epd8Wlq2pdXIBEnHf2sc6Cg.PlzAFO1ukCv-lcsbh9y8Xo4uchdZKaET3OofXoGDaoA&dib_tag=se&keywords=micro+usb+to+ethernet+adapter&qid=1773245899&s=electronics&sprefix=microUSB+to+Ethern%2Celectronics%2C189&sr=1-3)
