# Ubuntu - Intermediate

## Table of Contents
* [1. Intro](#intro)
* [2. Install](#install)
* [3. Initial Setup](#initial-setup)
* [4. VPN](#vpn)
* [5. Web Browser](#web-browser)
* [6. Tor Browser](#tor-browser)
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

- Ubuntu is a Linux Operating System which is based on Debian.

- This OS is often considered a good place for newer Linux users to get started.

- Ubuntu is a good choice for everyday browsing, media, work, and other regular tasks.

- While Ubuntu is good for ease of use and a flashy interface, it is not recommended for more sensitive use cases.

<br/>

## Install

Ubtuntu has a great step-by-step installation guide for you to follow. Please go to the [Ubuntu Install Guide](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview) on the Ubuntu official website to get started.

<br/>

## Initial Setup

1. First, open the Terminal from the applications menu, then run the following command to make sure your system is up to date.
    ```
    sudo apt update && sudo apt upgrade
    ```

2. Once you have updated Ubuntu, it is a good time get familiar with initial configuration options. See this [Ubuntu Initial Setup Guide](https://itsfoss.com/things-to-do-after-installing-ubuntu-22-04) to get started learning what is possible.

3. It is recommended to follow the [VPN Section](#vpn) below and enable your VPN before you continue with online activity. Remember, a VPN relies on trust in the VPN service provider, and should **never** be considered a replacement for the Tor Browser which has stronger privacy guarantees.

<br/>

## VPN

Open Terminal from the applications menu, then run the following commands to install the IVPN app by using IVPN's repository.

1. Make sure your have curl and apt-transport-https installed.
    ```
    sudo apt install curl apt-transport-https
    ```

2. Download IVPN's PGP key and save using `--dearmor` option.
    ```
    curl -fsSL https://repo.ivpn.net/stable/ubuntu/generic.gpg | gpg --dearmor > ~/ivpn-archive-keyring.gpg
    ```

3. Move to appropriate directory.
    ```
    sudo mv ~/ivpn-archive-keyring.gpg /usr/share/keyrings/ivpn-archive-keyring.gpg
    ```

4. Set appropriate permissions for PGP key.
    ```
    sudo chown root:root /usr/share/keyrings/ivpn-archive-keyring.gpg && sudo chmod 644 /usr/share/keyrings/ivpn-archive-keyring.gpg
    ```

5. Add the IVPN repository to sources list.
    ```
    curl -fsSL https://repo.ivpn.net/stable/ubuntu/generic.list | sudo tee /etc/apt/sources.list.d/ivpn.list
    ```

6. Set appropriate permissions for repository.
    ```
    sudo chown root:root /etc/apt/sources.list.d/ivpn.list && sudo chmod 644 /etc/apt/sources.list.d/ivpn.list
    ```

7. Update repository info and install the IVPN software.
    ```
    sudo apt update && sudo apt install ivpn-ui
    ```

8. Open IVPN from the applications menu, log in, and enable the killswitch.

<br/>

## Web Browser

Open Terminal from the applications menu, and run the following commands to install Brave Browser using Brave's repository.

1. Download Braves's PGP key.
    ```
    sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg
    ```

2. Copy repository URL and keyring info to sources list.
    ```
    echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list
    ```

3. Update repository info and install Brave Browser.
    ```
    sudo apt update && sudo apt install brave-browser
    ```

<br/>

## Tor

Open Terminal from the applications menu, and run the following commands to install Tor Daemon using the Tor Project repository.

1. Add Tor repository and keyring info to sources list.
    ```
    sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/deb.torproject.org-keyring.gpg] https://deb.torproject.org/torproject.org $(lsb_release -sc) main" >> /etc/apt/sources.list.d/tor-project.list'
    ```

**NOTE:** For Linux Mint and other Ubuntu based systems, replace `$(lsb_release -sc)` in the command with the latest [Ubuntu code-name](https://wiki.ubuntu.com/Releases) (e.g, noble, jammy) that your system is based on. The keyring does have to be manually updated when rotated.

2. Update repository info and install the Tor Daemon. 
    ```
    sudo apt update && sudo apt install tor
    ```

3. Once installed check version and status.
    ```
    tor --version && sudo systemctl status tor
    ```
<br/>

## Tor Browser

Open Terminal from the applications menu, and run the following command to install Tor Browser using the Tor Project repository.

1. Open terminal and run command.
    ```
    sudo apt install torbrowser-launcher
    ```

2. Now launch the Tor Browser via the applications menu and get started browsing.

<br/>

## Password Manager

Open Terminal from the applications menu, and run the following command to install KeePassXC.

1. update
    ```
    sudo apt update && sudo apt upgrade
    ```

2. install
    ```
    sudo apt install keepassxc
    ```

3. Now launch KeePassXC via the applications menus to get started with 2FA, username & password management, and so much more! Don't forget to backup your database file in a safe place and make multiple backups.

<br/>

## Continue Your Training

Continue to the [Advanced Section](https://github.com/thesovereignrepo/The-Sovereign-Repository/tree/master/01-Desktop/03-Advanced) to learn about a more security and privacy focused operating system.
