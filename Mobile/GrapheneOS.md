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

<summary>**>> Click to expand**</summary>

### What is this?

Are you currently using default Android OS or an iPhone and looking to regain your privacy? Here you'll find everything you need to get started on your journey.

This page is in an attempt to make the task of buying, configuring, and using a private/secure alternate phone OS as easy as possible. It is not too difficult if you are willing to put a little bit of time and effort in.

Graphene OS is the only option we can recommend at this point for a phone Operating System. It's an Open Source project that puts privacy and security first. The OS only runs on Google Pixel devices, so that's the phone you'll need to use.

### Buying a phone

If you don't already own a Google Pixel you'll need to purchase one. Before buying your device confirm that it is fully unlocked or you will not be able to install Graphene OS.

Some ideas for purchase are Amazon, eBay, or just walk into a Best Buy with cash and purchase one.

### Cell service

You do not need to purchase a SIM card or eSIM from a company like AT&T or Tmobile unless you are trying to make this an every day carry.

Many people get comfortable enough with Graphene OS to use it every day, and in that case you will probably need data services.

When considering your threat model, see this information - [Clearnet Link](https://grapheneos.org/faq#cellular-tracking)


[Tor Link]() | [Clearnet Link]()
[Tor Link]() | [Clearnet Link]()

###  Graphene OS Resources

Features - [Clearnet Link](https://grapheneos.org/features) 
Usage - [Clearnet Link](https://grapheneos.org/usage)
FAQ - [Clearnet Link](https://grapheneos.org/faq)
Camera - [Clearnet Link](https://grapheneos.org/usage#grapheneos-camera-app)
PDF Viewer - [Clearnet Link](https://grapheneos.org/features#grapheneos-pdf-viewer)
Vanadium - [Clearnet Link](https://grapheneos.org/features#vanadium)
Auto reboot - [Clearnet Link](https://grapheneos.org/features#auto-reboot)
Wi-Fi/Bluetooth timeout - [Clearnet Link](https://grapheneos.org/features#attack-surface-reduction)
Pin Scrambling - [Clearnet Link](https://grapheneos.org/features#pin-scrambling)

</details>

<br/>

## Installing

1. Make sure the default Android OS on the pixel is has the latest system updates.

2. Enable the developer options menu by going to Settings > About and repeatedly pressing the Build Number menu entry until developer mode is enabled.

3. Next, go to Settings > System > Developer options and toggle on the OEM unlocking setting and USB debugging setting. Note for the Pixel 6a, OEM unlocking won't work with the version of the stock OS from the factory. You need to update it and factory reset the device to fix OEM unlocking.

4. Now you can plug the phone into your PC and proceed with the web installer. [Clearnet Link](https://grapheneos.org/install/web)

5. For visual learners, follow along with this video. [Clearnet Link](https://www.youtube.com/watch?v=CD4Jl6ZYEbw)

## VPN

TODO: Mullvad, IVPN, Proton

## Apps

TODO: Contact or storage scopes

TODO: Secure messaging - Text messages (SMS) are not secure or private. 

### Obtainium

Get Android app updates directly from the source. Obtainium allows you to install and update apps directly from their releases pages, and receive notifications when new releases are made available. This is a by far the best option available to download and update apps if you are willing to learn some new tricks.

TODO: Add obtainium apps list for others to use

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
Auditor App

https://attestation.app/ - Auditor App
https://attestation.app/tutorial#scheduled-remote-verification - Remote attestation setup

### Aurora Store

GrapheneOS doesn't come bundled with any app stores pre-installed, so we need to install them ourselves. The first app store I would suggest you install is called Aurora Store. Aurora Store allows you to download apps from Google Play store without having to install Google Play Store. Go to https://auroraoss.com in your mobile browser and download "Aurora Store x.x.x (Stable).

Once you have it installed you can watch this video on how to set it up.

### F-Droid

TODO: A popular repository for Open Source Software (FOSS) is F-Droid. 

## Profiles

TODO: Work Profiles vs User Profiles. 

Protip Put any Aurora Store apps on work profile.

## Sandboxed Google Play

Google Play Services (GPS) are not installed by default. You might notice that notifications don't work for some Apps in GrapheneOS or maybe some apps fail to run (such as banking apps). The reason for this is that some apps depend on Google Play Service, but GrapheneOS doesn't have those. Luckily the developers provide a way to install Google Play Service Sandboxed, so you can have all the functionality available on a device with stock Android OS. GrapheneOS.org has a great write up on the details of the implementation that I would suggest reading.

## Web Apps

TODO: explain how you can use webapps for reservations, travel, uber, shopping, etc.

## Wallet

TODO: Want to learn more about your options for wallet? Link wallet section

## Backups

TODO:
Contact/Calendar storage

Most of us use our phones for communicate with people and to store our calendars. If you're looking for a method that I would recommend, I detail those in the following videos.

    Free Secure Cloud Contact Storage - ADD URLS
    Free Secure Cloud Calendar Storage

Phones get lost/stolen everyday. Protect your data by taking a backup in case this happens to you.

    How to backup GrapheneOS - ADD URLS
    How to restore GrapheneOS from a backup

Seedvault

"...the project has been taken over by another group of people not sharing our goals or approach. For now, this is the best available option, so we're including it to give people encrypted backup support. We've made several security fixes to work around upstream issues with the project."

Most of us use our phones for communicate with people and to store our calendars. If you're looking for a method that I would recommend, I detail those in the following videos.

    Free Secure Cloud Contact Storage - ADD URLS
    Free Secure Cloud Calendar Storage

## Videos

Here's a review video of GrapheneOS - https://youtu.be/hbs7EPSaauI
GrapheneOS on a road trip test - https://youtu.be/rp--qY9eSYI
