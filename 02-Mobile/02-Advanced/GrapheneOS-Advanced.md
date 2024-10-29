# GrapheneOS Advanced

## Table of Contents
* [1. Intro](#intro)
* [2. Installing](#installing)
* [3. VPN](#vpn)
* [4. Scopes](#contact-and-storage-scopes)
* [5. Open Source Apps](#open-source-apps)
* [6. Close Source Apps](#close-source-apps)
* [7. Private Space](#private-space)
* [8. Google Play](#sandboxed-google-play)
* [9. Web Apps](#web-apps)

<br/>

## Intro

- Follow these instructions to setup a fairly private, modern-feeling, and secure phone fit for every day use.

- GrapheneOS is a privacy and security focused Android Operating System for Google Pixel smartphones.

- Think of it as an escape from Google, Apple, and much of tech that is tracking you in addition to hoarding your data.

- Use this guide any time you need to redeploy a phone or need a reminder during phone setup.

<details><summary>**First time? Click to expand ...**</summary>

### What is this?

Are you currently using default Android OS or an iPhone and looking to regain your privacy? Here you'll find everything you need to get started on your journey.

This page is in an attempt to make the task of buying, configuring, and using a private/secure alternate phone OS as easy as possible. Once familiar, you can use this guide you can deploy a phone in about 1 hour.

GrapheneOS is the only option we can recommend at this point for a phone Operating System. It's an Open Source project that puts privacy and security first. The OS only runs on Google Pixel devices, so that's the phone you'll need to use.

### Buying a phone

The current recommendation is an Unlocked Google Pixel 8 or any model after, and NEVER use a model prior to the Google Pixel 6 as they do not have the Titan M2 secure element chip.

If you don't already own a Google Pixel you'll need to purchase one. Before buying your device confirm that it is a carrier unlocked phone or you will not be able to install GrapheneOS.

Some ideas for purchase are Amazon, eBay, or just walk into a Best Buy with cash and purchase one.

### Cell service

Many people get comfortable enough with GrapheneOS to use it every day, and in that case you will probably need phone service. There are many different threat models, and most do not mind the tradeoffs of having access to cellular data services.

If considering a threat model, see this information.  [Clearnet Link](https://grapheneos.org/faq#cellular-tracking)

It is not required to purchase a SIM card or eSIM from a company like AT&T or Tmobile if you are not trying to make this an every day carry phone. You can use this device as Wifi only or even keep it totally offline depending on your needs.

### Open Source vs Close Source

Open Source apps are suggested in this guide and we urge avoiding Closed Source apps wherever possible. Since the source code is available for everyone to see, any attempts by Open Source apps to track users or collect data are visible. There is a lot less incentive for Open Source app projects to attempt tracking users.

For example, Organic Maps was selected for the [Suggested Apps](#main-profile-suggested-apps) list because it has much better privacy than Google Maps. This claim can be verified thanks to the Organic Maps code being Open Source.

### GrapheneOS Resources

Features -  [Clearnet Link](https://grapheneos.org/features)
Usage -     [Clearnet Link](https://grapheneos.org/usage)
FAQ -       [Clearnet Link](https://grapheneos.org/faq)
Vanadium -  [Clearnet Link](https://grapheneos.org/features#vanadium)

### Videos

GrapheneOS Install -    [Clearnet Link](https://www.youtube.com/watch?v=CD4Jl6ZYEbw)
Application Install -   [Clearnet Link](https://www.youtube.com/watch?v=IAoCfrqxIEg)
Review of GrapheneOS -  [Clearnet Link](https://youtu.be/hbs7EPSaauI)
GrapheneOS Road Trip -  [Clearnet Link](https://youtu.be/rp--qY9eSYI)

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

1. Go to your apps, open the app named App Store, and choose to install Accrescent.

2. Open Accrescent app, and choose to install the IVPN app.

3. Open Tor browser on your desktop PC, and register for IVPN service using this link. [Clearnet Link](https://www.ivpn.net/en)

4. Use the login code IVPN provides to activate the IVPN app, and make sure to store this code in your password manager.

5. Go to your phone Settings > Network & Internet > VPN > Enable Always-on VPN > Enable Block connection without VPN

### Alternative VPN

1. Mullvad VPN -  [Tor Link](https://protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion) | [Clearnet Link](https://mullvad.net)

2. Proton VPN  -  [Tor Link](https://protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion/) | [Clearnet Link](https://protonvpn.com)

3. (Optional) Later on, consider trying the Wireguard app along with Wireguard VPN config files which are provided by whatever VPN service you have chosen. Keep in mind the Wireguard app is included in the [Quick Deploy File](#obtainium) below.

<br/>

## Contact and Storage Scopes

It is helpful to know the "scopes" feature and how you can limit access that apps have to your data.

1. Be advised, when installing new apps that access Contacts or stored media such as photos, Graphene will show a pop-up to notify you of the "scopes" feature for your newly installed app. 

2. If you choose to enable "scopes", the app will not have acccess to your Contacts or Storage data. For example, you probably don't want to enable "scopes" when installing an app you need to edit photos taken with your camera, as you would not have access to where the photos are stored.

3. Make a mistake installing an app and enabling "scopes" feature? Uninstall, reinstall, and try again!

<br/>

## Open Source Apps

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

## Close Source Apps

It is possible to download Close Source apps like Instagram, Facebook, or Banking if you absolutely need to.

Let's explore how to manage these less desireable apps which we know harvest your data!

<details><summary>**Click to expand ...**</summary>

### Private Space

The Private Space feature allows you to have a seperate area for the less desireable apps and it can be locked. If you want apps like Instagram or Facebook then continue with setting up a Private Space. The easiest and fastest method is reusing some of the steps from the [Suggested VPN]() section above, but feel free to modify with whatever VPN you prefer.

1. Go to `Settings` > `Security & privacy` > `Private space` to create your Private Space.

2. Go to your Private Space, open the app named App Store, and choose to install Accrescent.

3. Open Accrescent app, and choose to install the IVPN app.

4. Use the login code IVPN provides to activate the IVPN app.

5. Go to your phone Settings > Network & Internet > VPN > Enable Always-on VPN > Enable Block connection without VPN

### Aurora Store

Aurora Store allows you to download apps from Google Play Store without having to install Google Play Store. Make sure to create a [Private Space](#private-space) for the nasty apps like Facebook or Instagram!

1. Go to the Aurora Store Releases page and download the latest `AuroraStore.apk` file. [Clearnet Link](https://gitlab.com/AuroraOSS/AuroraStore/-/releases)

2. Open Accrescent app, and choose to install AppVerifier.

3. Open AppVerifier app, tap `Verify APK File` button, and choose the `AuroraStore.apk` file you just downloaded.

4. Look for `SUCCESS` at the top of your screen to know the app is authentic.

5. Now you can go to the Files app, tap the `AuroraStore.apk` to install, and finally open the Aurora Store using the `Anonymous` button when logging in.

### Sandboxed Google Play

Google Play Services are not installed by default. You might notice that notifications don't work for some Google Play Apps in GrapheneOS, or maybe some apps fail to run such as Banking apps. This is because some apps depend on Google Play Services, and luckily the developers provide a way to install Google Play Services "Sandboxed", so you can have all the functionality the default Android OS users do.

1. Go to your [Private Space](#private-space), open the app called App Store, and choose to install Google Play Services.

2. Once installed you should have full functionality needed for your Private Space apps that require Google Play Services to function properly.

3. Lock your Private Space when not in use to avoid Google Play Services running in the background.

4. If you need the Private Space to stay unlocked, adjust the Private Space setting to lock only after device restart.

</details>
<br/>

## Web Apps

Don't want to use Aurora Store to download apps from Google Play? Don't want to enable Google Play Services?

1. Try using Web Apps like `https://uber.com` instead of the Uber app to avoid downloading apps wherever possible.

2. If this is an every day carry phone, then try to keep Web Apps in mind for things like reservations, travel, shopping, etc.

3. Always keep in mind that a VPN in an odd country could cause problems when using something like a banking app. Try changing the VPN to a nearby location in these cases.

<br/>

## Completion

If you have mastered this guide then congratulations is in order! You are now an advanced user of GrapheneOS and hopefully feel comfortable using this setup in your day-to-day life.

## TODO
<details><summary>**Contributors - Click to expand TODO ...**</summary>
TODO: Backups, Bitcoin and Monero info, Hardcore/InviZiblePro ?
TODO: Verify apps not in AppVerifier database, explain getting AppVerifier from Accrescent
TODO: IVPN verify
TODO: Android will not allow apps to be updated unless the new APK file uses the same unique developer Java KeyStore*.
TODO: Verify build number or verifier os install app
TODO: Quick add to Obtanium buttons, additional requests for crowdsourced app list
TODO: Add link device support EOL
TODO: Further refine quick deploy and offline guides, screeshots or vid
</details>
