# Coming soon

Useful links:

    https://grapheneos.org - GrapheneOS
    https://grapheneos.org/features - GrapheneOS Features
    https://grapheneos.org/usage - GrapheneOS Usage
    https://grapheneos.org/faq - GrapheneOS FAQ

Auditor App

    https://attestation.app/ - Auditor App
    https://attestation.app/tutorial#scheduled-remote-verification - Remote attestation setup

GrapheneOS Camera

    https://grapheneos.org/usage#grapheneos-camera-app GrapheneOS Camera documentation
    https://github.com/GrapheneOS/Camera - GrapheneOS Camera GitHub

GrapheneOS PDF Viewer

    https://grapheneos.org/features#grapheneos-pdf-viewer - GrapheneOS PDF Viewer documentation
    https://github.com/GrapheneOS/PdfViewer - GrapheneOS PDF Viewer GitHub

GrapheneOS Vanadium

    https://grapheneos.org/features#vanadium - GrapheneOS Vanadium documentation
    https://github.com/GrapheneOS/Vanadium - GrapheneOS Vanadium GitHub

Settings

    https://grapheneos.org/features#auto-reboot - Auto reboot
    https://grapheneos.org/features#attack-surface-reduction - Wi-Fi/Bluetooth timeout
    https://grapheneos.org/features#pin-scrambling - Pin Scrambling


Todo:
explain how you can use webapps for uber, shopping, etc.
android-setup-tips

Apps:
Protonmail .apk: https://protonapps.com/protonmail-android
Nekogram
Shelter
Open Camera
New Pipe
Dicio
Hashdroid
OpenKeychain
KeePassDX
Tor Browser
Wireguard

## What is this?

Are you currently using Stock Android OS or an iPhone and looking to regain your privacy? Here you'll find everything you need to get started on your journey.

I put this page together in an attempt to make the task of buying, configuring, and using a private/secure alternate phone OS as easy as possible. If you're like some more info on the "why" check out this clip 📺.

## Choosing an OS

GrapheneOS is the only option I can recommend at this point for a phone Operating System. It's an Open Source project that puts privacy and security first. The OS only runs on Google Pixel devices, so that's the phone you'll need to use. Now that we know what OS we'll be installing:

Here's my most recent review video of GrapheneOS - https://youtu.be/hbs7EPSaauI 

I also took GrapheneOS on a road trip to test it out - https://youtu.be/rp--qY9eSYI 

## Buying a phone

If you don't already own a Google Pixel that's supported by GrapheneOS, you'll need to purchase one. Before buying your device, you need to confirm that OEM Unlocking is supported. I cover that in this clip.


Amazon - recommended if buying new
Swappa - recommended if buying used
Gazelle
eBay
Walk into a Best Buy with cash and purchase one.

## Installing GrapheneOS

Now that you have a device, it's time to install GrapheneOS. If your device isn't listed, just choose the most recent video.

    Install GrapheneOS on Pixel 7 - ADD VIDEO HERE

If you don't see your device listed in one of the videos, choose the newest video. The installation process is nearly identical across devices when using the web installer.

Once you have GrapheneOS installed, let's start with an overview of the stock apps installed 📺, you only need to watch the first 1min12s of that video.

## Cell service

If you have a physical SIM card, you can remove it from your old device and put it in your new one. If you have an eSIM, there's a few more steps involved in the eSIM setup.

## App Stores

Before deciding which app stores to use, check out this video  for an overview of what's available and some basics.

### Aurora Store

GrapheneOS doesn't come bundled with any app stores pre-installed, so we need to install them ourselves. The first app store I would suggest you install is called Aurora Store. Aurora Store allows you to download apps from Google Play store without having to install Google Play Store. Go to https://auroraoss.com in your mobile browser and download "Aurora Store x.x.x (Stable).

Once you have it installed you can watch this video on how to set it up.

### F-Droid

A popular repository for Open Source Software (OSS) is F-Droid. F-Droid has some security concerns that I detail in this video.

To simplify it, here are the 3 options:

    F-Droid - Video Link 📺 - OK
    Droid-ify/Neo Store - A little better than OK
    Using Obtanium to manually track apps - Video Link 📺 - Best

### Obtainium

Get Android app updates directly from the source. Obtainium allows you to install and update apps directly from their releases pages, and receive notifications when new releases are made available. This is a by far the best option available to download and update apps if you are willing to learn some new tricks.

Todo: Add obtainium apps list for others to use

## Sandboxed GPS

Google Play Services (GPS) are not installed by default. You might notice that notifications don't work for some Apps in GrapheneOS or maybe some apps fail to run (such as banking apps). The reason for this is that some apps depend on Google Play Service, but GrapheneOS doesn't have those. Luckily the developers provide a way to install Google Play Service Sandboxed, so you can have all the functionality available on a device with stock Android OS. GrapheneOS.org has a great write up on the details of the implementation that I would suggest reading.

In this video I show how to install Sandboxed Google Play services and some different configuration options available.

## Profiles

Work Profiles vs User Profiles. In the Sandboxed Googlge Play Services video, I mentioned User Profiles. If you're interested in learning some more about those, check out this video 📺.

## Secure messaging

Text messages (SMS) are not secure or private. There are some great options out there which I cover in this video 📺.

## Contact/Calendar storage

Most of us use our phones for communicate with people and to store our calendars. If you're looking for a method that I would recommend, I detail those in the following videos.

    Free Secure Cloud Contact Storage - ADD URLS
    Free Secure Cloud Calendar Storage 

## Backup/Restore

Phones get lost/stolen everyday. Protect your data by taking a backup in case this happens to you.

    How to backup GrapheneOS - ADD URLS
    How to restore GrapheneOS from a backup

## Useful videos

    Apps I use on my personal phone - ADD VIDEO URLS
    GrapheneOS new features - Profile notifications and Storage Scopes 
    How your phones' wallpaper can be used to track you 
    Sensors and Network permission toggle 
    GrapheneOS Review - Android 13 
    Progressive Web Apps 
    GrapheneOS new features - Sensors, Network, Exploit Protection