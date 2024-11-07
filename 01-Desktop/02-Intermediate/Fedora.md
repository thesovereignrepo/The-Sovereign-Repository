# Fedora - Intermediate

## Table of Contents
* [1. Intro](#intro)
* [2. Install](#install)
* [3. Initial Setup](#initial-setup)
* [4. VPN](#vpn)
* [5. Web Browser](#web-browser)
* [6. Tor](#tor-daemon)
* [7. Password Manager](#password-manager)
* [8. Continue Your Training](#continue-your-training)

## Ratings
Gaming: Low
Enterprise: High
Security: Medium
Privacy: Medium
Cryptocurrency: Medium
Open Source: Yes

<br/>

## Intro

- Fedora is a Linux Operating System.

- This OS is often considered a good place for newer Linux users to get started.

- Fedora is a good choice for everyday browsing, media, work, and other regular tasks.

- While Fedora is good for ease of use and a flashy interface, it is not recommended for more sensitive use cases.

<br/>

## Install

Fedora has a great step-by-step installation guide for you to follow. Please go to the [Fedora Install Guide](https://docs.fedoraproject.org/en-US/fedora/f36/install-guide/install/Preparing_for_Installation/#_installing_and_running_fedora_media_writer) on the Fedora official website to get started.

<br/>

## Initial Setup

1. First, open the Terminal from the applications menu, then run the following command to make sure your system is up to date.
    ```
    sudo dnf update
    ```

2. Once you have updated Fedora, it is a good time get familiar with initial configuration options. See this [Fedora Initial Setup Guide](https://itsfoss.com/things-to-do-after-installing-fedora) to get started learning what is possible.

3. It is recommended to follow the [VPN Section](#vpn) below and enable your VPN before you continue with online activity. Remember, a VPN relies on trust in the VPN service provider, and should **never** be considered a replacement for the Tor Browser which has stronger privacy guarantees.

<br/>

## VPN

Open Terminal from the applications menu, then run the following commands to install the IVPN app by using IVPN's repository.

1. Add the IVPN repository.
    ```
    sudo dnf config-manager addrepo --from-repofile=https://repo.ivpn.net/stable/fedora/generic/ivpn.repo
    ```

2. To install IVPN software.
    ```
    sudo dnf install ivpn-ui
    ```

3. Open IVPN from the applications menu, log in, and enable the killswitch.

<br/>

## Web Browser

Open Terminal from the applications menu, and run the following commands to install Brave Browser using Brave's repository.

1. Install dnf-plugins-core package.
    ```
    sudo dnf install dnf-plugins-core
    ```

2. Add the Brave Browser repository.
    ```
    dnf config-manager addrepo --from-repofile=https://brave-browser-rpm-release.s3.brave.com/brave-browser.repo
    ```

3. Import Brave's PGP key.
    ```
    sudo rpm --import https://brave-browser-rpm-release.s3.brave.com/brave-core.asc
    ```

4. Install the Brave Browser.
    ```
    sudo dnf install brave-browser
    ```

5. Open Brave Browser and get started browsing.
<br/>

## Tor Daemon

Open Terminal from the applications menu, and run the following commands to install Tor Daemon.

1. Install the Tor Daemon.
    ```
    sudo dnf install tor
    ```

2. Once installed, start the Tor Daemon.
    ```
    sudo systemctl start tor
    ```

3. Once installed, check version and status. Press Q to quit to return to Terminal.
    ```
    tor --version && sudo systemctl status tor
    ```

## Tor Browser

Open Terminal from the applications menu, and run the following command to install Tor Browser.

1. Install the Tor Browser.
    ```
    sudo dnf install torbrowser-launcher
    ```

2. Now launch the Tor Browser via the applications menu and get started browsing.

<br/>

## Password Manager

Open Terminal from the applications menu, and run the following command to install KeePassXC.

1. Install KeePassXC.
    ```
    sudo apt install keepassxc
    ```

2. Now launch KeePassXC via the applications menus to get started with 2FA, username & password management, and so much more! Don't forget to backup your database file in a safe place and make multiple backups.

<br/>

## Continue Your Training

Continue to the [Advanced Section](https://github.com/thesovereignrepo/The-Sovereign-Repository/tree/master/01-Desktop/03-Advanced) to learn about a more security and privacy focused operating system.
