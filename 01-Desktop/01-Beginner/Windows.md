# Windows - Beginner

## Table of Contents
* [1. Intro](#intro)
* [2. Install](#install)
* [3. Initial Setup](#initial-setup)
* [4. Tor Browser](#tor-browser)
* [5. VPN](#vpn)
* [6. WinUtil](#winutil)
* [7. Web Browser](#web-browser)
* [8. Password Manager](#password-manager)
* [9. Continue Your Training](#continue-your-training)

## Ratings
Gaming: High
Enterprise: High
Security: Medium
Privacy: Low
Cryptocurrency: Low
Open Source: No

<br/>

## Intro

- Tune your Windows setup to trim off the bloat, and improve privacy or security where possible.

- Windows isn't the best for privacy and security, but for gaming or enterprise it's widely used.

- The goal is to eventually graduate from Windows to other Operating Systems for more sensetive tasks.

<br/>

## Reinstall

A lot of people already have Windows and just need a fresh start. In that case follow these instructions to wipe your Windows computer to a fresh state.

1. Go to `Settings Menu` > `System` > `Reset This PC`

2. Once you have backed pictures, documents, etc. then choose to remove everything.

## Install

1. If you need to install Windows, go to [Create Windows 11 Installation Media](https://www.microsoft.com/en-us/software-download/windows11) section on the Microsoft downloads page.

2. Plug in a USB stick, run the Media Creation Tool, and create a Windows Install USB stick.

3. Plug USB stick into computer, boot into the BIOS, and choose to boot using the Windows Install USB stick.

<br/>

## Initial Setup

1. Boot up your fresh Windows PC for the first time.

2. Microsoft asks privacy and tracking preferences during setup, disable everything that you can during the initial Windows setup process.

<br/>

## Tor Browser

1. Go to the [Tor Project Download](https://www.torproject.org/download) page and choose to download the browser for Windows.

2. Open Tor Browser, and go to the [IVPN Website](https://www.ivpn.net/en).

<br/>

## VPN

1. Purchase a subscripton from the [IVPN Website](https://www.ivpn.net/en) using Bitcoin or Monero.

2. Download the [IVPN Windows App](https://www.ivpn.net/en/apps-windows) and install it.

3. Open the IVPN App, enter your login code, and be sure to **enable the killswitch**.

<br/>

## WinUtil

Let's use Chris Titus's [Windows Utility](https://christitustech.github.io/winutil) on Github to finish setting up quickly.

This all-in-one Open Source tool is an easy way to streamline the best possible Windows setup. It can be used to streamline installs, debloat with tweaks, troubleshoot with config, and fix Windows updates.

1. To use the tool, the Start Menu and type `Powershell`, then right click the `Powershell` option and select to run as Administrator.

2. Enter the following command:
    ```
    irm christitus.com/win | iex
    ```

3. Run essential tweaks then run OOshutup.

<br/>

## Web Browser

1. Go to the WinUtil App "Install" tab, and look at the "Browsers" section.

2. Choose to install Brave Browser or Thorium AVX2.

3. U-block and Speedy extenstions are suggested.

<br/>

## Password Manager

1. Go to the WinUtil App "Install" tab, and look at the "Utilities" section.

2. Choose to install KeepassXC and use it to record usernames, passwords, and website info.

3. Make sure to **create regular backups** of your KeepassXC database .kdbx file! Avoid using Google or Apple cloud for data backups.

<br/>

## Continue Your Training

1. TODO: Why migrate
2. TODO: Open Source v Closed
3. TODO: Avoid using hwalls on win
