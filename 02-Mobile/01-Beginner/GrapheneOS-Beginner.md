# GrapheneOS Beginner

## Table of Contents
* [1. Intro](#intro)
* [2. Installing](#installing)
* [3. VPN](#vpn)
* [4. Apps](#apps)
* [5. Continue](#continue-your-training)

<br/>

## Intro

- Follow these instructions to setup a basic GrapheneOS phone.

- GrapheneOS is a privacy and security focused Android Operating System for Google Pixel smartphones.

- Think of it as an escape from Google, Apple, and much of tech that is tracking you in addition to hoarding your data.

- This beginner guide is Wifi only and does not support mobile data, or any apps from the Google Play app store.

<details><summary>**First time? Click to expand ...**</summary>

### What is this?

Are you currently using default Android OS or an iPhone and looking to regain your privacy? Here you'll find everything you need to get started on your journey.

This page simplifies the task of buying, configuring, and getting started with GrapheneOS. Once familiar, you can use this guide you can deploy a basic phone in about 30 minutes.

GrapheneOS is the only option we can recommend at this point for a phone Operating System. It's an Open Source project that puts privacy and security first. The OS only runs on Google Pixel devices, so that's the phone you'll need to use.

### Buying a phone

The current recommendation is an Unlocked Google Pixel 8 or any model after, and NEVER use a model prior to the Google Pixel 6 as they do not have the Titan M2 secure element chip.

If you don't already own a Google Pixel you'll need to purchase one. Before buying your device confirm that it is a carrier unlocked phone or you will not be able to install GrapheneOS.

Some ideas for purchase are Amazon, eBay, or just walk into a Best Buy with cash and purchase one.

### Videos

GrapheneOS Install   -  [Clearnet Link](https://www.youtube.com/watch?v=CD4Jl6ZYEbw)
Review of GrapheneOS -  [Clearnet Link](https://youtu.be/hbs7EPSaauI)

</details>
<br/>

## Installing

Grab your Google Pixel phone and let's get started with the de-Googling.

1. Make sure the default Android OS on the Pixel has the latest system updates.

2. Go to `Settings` > `About` and repeatedly tap the "Build Number" menu entry until developer mode is enabled.

3. Next, go to `Settings` > `System` > `Developer` and toggle ON the `OEM unlocking` setting and `USB debugging` setting. Note for Pixel 6a users, the unlocking will not be available with the default OS from the factory. You need to update and factory reset the device to fix it.

4. Reboot the phone while pressing the volume down button, and continue to hold it until the phone boots into the bootloader interface. Then you can release the volume down button once you see the interface.

5. Now you can plug the phone into your desktop computer (or another Pixel phone) and proceed with the [GrapheneOS Web Installer](https://grapheneos.org/install/web#unlocking-the-bootloader).

<br/>

## VPN

### Suggested VPN

Currently the easiest and best VPN to setup after installing GrapheneOS is called IVPN. If you don't have an IVPN subscription this is a good method to acquire one.

1. Open the app named App Store, and choose to install Accrescent.

2. Open Accrescent app and choose to install the IVPN app.

3. Using Tor browser on your desktop PC, pay for for IVPN service using this link. [Clearnet Link](https://www.ivpn.net/en)

4. Use the login code IVPN provides to activate the IVPN app, and make sure to store this code in your password manager.

5. Go to your phone Settings > Network & Internet > VPN > Enable Always-on VPN > Enable Block connection without VPN

### Alternative VPN

1. Mullvad VPN -  [Tor Link](https://protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion) | [Clearnet Link](https://mullvad.net)

2. Proton VPN  -  [Tor Link](https://protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion/) | [Clearnet Link](https://protonvpn.com)

<br/>

## Apps

Downloading Open Source apps without the Google Play Store is easier than you think.

Let's explore some Open Source app options!

<details><summary>**Click to expand ...**</summary>

### Obtainium

Obtainium allows you to install and update apps directly from their source release pages, and receive notifications when new releases are made available. This is a by far the best option available to download and update Open Source apps.

1. To install Obtainium, download the file called `app-release.apk` from the releases page and open it. [Clearnet Link](https://github.com/ImranR98/Obtainium/releases)

2. (Optional) For a quick app deployment, download the [obtainium-quick-deploy.json](https://github.com/thesovereignrepo/The-Sovereign-Repository/blob/master/02-Mobile) file and import it into the Obtainium app. This will add every app on the [Suggested Apps](#-main-profile-suggested-apps) list below.

3. (Optional) Or manually copy/paste Github links into Obtainium to download any apps you want.

### Main Profile Suggested Apps

BreezyWeather -  [Clearnet Link](https://github.com/breezy-weather/breezy-weather)
Calendar -       [Clearnet Link](https://github.com/FossifyOrg/Calendar)
FUTOkeyboard -   [Clearnet Link](https://github.com/futo-org/android-keyboard)
KeePassDX -      [Clearnet Link](https://github.com/Kunzisoft/KeePassDX)
Markor -         [Clearnet Link](https://github.com/gsantner/markor)
Nekogram -       [Clearnet Link](https://github.com/Nekogram/Nekogram)
NewPipe -        [Clearnet Link](https://github.com/TeamNewPipe/NewPipe)
OrganicMaps -    [Clearnet Link](https://github.com/organicmaps/organicmaps)
Protonmail -     [Clearnet Link](https://github.com/ProtonMail/android-mail)
Signal -         [Clearnet Link](https://github.com/signalapp/Signal-Android)
SimpleX -        [Clearnet Link](https://github.com/simplex-chat/simplex-chat)
Spotube -        [Clearnet Link](https://github.com/KRTirtho/spotube)
TorBrowser -     [Clearnet Link](https://www.torproject.org/download/#android)
Wireguard -      [Clearnet Link](https://download.wireguard.com/android-client)

</details>
<br/>

## Continue Your Training

Curious about how to safely manage apps from Google Play app store, want to maintain sensitive data, or ready to step up and turn GrapheneOS into your every day carry?

1. Continue to the [Advanced GrapheneOS Guide](https://github.com/thesovereignrepo/The-Sovereign-Repository/tree/master/02-Mobile/Advanced/GrapheneOS-Advanced.md) or the [Offline GrapheneOS Guide](https://github.com/thesovereignrepo/The-Sovereign-Repository/tree/master/02-Mobile/Advanced/GrapheneOS-Offline.md) when you are ready to continue your training.

2. Keep in mind, you can Factory Reset at any time for a fresh start, and continue to the next guide.
