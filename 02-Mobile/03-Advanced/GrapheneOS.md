# Graphene OS

## Table of Contents
* [1. Intro](#intro)
* [2. Installing](#installing)
* [3. VPN](#vpn)
* [4. Scopes](#contact-&-storage-scopes)
* [5. Open Source Apps](#open-source-apps)
* [6. Close Source Apps](#close-source-apps)
* [7. Profiles](#profiles)
* [8. Sandboxed Google Play](#sandboxed-google-play)
* [9. Web Apps](#web-apps)

<br/>

## Intro

- Follow these instructions to set up a fairly private, modern-feeling, and secure phone fit for every day use.

- GrapheneOS is a privacy and security focused Android Operating System for Google Pixel smartphones.

- Think of it as an escape from Google, Apple, and much of tech that is tracking you in addition to hoarding your data.

- Use this guide any time you need to redeploy or need a reminder.

<details><summary>**First time? Click to expand ...**</summary>

### What is this?

Are you currently using default Android OS or an iPhone and looking to regain your privacy? Here you'll find everything you need to get started on your journey.

This page is in an attempt to make the task of buying, configuring, and using a private/secure alternate phone OS as easy as possible. Once familiar, you can use this guide you can deploy a phone in about 30 minutes.

Graphene OS is the only option we can recommend at this point for a phone Operating System. It's an Open Source project that puts privacy and security first. The OS only runs on Google Pixel devices, so that's the phone you'll need to use.

### Buying a phone

The current recommendation is an Unlocked Google Pixel 8 or any model after, and NEVER use any model prior to the Google Pixel 6 as they do not have the Titan M2 secure element chip.

If you don't already own a Google Pixel you'll need to purchase one. Before buying your device confirm that it is a carrier unlocked phone or you will not be able to install Graphene OS.

Some ideas for purchase are Amazon, eBay, or just walk into a Best Buy with cash and purchase one.

### Cell service

Many people get comfortable enough with Graphene OS to use it every day, and in that case you will probably need phone service. There are many different threat models, and most do not mind the tradeoffs of having access to cellular data services.

If considering a threat model, see this information.  [Clearnet Link](https://grapheneos.org/faq#cellular-tracking)

It is not required to purchase a SIM card or eSIM from a company like AT&T or Tmobile if you are not trying to make this an every day carry phone. You can use this device as Wifi only or even keep it totally offline depending on your needs.

### Open Source vs Close Source

Open Source apps are suggested in this guide and we urge avoiding Closed Source apps wherever possible. Since the source code is available for everyone to see, any attempts by Open Source apps to track users or collect data are visible. There is a lot less incentive for Open Source app projects to attempt tracking users.

For example, Organic Maps was selected for the [Suggested Apps](#-main-profile-suggested-apps) list because it has much better privacy than Google Maps. This claim can be verified thanks to the Organic Maps code being Open Source.

### Graphene OS Resources

Features -                [Clearnet Link](https://grapheneos.org/features)
Usage -                   [Clearnet Link](https://grapheneos.org/usage)
FAQ -                     [Clearnet Link](https://grapheneos.org/faq)
Vanadium -                [Clearnet Link](https://grapheneos.org/features#vanadium)

### Videos

Graphene OS Install -   [Clearnet Link](https://www.youtube.com/watch?v=CD4Jl6ZYEbw)
Application Install -   [Clearnet Link](https://www.youtube.com/watch?v=IAoCfrqxIEg)
Review of GrapheneOS -  [Clearnet Link](https://youtu.be/hbs7EPSaauI)
GrapheneOS Road Trip -  [Clearnet Link](https://youtu.be/rp--qY9eSYI)

</details>
<br/>

## Installing

Grab your Google Pixel phone and let's get started with the de-Googling.

1. Make sure the default Android OS on the Pixel has the latest system updates.

2. Go to Settings > About and repeatedly tap the "Build Number" menu entry until developer mode is enabled.

3. Next, go to Settings > System > Developer and toggle ON the "OEM unlocking" setting and "USB debugging" setting. Note for Pixel 6a users, the "OEM unlocking" will not be available with the default OS from the factory. You need to update and factory reset the device to fix it.

4. Reboot the phone while pressing the volume down button, and continue to hold it until the phone boots into the bootloader interface. Then you can release the volume down button once you see the interface.

5. Now you can plug the phone into your desktop computer (or another Pixel phone) and proceed with Graphene OS web installer. [Clearnet Link](https://grapheneos.org/install/web#unlocking-the-bootloader)

<br/>

## VPN

### Suggested VPN

Currently the easiest and best VPN to setup after installing Graphene OS is called IVPN. If you don't have an IVPN subscription this is a good method to acquire one.

1. Go to your Main Profile apps, open the app named "App Store", and choose to install Accrescent.

2. Open Accrescent app and choose to install the IVPN app.

3. Open Tor browser on your desktop PC, and register for IVPN service using this link. [Clearnet Link](https://www.ivpn.net/en)

4. Use the login code IVPN provides to activate the IVPN app.

5. Go to your phone Settings > Network & Internet > VPN > Enable Always-on VPN > Enable Block connection without VPN

### Alternative VPN

1. Mullvad VPN -  [Tor Link](https://protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion) | [Clearnet Link](https://mullvad.net)

2. Proton VPN  -  [Tor Link](https://protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion/) | [Clearnet Link](https://protonvpn.com)

3. (Optional) Later on, consider trying the Wireguard app along with Wireguard VPN config files which are provided by whatever VPN service you have chosen. Keep in mind the Wireguard app is included in the [Quick Deploy File](#obtainium) below.

<br/>

## Contact & Storage Scopes

It is helpful to know the "scopes" feature and how you can limit access that apps have to your data.

1. Be advised, when installing new apps that access Contacts or stored media such as photos, Graphene will show a pop-up to notify you of the "scopes" feature for your newly installed app. 

2. If you choose to enable "scopes", the app will not have acccess to your Contacts or Storage data. For example, you probably don't want to enable "scopes" when installing an app you need to edit photos taken with your camera, as you would not have access to where the photos are stored.

3. Make a mistake installing an app? Uninstall, reinstall, and try again!

<br/>

## Open Source Apps

Downloading Open Source apps without the Google Play Store is easier than you think.

Let's explore some Open Source app options!

<details><summary>**Click to expand ...**</summary>

### Obtainium

Obtainium allows you to install and update apps directly from their source release pages, and receive notifications when new releases are made available. This is a by far the best option available to download and update Open Source apps.

1. To install Obtainium, download the file called `app-release.apk` from the releases page and open it. [Clearnet Link](https://github.com/ImranR98/Obtainium/releases)

2. (Optional) For a quick app deployment, download the [obtainium-quick-deploy.json](https://github.com/thesovereignrepo/The-Sovereign-Repository/blob/master/Mobile) file and import it into the Obtainium app. This will add every app on the [Suggested Apps](#-main-profile-suggested-apps) list below.

3. (Optional) Manually copy/paste Github links into Obtainium to download any apps you want.

### Main Profile Suggested Apps

AppVerifier -    [Clearnet Link](https://github.com/soupslurpr/AppVerifier)
AuroraStore -    [Clearnet Link](https://auroraoss.com/downloads/AuroraStore/Release)
BreezyWeather -  [Clearnet Link](https://github.com/breezy-weather/breezy-weather)
Deadhash -       [Clearnet Link](https://github.com/CodeDead/DeadHash-android)
Calendar -       [Clearnet Link](https://github.com/FossifyOrg/Calendar)
FUTOkeyboard -   [Clearnet Link](https://github.com/futo-org/android-keyboard)
Island -         [Clearnet Link](https://f-droid.org/en/packages/com.oasisfeng.island.fdroid)
InviZiblePro -   [Clearnet Link](https://github.com/Gedsh/InviZible)
KeePassDX -      [Clearnet Link](https://github.com/Kunzisoft/KeePassDX)
Markor -         [Clearnet Link](https://github.com/gsantner/markor)
Nekogram -       [Clearnet Link](https://github.com/Nekogram/Nekogram)
NewPipe -        [Clearnet Link](https://github.com/TeamNewPipe/NewPipe)
OpenKeychain -   [Clearnet Link](https://github.com/open-keychain/open-keychain)
OrganicMaps -    [Clearnet Link](https://github.com/organicmaps/organicmaps)
Protonmail       [Clearnet Link](https://github.com/ProtonMail/android-mail)
Signal -         [Clearnet Link](https://signal.org)
SimpleX -        [Clearnet Link](https://github.com/simplex-chat/simplex-chat)
Spotube -        [Clearnet Link](https://github.com/KRTirtho/spotube)
TorBrowser -     [Clearnet Link](https://www.torproject.org/download/#android)
Wireguard -      [Clearnet Link](https://download.wireguard.com/android-client)

</details>
<br/>

## Close Source Apps

It is possible to download Close Source apps like Instagram, Facebook, or Banking from the Google Play Store if you absolutely need to.

Let's explore how to manage the less desireable apps!

<details><summary>**Click to expand ...**</summary>

### Profiles

If downloading apps from Google Play, then first it is suggested to use the Island app to create a Work Profile.

1. (Optional) Skip to step 3 if you used the [Quick Deploy File](#obtainium).

2. (Optional) Download and install the Island app using the [Suggested Apps](#-main-profile-suggested-apps) list.

3. Open the Island app and choose to set up your Work Profile.

4. Open the apps list by swiping upward on the phone home screen, and you will see the new Work Profile at the top.

### Aurora Store

Aurora Store allows you to download apps from Google Play Store without having to install Google Play Store. Make sure to create a [Work Profile](#profiles) for the nasty apps like Facebook or Instagram!

1. (Optional) Skip to step 3 if you used the [Quick Deploy File](#obtainium).

2. (Optional) Download and install the Aurora Store app using the [Suggested Apps](#-main-profile-suggested-apps) list.

3. Open the Island app, and clone the Aurora Store app to your new Work Profile.

4. Download the apps you need from Aurora Store on your Work Profile.

</details>
<br/>

## Sandboxed Google Play

Google Play Services are not installed by default. You might notice that notifications don't work for some Google Play Apps in Graphene OS, or maybe some apps fail to run such as Banking apps. This is because some apps depend on Google Play Services, and luckily the developers provide a way to install Google Play Services "Sandboxed", so you can have all the functionality the default Android OS users do.

1. Go to your Work Profile apps, open the app called "App Store", and choose to install Google Play Services.

2. Once installed you should have full functionality needed for your Work Profile apps.

3. Pause your Work Profile when not in use to avoid having Google Play Services running in the background 24/7.

<br/>

## Web Apps

Don't want to use Aurora Store to download apps from Google Play? Don't want to enable Google Play Services?

1. Try using Web Apps like https://uber.com instead of downloading apps wherever possible.

2. If this is an every day carry phone, then try to keep Web Apps in mind for things like reservations, travel, shopping, etc.

<br/>

## TODO

TODO: Backups
TODO: Verify apps not in AppVerifier database, explain getting AppVerifier from Accrescent
TODO: Separate verified and non verified apps maybe?
TODO: Quick add to Obtanium buttons, additional requests for crowdsourced app list
TODO: Android 15 private spaces
TODO: Add pic for device support EOL
TODO: Further refine quick deploy and offline guides, screeshots or vid
