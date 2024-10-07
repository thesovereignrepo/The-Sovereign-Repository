# Graphene OS

## Table of Contents
* [1. Intro](#intro)
* [2. Installing](#installing)
* [3. VPN](#vpn)
* [4. Apps](#apps)
* [5. Profiles](#profiles)
* [6. Sandboxed Google Play](#sandboxed-google-play)
* [7. Web Apps](#web-apps)
* [8. Wallet](#wallet)
* [9. Backup](#backup)
* [10. Videos](#videos)

<br/>

## Intro

- GrapheneOS is a privacy and security focused Android Operating System for Google Pixel smartphones.

- Think of it as an escape from Google, Apple, and much of tech that is tracking you in addition to hoarding your data.

- Follow the table of contents to set up a decently private, modern-feeling, and secure phone.

- Use this guide any time you need to redeploy or need a reminder.

<details>

<summary>**>> First time? Click to expand**</summary>

### What is this?

Are you currently using default Android OS or an iPhone and looking to regain your privacy? Here you'll find everything you need to get started on your journey.

This page is in an attempt to make the task of buying, configuring, and using a private/secure alternate phone OS as easy as possible. Once familiar, you can use this guide you can deploy a phone in about 30 minutes.

Graphene OS is the only option we can recommend at this point for a phone Operating System. It's an Open Source project that puts privacy and security first. The OS only runs on Google Pixel devices, so that's the phone you'll need to use.

### Buying a phone

If you don't already own a Google Pixel you'll need to purchase one. Before buying your device confirm that it is fully unlocked or you will not be able to install Graphene OS.

Some ideas for purchase are Amazon, eBay, or just walk into a Best Buy with cash and purchase one.

### Cell service

You do not need to purchase a SIM card or eSIM from a company like AT&T or Tmobile unless you are trying to make this an every day carry.

Many people get comfortable enough with Graphene OS to use it every day, and in that case you will probably need data services.

When considering your threat model, see this information - [Clearnet Link](https://grapheneos.org/faq#cellular-tracking)

###  Graphene OS Resources

Features -                [Clearnet Link](https://grapheneos.org/features) 
Usage -                   [Clearnet Link](https://grapheneos.org/usage)
FAQ -                     [Clearnet Link](https://grapheneos.org/faq)
Camera -                  [Clearnet Link](https://grapheneos.org/usage#grapheneos-camera-app)
PDF Viewer -              [Clearnet Link](https://grapheneos.org/features#grapheneos-pdf-viewer)
Vanadium -                [Clearnet Link](https://grapheneos.org/features#vanadium)
Auto reboot -             [Clearnet Link](https://grapheneos.org/features#auto-reboot)
Wi-Fi/Bluetooth timeout - [Clearnet Link](https://grapheneos.org/features#attack-surface-reduction)
Pin Scrambling -          [Clearnet Link](https://grapheneos.org/features#pin-scrambling)

</details>

<br/>

## Installing

1. Make sure the default Android OS on the pixel is has the latest system updates.

2. Enable the developer options menu by going to Settings > About and repeatedly tapping the "Build Number" menu entry until developer mode is enabled.

3. Next, go to Settings > System > Developer options and toggle on the "OEM unlocking" setting and "USB debugging" setting. Note for the Pixel 6a, OEM unlocking won't work with the version of the stock OS from the factory. You need to update it and factory reset the device to fix it.

4. Now you can plug the phone into your PC and proceed with the web installer. [Clearnet Link](https://grapheneos.org/install/web)

5. For visual learners, follow along with this video. [Clearnet Link](https://www.youtube.com/watch?v=CD4Jl6ZYEbw)

## VPN

Please consider using Tor browser to register for a VPN service before proceeding. Here are some suggestions.

1. Mullvad VPN - [Tor Link](https://protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion) | [Clearnet Link](https://mullvad.net)

2. IVPN - [Clearnet Link](https://www.ivpn.net/en/wireguard)

3. Proton VPN - [Tor Link](https://protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion/) | [Clearnet Link](https://protonvpn.com)

TODO: Wireguard

## Apps

When it comes to downloading apps there are some options to consider. 

This guide suggests using Open Source apps downloaded via Obtainium for your Main Profile, and a Work Profile can be created for all the nasty tracking apps like Facebook or Instagram.

TODO: Contact/Storage scopes

### Obtainium

Obtainium allows you to install and update apps directly from their source release pages, and receive notifications when new releases are made available. This is a by far the best option available to download and update Open Source apps.

1. Download Obtainium app .apk from Github - [Clearnet Link](https://github.com/ImranR98/Obtainium)

2. (Optional) Import the [obtainium-quick-deploy.json](https://github.com/thesovereignrepo/The-Sovereign-Repository/blob/master/Mobile) file into the Obtainium app to quickly download everything listed in the Main Profile Example below.

3. (Optional) Manually copy/paste Github links into Obtainium to download any apps you want.

Main Profile Example Apps:
AppVerifier -     [Clearnet Link](https://github.com/soupslurpr/AppVerifier)
BreezyWeather -   [Clearnet Link](https://github.com/breezy-weather/breezy-weather)
Deadhash -        [Clearnet Link](https://github.com/CodeDead/DeadHash-android)
Calendar -        [Clearnet Link](https://github.com/FossifyOrg/Calendar)
Dicio -           [Clearnet Link](https://github.com/Stypox/dicio-android)
Heliboard -       [Clearnet Link](https://github.com/Helium314/HeliBoard)
Insular -         [Clearnet Link](https://f-droid.org/en/packages/com.oasisfeng.island.fdroid/)
InviZiblePro -    [Clearnet Link](https://github.com/Gedsh/InviZible)
KeePassDX -       [Clearnet Link](https://github.com/Kunzisoft/KeePassDX)
Markor -          [Clearnet Link](https://github.com/gsantner/markor)
Nekogram -        [Clearnet Link](https://github.com/Nekogram/Nekogram)
NewPipe -         [Clearnet Link](https://github.com/TeamNewPipe/NewPipe)
OpenKeychain -    [Clearnet Link](https://github.com/open-keychain/open-keychain)
OrganicMaps -     [Clearnet Link](https://github.com/organicmaps/organicmaps)
Protonmail        [Clearnet Link](https://github.com/ProtonMail/android-mail)
Signal -          [Clearnet Link](https://signal.org)
SimpleX -         [Clearnet Link](https://github.com/simplex-chat/simplex-chat)
Spotube -         [Clearnet Link](https://github.com/KRTirtho/spotube)
TorBrowser -      [Clearnet Link](https://www.torproject.org/download/#android/)
Wireguard -       [Clearnet Link](https://download.wireguard.com/android-client)

TODO: Verify apps not in AppVerifier database
TODO: Quick add to Obtanium buttons, crowdsourced app list

### Aurora Store

Aurora Store allows you to download apps from Google Play Store without having to install Google Play Store. Make sure to create a [Work Profile](#profiles) for these apps!

1. Download Aurora Store app .apk from Gitlab - [Clearnet Link](https://gitlab.com/AuroraOSS/AuroraStore)

2. Download the apps you need from Aurora Store, but always keep in mind they are coming from Google Play Store.

3. (Optional) Continue to the [Sandboxed Google Play](#sandboxed-google-play) section below if needed.

Work Profile Example Apps:
Aurora Store
Brave Browser
Instagram
Uber
X 

## Profiles

TODO: Insular App, Work Profiles vs Main Profile

## Sandboxed Google Play

Google Play Services (GPS) are not installed by default. You might notice that notifications don't work for some Apps in GrapheneOS or maybe some apps fail to run (such as banking apps). The reason for this is that some apps depend on Google Play Service, but GrapheneOS doesn't have those. Luckily the developers provide a way to install Google Play Service Sandboxed, so you can have all the functionality available on a device with stock Android OS. GrapheneOS.org has a great write up on the details of the implementation that I would suggest reading.

## Web Apps

Don't want to use Aurora Store to download apps from Google Play Store? Don't want to enable Sandboxed Google Play Services? Try using Web Apps like https://uber.com instead of downloading an app.

If this you are using this as a main device try to keep this in mind for reservations, travel, shopping, etc.

## Backups

TODO: Contact, Calendar, Data storage

Most of us use our phones for communicate with people and to store our calendars.
    Free Secure Cloud Contact Storage - ADD URLS
    Free Secure Cloud Calendar Storage

Phones get lost/stolen everyday. Protect your data by taking a backup in case this happens to you.
    How to backup GrapheneOS - ADD URLS
    How to restore GrapheneOS from a backup

Seedvault
"...the project has been taken over by another group of people not sharing our goals or approach. For now, this is the best available option, so we're including it to give people encrypted backup support. We've made several security fixes to work around upstream issues with the project."

## Videos

Here's a review video of GrapheneOS - https://youtu.be/hbs7EPSaauI
GrapheneOS on a road trip test - https://youtu.be/rp--qY9eSYI
App stores - https://www.youtube.com/watch?v=IAoCfrqxIEg
