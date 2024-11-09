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

• Tune your Windows setup to trim off the bloat, and improve privacy or security where possible.

• Windows isn't the best for privacy and security, but for gaming or enterprise it's widely used.

• The goal is to eventually graduate from Windows to other Operating Systems for more sensetive tasks.

<br/>

## Reinstall

A lot of people already have Windows and just need a fresh start. In that case follow these instructions to wipe your Windows computer to a fresh state.

1. Go to `Settings Menu` > `System` > `Reset This PC`

2. Once you have backup pictures, documents, etc. then choose to `Reset This PC` and remove everything.

## Install

1. If you need to install Windows, go to [Create Windows 11 Installation Media](https://www.microsoft.com/en-us/software-download/windows11) section on the Microsoft downloads page.

2. Plug in a USB stick, run the Media Creation Tool, and create a Windows Install USB stick.

3. Plug USB stick into computer, boot into the BIOS, and choose to boot using the Windows Install USB stick.

4. Choose to install the Windows Operating System.

<br/>

## Initial Setup

1. Boot up your fresh Windows PC for the first time.

2. Microsoft asks privacy and tracking preferences during setup, disable everything that you can during the initial Windows setup process.

<br/>

## Tor Browser

Open your Web Browser from the applications menu, and follow the instructions to install Tor Browser.

1. Go to the [Tor Project Download](https://www.torproject.org/download) page and choose to download the browser for Windows.

2. Now launch the Tor Browser via the applications menu and get started with private browsing. Always use Tor for sensitive tasks, and VPN can be used for regular browsing.

<br/>

## VPN

Open Tor Browser from the applications menu, and follow the instructions to install IVPN.

1. Using the Tor Browser, purchase a subscripton from the [IVPN Website](https://www.ivpn.net/en) using Bitcoin or Monero.

2. Download the [IVPN Windows App](https://www.ivpn.net/en/apps-windows) and install it.

3. Open the IVPN from the applications menu, enter your login code, and be sure to **enable the killswitch**. Be aware with the killswitch enabled your internet will not work if disconnected from the VPN.

<br/>

## WinUtil

Use the Chris Titus's [Windows Utility](https://christitustech.github.io/winutil) on Github to finish setting up quickly. This all-in-one Open Source tool is an easy way to streamline the best possible Windows setup.

1. To use the tool, the Start Menu and type Powershell, then right click the Powershell option, and select to run as Administrator.

2. Enter the following command:
    ```
    irm christitus.com/win | iex
    ```

3. Run essential tweaks then run OOshutup.

<br/>

## Web Browser

Use the Chris Titus's [Windows Utility](https://christitustech.github.io/winutil) to download a Web Browser.

1. Go to the WinUtil App "Install" tab, and look at the "Browsers" section.

2. Choose to install Brave Browser or Thorium AVX2.

3. U-block and Speedy extenstions are suggested.

4. It is recommended to follow the [VPN Section](#vpn) and enable your VPN before you continue with a regular web browser. Remember, a VPN relies on trust in the VPN service provider, and should **never** be considered a replacement for the Tor Browser which has stronger privacy guarantees.

<br/>

## Password Manager

Use the Chris Titus's [Windows Utility](https://christitustech.github.io/winutil) to download a Password Manager.

1. Go to the WinUtil App "Install" tab, and look at the "Utilities" section.

2. Choose to install KeePassXC.

3. Now launch KeePassXC via the applications menus to get started with 2FA, username & password management, and so much more! Make sure to **create regular backups** of your KeepassXC database .kdbx file! Avoid using Google or Apple cloud for data backups.

<br/>

## Continue Your Training

Continue to the [Intermediate Section](https://github.com/thesovereignrepo/The-Sovereign-Repository/tree/master/01-Desktop/02-Intermediate) to get started with Linux.

See something out of date, a broken link, or have a better idea? Please go [Open An Issue](https://github.com/thesovereignrepo/The-Sovereign-Repository/issues) on our Github and let us know!
