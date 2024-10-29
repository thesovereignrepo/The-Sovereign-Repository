# GrapheneOS Offline

## Table of Contents
* [1. Intro](#intro)
* [2. Installing](#installing)
* [3. Apps](#apps)
* [4. Bitcoin](#bitcoin)
* [5. Continue](#continue-your-training)

<br/>

## Intro

- Follow these instructions to setup an **offline** GrapheneOS phone.

- Think of this deployment as geared towards offline Bitcoin (cold storage), or perhaps storing some sensitive data offline.

- Skip this guide if it's not a useful exercise, and continue to the [Advanced GrapheneOS Guide]().

- A setup like this can replace a bitcoin hardware wallet. These concepts will really get your gears turning!

- This guide does not support wifi, mobile data, or any kind of internet connection.

<details><summary>**First time? Click to expand ...**</summary>

### What is this?

This page simplifies the task of getting started with an offline GrapheneOS phone. Once familiar, you can use this guide you can deploy a basic offline phone in about 30 minutes and start using it as a bitcoin wallet or sensitive data storage device.

The purpose of never allowing networking (internet) on this device is simple, it drastically reduces the chance this device can be compromised. One could even argue that with the Titan M2 secure element and large bug bounties from Google's Project Zero, a GrapheneOS device with networking disabled is as secure or perhaps more secure than a bitcoin hardware wallet.

GrapheneOS is the only option we can recommend at this point for a phone Operating System. It's an Open Source project that puts privacy and security first. The OS only runs on Google Pixel devices, so that's the phone you'll need to use.

### Videos

GrapheneOS Install  -  [Clearnet Link](https://www.youtube.com/watch?v=CD4Jl6ZYEbw)

</details>
<br/>

## Installing

Grab your Google Pixel phone and let's get started with the de-Googling.

1. Make sure the default Android OS on the Pixel has the latest system updates.

2. Go to `Settings` > `About` and repeatedly tap the "Build Number" menu entry until developer mode is enabled.

3. Next, go to `Settings` > `System` > `Developer` and toggle ON the `OEM unlocking` setting and `USB debugging` setting. Note for Pixel 6a users, the unlocking will not be available with the default OS from the factory. You need to update and factory reset the device to fix it.

4. Reboot the phone while pressing the volume down button, and continue to hold it until the phone boots into the bootloader interface. Then you can release the volume down button once you see the interface.

5. Now you can plug the phone into your desktop computer (or another Pixel phone) and proceed with the [GrapheneOS Web Installer](https://grapheneos.org/install/web#unlocking-the-bootloader).

6. Once you boot up GrapheneOS for the first time be sure to **NOT ALLOW** networking. This will prevent any internet access.

<br/>

## Apps

Without internet you obviously cannot download apps, instead you need to become familiar with the concept of Sideloading apps. Sideloading is the practice of installing software on a device without using the approved app store.

Let's try sideloading a bitcoin wallet app in the next section.

<br/>

## Bitcoin

### App Verification

First you will need to verify this bitcoin wallet app is authentic.

1. On your desktop PC using Tor Browser, go to the [Ashigaru Downloads]() page, and copy the "SHA-256 Hash of the APK file".

2. Using Tor Browser, navigate to the [Keybase Online Verify Tool](http://keybase5wmilwokqirssclfnsqrjdsi7jdir5wy7y7iu3tanwmtp6oid.onion/verify), paste the hash you copied in step 1.

3. Click verify then look for **✔ Signed by ashigarudev** to indicate success, and do not continue if the result is unsuccessful.

4. Return to the [Ashigaru Downloads]() and click the `Download Android APK File` button.

5. Using Tor Browser, go to [Hash-file Online](https://hash-file.online), choose browse, and select the `Ashigaru.apk` file you just downloaded in step 4.

6. Choose the `SHA-256 | 256-bit` option and press the `Launch hash process` button.

7. Compare the hash output to the hash listed on the [Ashigaru Downloads]() page in step 1. If the hashes match then you know the app is authentic and not tampered with, and if they do not match then stop immediately and seek help from a community member.

### Sideload Wallet App

Now that you have verified the APK File you can finally Sideload the app on your phone.

1. Plug a USB stick into your computer and move the `Ashigaru.apk` to it. Eject the USB stick from your computer.

2. Your phone came with a USB adapter in the box, plug the USB adapter into your phone, and then plug in the USB stick.

3. Open the Files app on your phone, go to the USB stick, tap the `Ashigaru.apk`, and select allow install.

4. Now you can launch the Ashigaru app.

5. TODO: See the [Offline Bitcoin Section]() to learn how bitcoin can be spent and stored safely without using the internet.

<br/>

## Continue Your Training

Ready to use GrapheneOS every day while on the go? Curious about how to safely manage apps from Google Play app store?

1. Continue to the [Advanced GrapheneOS Guide]() when you are ready to use GrapeheneOS in your daily life.

2. Keep in mind, you can Factory Reset at any time for a fresh start, and continue to the next guide.

3. Keep in mind, you could have multiple phones if needed. A phone for offline usage and a phone for for every day usage.
