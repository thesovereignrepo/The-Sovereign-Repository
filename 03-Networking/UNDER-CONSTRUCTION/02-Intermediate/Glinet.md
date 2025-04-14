# Glinet Mudi Mobile Router
Picture1

<br/>

## Table of Contents
* [1. Intro](#intro)
* [2. SIM Card](#sim-card)
* [3. Purchase Prebuilt](#purchase-prebuilt)
* [4. DIY Build](#diy-build)
* [5. Setup](#setup)
* [6. Changing SIM](#changing-sim)
* [7. Updating](#updating)
* [8. FAQ](#faq)
* [9. Continue](#continue-your-training)

<br/>

## Intro

- Glinet's Mudi Mobile Router securely connects your smartphone or laptop to the internet while on the move. The main function is the router acts as a mobile hotspot using SIM card or E-SIM. Your laptop or smartphone can be connected via Wifi, Ethernet, or USB tethering.

- Thanks to the Blue Merle software, it is possible to swap SIM cards and actually maintain privacy with mobile internet. The trick is the device IDs of the Mudi Mobile Router known as IMEI, BSSID and MAC are random, and can be changed to prevent tracking of the device (e.g. by IMSI catchers).

- Finally! A solution to private mobile internet. Anyone out there who does not want their normal mobile data provider to see they are using Tor, this is your lucky day.

- The Open Source software being used is OpenWRT / Blue Merle. The hardware being used is the Glinet Mudi 4G LTE Mobile Router (GL-E750V2).

- Anonymous mobile surfing is possible using integrated Tor. Tor can be easily controlled via a web interface and requires no software installation. Your data is routed via a network of several Tor servers, thus anonymizing the data flow.

- Internet access via VPN is possible, transmits your data securely encrypted, and protects against local eavesdropping and manipulation. Use any VPN service via WireGuard or OpenVPN without additional software. You can even run a VPN server on this Mudi Mobile Router.

- Interception and manipulation of Internet addresses (DNS) by man-in-the-middle attacks is prevented via DNS over TLS (DoT).

<details><summary>**Need More Details? Click to expand ...**</summary>

### What is this?

The SRLabs research team behind the open-source Blue Merle project have identified and mitigated remote and local data leakage risks for users of the Glinet Mudi 4G LTE router. The average mobile router (also called Hotspot) offers users a convenient and reliable internet connection when other options are unavailable, but unfortunately they also render associated activity and traffic vulnerable to tracking methods used by mobile network operators.

Users interested in using mobile networks anonymously must change each identifying element associable with 4G LTE routers and linked devices, namely IMSI/IMEI numbers, router BSSIDs, and device MAC addresses. This guide will help you with the solution to this difficult problem by utilizing the the marriage of Glinet Mudi Mobile Router hardware, and Blue Merle software.

### Using Cellular Networks Anonymously

Mobile network operators use several identifiers to identify their users, making it hard to use cellular networks anonymously. Techniques typically used to avoid tracking, such as changing SIM cards, fail to account for other personal identifiers such as International Mobile Equipment Identity (IMEI) numbers. Device owners looking to use mobile networks anonymously must instead use techniques that change each identifying element of their mobile phones.

SRLabs researchers examined the Glinet Mudi 4G LTE (GL-E750) router as part of their company’s ongoing mobile network security research efforts. The travel router features native privacy-enhancing features such as Tor and user-defined VPN support shielding its user’s associated network traffic. The examination of the Mudi 4G LTE router uncovered several unmitigated tracking risks at the Wi-Fi and cellular protocol levels. The Mudi also stores Media Access Control (MAC) addresses of connected devices, which can be used to identify user devices that have previously connected to the travel router.

SRLabs released the Blue Merle software package containing fixes that researchers developed to mitigate deanonymization risks uncovered during the investigation of the Mudi 4G LTE router. The Blue Merle project adds additional privacy protections to the Mudi device designed to reduce forensic traces that could be used by mobile network operators to identify its users. The project’s source code and detailed documentation is available on the [SRLabs GitHub](https://github.com/srlabs/blue-merle).

### Threats

Before learning about features, first it's wise to understand what threats are being faced by users.

1. Tracking of the Mudi’s activity, location, and, in some cases, the identification of the purchaser is possible through the IMEI. The simplest method of mobile-network tracking uses the International Mobile Subscriber Identity (IMSI) number, which uniquely identifies a subscriber by their SIM card. This tracking method can be mitigated by regularly changing SIM cards. However, the mobile device counterpart to the IMSI, namely its unique IMEI, remains the same across SIM changes. The common notion that changing the SIM card – ideally to an anonymous one – results in a completely new identity is wrong. If a user changes their SIM but continues to use the same device, a connection to their so-called new identity can be drawn through the unchanged IMEI. A device IMEI might even be traceable to a specific purchase, allowing for direct identification of the purchaser.

https://cdn.prod.website-files.com/636034b5be6f5507ed57c4ca/6422d5c9a28993f7ec03e073_63d94dbaf73e4c367e6ae7d9_Screenshot%25202023-01-31%2520at%25206.19.00%2520PM.png
Picture Detail 1: illustrates how IMSI and IMEI identifiers can be linked if not changed simultaneously. Only by changing IMEI and IMSI at the same time can the user shake off all traces accumulated by their previous subscriber- and device-based identity.
Picture Detail 2: Identity linkability across different IMEI and IMSI change scenarios

2. The BSSID and MAC address allow for activity and Wi-Fi-based location tracking. The Basic Service Set Identifier (BSSID) is associated with a specific WLAN access point and is referenced in all wireless packets associated between the access point and connected clients. By convention, an access point’s MAC address is used as the ID of a BSS. BSSIDs are constantly transmitted by both the Mudi device and connected clients when the Mudi is offering a Wi-Fi network. By passively collecting Wifi network identifiers such as BSSIDs, device identifiers – including that of the Mudi router – can be mapped to fixed locations.

Like other mobile routers, the Mudi 4G LTE router records the MAC addresses of connected devices. MAC addresses uniquely identify a device’s network adapter and are assigned during the manufacturing process. A connected device’s stored MAC address serves as a uniquely identifying element that can be tied to the device user. In case of a device’s loss, theft or confiscation, this data collection may prove detrimental to the users’ privacy interests.  Additionally, the MAC address can be collected by passive intercept as it is not encrypted. Therefore, the unique and static MAC address is in itself a risk for activity and location tracking.  

### Solutions

Blue Merle provides solutions to the privacy limitations of the Mudi router by providing the following features.

1. IMEI randomization. Blue Merle enforces an IMEI randomization upon every SIM card change to break the linkage between the subscriber and device identities. The Mudi router’s baseband unit is a Quectel EP06-E/A Series LTE Cat 6 Mini PCIe module. Its IMEI can be changed by issuing Quectel LTE series-standard AT commands. The AT command to write a new IMEI to a Quectel EP06-E/A-based device is AT+EGMR.

Blue Merle’s IMEI randomization functionality is built around this command and offers two distinct approaches to IMEI generation. The first deterministic method seeds the new value with the user’s IMSI, while the second randomizing method generates a fully random IMEI. Multiple IMEI changes increase the likelihood of alerting an ISP of suspicious behavior. Therefore, the Blue Merle project team recommends constraining usage of the IMEI randomization option to **only** when the SIM card is changed.

Ideally IMEI randomization occurring when the SIM card is changed would associate a single, randomly generated IMEI to that SIM card. However, this would require the new IMEI to be stored within the device. The Blue Merle package ensures the IMEI is deleted from the router when the SIM card is removed. To ensure that there is no leakage of the old IMEI after rebooting the device, the radio is turned off in advance. This disrupts the device’s connection with the mobile network during the time the IMEI is changed, and the connection is only reestablished after rebooting the device.

‍2. BSSID and MAC randomization. Since BSSIDs are another case of personally identifiable data, randomizing it serves as a strong privacy measure. The Blue Merle package regularly randomizes the Mudi router’s BSSID to eliminate another uniquely identifying artifact. Also, Wifi clients such as mobile phones frequently leak SSIDs, and in some cases BSSIDs of Wifi connections they have previously connected to. Changing the Mudi router’s BSSID eliminates the risk posed by this source of persistent data leakage and subsequent Wifi based location tracking attempts.

A Blue Merle-modified Mudi router removes links to past activities, whereabouts, and Wifi connections by using a different MAC address on each boot. The Mudi router BSSID is set by the process hostapd using the function `mac80211_prepare_vif()` in `/rom/lib/netifd/wireless/mac80211.sh`. The resulting BSSID is stored in `/etc/config/wireless`. 

The Blue Merle BSSID randomization function generates a valid unicast address value and overrides the current MAC values set for the `wlan0` and `wlan1` interfaces. This is done by issuing the OpenWrt command uci set targeting the mac address fields of `wireless.@wifi-iface[0]` and `wireless.@wifi-iface[1]`. The Mudi router’s Wifi is then reset to implement the changes. The BSSID randomization feature is run on boot, ensuring that a new BSSID is generated each time the device is started.

3. MAC address log wiper. By wiping the Mudi router’s cache of stored MAC addresses at each boot, third parties with remote or physical access can no longer enumerate the devices that have connected to the Mudi router.

MAC addresses of devices that connected to the Mudi's Wi-Fi connection are stored in `/tmp/tertf(_bak)` and `/etc/tertf(_bak)`. The Blue Merle MAC address log wiper first symbolically links the `gl_tertf` file responsible for the gltertf process, which reads and logs MAC addresses. It then kills the gltertfprocess if active, checks if either file contains any data, and uses shred to delete any data if found. 

The MAC address log wiper is run on boot, ensuring that the Mudi device’s initial MAC log read/write functionality is disrupted each time the device is started.

### Videos

Unboxing Video   -  [Clearnet Link](https://www.youtube.com/watch?v=4FzEgmYyy7k)

DIY Install Video -  [Clearnet Link](https://www.youtube.com/watch?v=8BsbS6Mkcw4)

</details>
<br/>

## SIM Card

There are a few options when it comes to SIM, e-SIM, and the companies that provide you internet service.

### Physical SIM

The Mint Mobile Unlimited 3-month plan is a good match if you only need up to 10GB of Mobile Hotspot data per month. This is a prepaid plan that comes with a physical SIM card. It's sold in common stores such as Target or Best Buy can be purchased privately with cash. 

Mint Mobile Plans  -  [Tor Link](https://web.archivep75mbjunhxc6x4j5mwjmomyxb573v42baldlqu56ruil2oiad.onion/web/20250327173206/https://www.mintmobile.com/plans)

Mint Mobile Plans   -  [Clearnet Link](https://www.mintmobile.com/plans)

### Physical SIM 2

TBD

### E-SIM

TBD

<br/>

## Purchase Prebuilt

First, then consider a prebuilt if you wish to buy a plug-and-play device that "just works" out of the box.

1. Purchase the prebuilt, known as the Nitrowall, from the [Nitrokey Shop](https://shop.nitrokey.com/shop?&search=nitrowall) website.

2. Turn on the device and continue to the [Setup]() section (below).

<br/>

## DIY Build

Are you the DIY type? Great you can dive on in! The following DIY section is of course optional, see Purchase Prebuilt section (above) if you do not wish to perform a Do-It-Yourself setup. 

1. Purchase the Mudi router from the [Glinet Shop](https://www.gl-inet.com/products/gl-e750) website.

2. Expand the instructions below to continue with an offline or online install. Now is also a good time to bookmark the [Blue Merle Repo](https://github.com/srlabs/blue-merle).

<details><summary>**Click to expand DIY Build instructions ...**</summary>

### Offline Install

The offline install method does **not need an active Internet connection** on your Mudi device.

1. Download the [Prebuilt v2.0 Offline Release](https://github.com/srlabs/blue-merle/releases/download/v2.0/blue-merle_2.0.0-0_offline_install.zip) then execute the following commands.

2. Unzip the Blue Merle Offline Install package.
```
unzip /$HOME/$USER/download-name-here.zip
```

3. Connect your computer to the Mudi Router via Wifi or Ethernet. Default Wifi password is `goodlife`.

4. Copy the package to your Mudi. The `-O` might be needed due to SSH daemon used by Mudi.
```
scp -O -r blue_merle_install root@192.168.8.1:/tmp
```

5. Connect to Mudi via SSH.
```
ssh root@192.168.8.1
```

6. Execute the following commands.
```
cd /tmp/blue_merle_install
./install.sh
```

**Note**: The offline install package bundles dependencies collected in October 2023. These dependencies could be outdated at the time of installation and might not be compatible with future Mudi firmware versions.

### Online Install

The online install method requires an **active Internet connection** on your Mudi device to **download up-to-date dependencies**.

1. Download the [Prebuilt v2.0 Online Release](https://github.com/srlabs/blue-merle/releases/download/v2.0/blue-merle_2.0.0-0_mips_24kc.ipk) package.

2. Connect your computer to the Mudi Router via Wifi or Ethernet. Default Wifi password is `goodlife`.

3. Copy the package to your Mudi. The `-O` might be needed due to SSH daemon used by Mudi.
```
scp -O -r blue-merle*.ipk root@192.168.8.1:/tmp
```

4. Install the package file by running these commands.
```
cd /tmp/blue-merle*.ipk
opkg update
opkg install blue-merle*.ipk
```

</details>
<br/>

## Setup

1. Activate your SIM card from a random Wifi such as Public Library, Restaurant, or Gym.

2. Insert the SIM card into your Mudi device.

3. Turn device power on, and connect to the Wifi network GL-E750-XXX. Default password is `goodlife`.

4. Open the web interface at `http://192.168.8.1`.

5. Click the Auto Setup button and you should get internet access.

<br/>

## Changing SIM

1. Turn device power on, and flip the hardware switch to activate Blue Merle.

2. You should see `Disabled` on the screen followed by `Replace the SIM card. Then pull the switch.`

3. Replace the SIM card with a new one, then flip the hardware switch again.

4. You should see `Setting random IMEI` follwed by a new IMEI number.

5. Your device will then shutdown and display the message: `You should change your location before booting again.`

6. Change to a new location and power on your device.

7. Connect to the Wifi network GL-E750-XXX. Default password is `goodlife`.

8. Open the web interface at `http://192.168.8.1`.

9. Click the Auto Setup button and you should get internet access.

<br/>

## Updating

To update Blue Merle, download the newest blue-merle*.ipk, copy it to your Mudi and reinstall.

Details for the needed commands can be found in the [Online Install]() section. This guide will be edited once a new update is released and tested, there is no gurrantee that updates will go smoothly along with Mudi firmware updates until it's tested.

```
opkg install --force-reinstall blue-merle*.ipk
```

<br/>

## FAQ

Q: What is wrong with the Internet Service Provider on my everyday phone seeing I connect to the Tor Network?
A: Your ISP may put you on a list. For example, you probably paid for the internet on your regular phone with a credit card or some other method that reveals your identity. If you want privacy from that Internet Service Provider, then you will need to use one of these Mudi Mobile Routers for things like Tor Browser and other Tor-enabled Apps.

Q: Do I need to use this router instead of my main mobile device's internet?
A: No, you can keep the usage of this device to sensitive activites only. For example, using the using the Tor Browser or Tor-enabled Apps.

Q: Could I use this router instead of buying a SIM card for my phone?
A: Yes, this is a solution if you do not want your phone to register device IDs on a cellular network.

Q: How far do I need to travel between locations for a [SIM card change]()?
A: As far as makes you comfortable. Maybe that means down the street or it's miles/kilometers away. You decide.

Q: Do I have to enable Tor or VPN on the router or can I use it on a phone connected to this hotspot?
A: No you do not have to enable Tor or VPN at the router level. But the same rules apply as usual, for example if phone VPN App (or killswitches) fail then some info could be leaked to the internet service provider. 

Q: I have a VPN running on the Mudi router, but what about my phone's VPN/TOR app?
A: You can think of it as VPN (phone) over VPN (mudi). With Tor Browser or Tor-enabled App on your phone, think of it as Tor (phone) over VPN (mudi). The advantage you gain here is mainly being sure Tor runs over VPN, as the internet service provider cannot see you are using Tor since the traffic is encrypted by VPN. Some may prefer to never let their internet service provider know about Tor usage.

Q: I heard it's possible to track if the SIM card is changed, it's still the same hardware afterall?
A: No, thanks to Blue Merle all device ID's are roatated when you follow the instructions to perform a SIM swap. Expand the intro details of this guide for more info.

Q: How much money can I save if I do a DIY build?
A: About $150 USD. If your time is worth more than that, go for the prebuilt.

<br/>

## Continue Your Training

Ready to learn more about networking?

1. Continue to the [Pfsense Guide](https://github.com/thesovereignrepo/The-Sovereign-Repository/tree/master/03-Networking/Advanced/Pfsense.md).
