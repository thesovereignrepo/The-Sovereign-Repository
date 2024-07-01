# Qubes OS

## Table of Contents
* [1. Intro](#intro)
* [2. Setting Up](#setting-up)
* [3. Check for Updates](#check-for-updates)
* [4. USB Qube](#usb-qube)
* [5. Disposables](#disposables)
* [6. Customize Appearance](#customize-appearance)
* [7. Password & Key Management](#password-and-key-management)
* [8. VPNs](#vpn)
* [9. Whonix](#whonix)
* [10. VMs Resource Usage](#vm-resource-usage)

<br/>

## Intro

- This is a basic overview guide for Qubes users to setup or recover from backup. I have tried to make this guide short and easy to skim through.

- In this guide I assume the reader is somewhat familiar with the command line & PGP, knows basic things about Qubes OS such as the difference between a Template VM & Application VM, and understands the basics of some privacy tools like Tor & VPNs.

- Stay focused on a single task or section at a time, think about what is relevant to learn, and avoid wasting your time.

- Please expand the additional resources below if this is your first time.

<br/>

<details>

<summary>**>> Click here to expand additional resources**</summary>

### Qubes Introduction Resources

Official Documentation - [Tor Link](http://qubesosfasa4zl44o4tws22di6kepyzfeqv3tg4e3ztknltfxqrymdad.onion/doc/) | [Clearnet Link](https://www.qubes-os.org/doc/)

Introduction  - [Tor Link](http://qubesosfasa4zl44o4tws22di6kepyzfeqv3tg4e3ztknltfxqrymdad.onion/intro/) | [Clearnet Link](https://www.qubes-os.org/intro/)

Get Started Video - [Tor Link](http://iv.daturab6drmkhyeia4ch5gvfc2f3wgo6bhjrv3pz6n7kxmvoznlkq4yd.onion/watch?v=Aghj8MyDF4I) | [Clearnet Alt YT Front-end Link](https://iv.datura.network/watch?v=Aghj8MyDF4I) | [Clearnet YT Link](https://www.youtube.com/watch?v=Aghj8MyDF4I)

Video Tutorial Playlist [Tor Link](http://iv.daturab6drmkhyeia4ch5gvfc2f3wgo6bhjrv3pz6n7kxmvoznlkq4yd.onion/playlist?list=PLjwSYc73nX6aHcpqub-6lzJbL0vhLleTB) | [Clearnet Alt YT Front-end Link](https://iv.datura.network/playlist?list=PLjwSYc73nX6aHcpqub-6lzJbL0vhLleTB) | [Clearnet YT Link](https://www.youtube.com/playlist?list=PLjwSYc73nX6aHcpqub-6lzJbL0vhLleTB)

<br/>

### Open Source Firmware/BIOS

Open Source Firmware/BIOS

I suggest the PC firmware ("BIOS") consists of the Coreboot distribution known as Dasharo, which is published as open source. This allows independent security checks of the firmware and prevents undetected backdoors. You can also purchase a Dasharo Entry Subscription which guarantees continuous firmware development and fast firmware updates. Please note I am just a supporter and not affiliated with this project in any way.

Dasharo is available in two versions:
The first version of Dasharo uses HEADS with Measured Boot to enable tamper detection of the TPM, the installed firmware, and the operating system. This requires a Nitrokey USB key that serves as a trust anchor. [Clearnet Link](https://www.nitrokey.com)

The second version of Dasharo is just the TianoCore UEFI without Measured Boot. It is a lean, fast, and easy-to-use UEFI. It can even be used with all PC operating systems including Windows.

It is optional to change the Firmware/BIOS for your PC, but worth it in my humble opinion!

<br/>

### Deactivatable Intel Management Engine

The Intel Management Engine (ME) is a type of separate computer within all modern Intel processors (CPU). The ME acts as a master controller for your CPU and has extensive access to your computer (system memory, display, keyboard, network). Intel controls the code of the ME and severe vulnerabilities have already been found in the ME that allow local and remote attacks. Therefore, ME can be considered a backdoor should be disabled.

The Dasharo coreboot-based Firmware/BIOS (above) offers ‘Intel ME disabling’. This is done via the HAP bit disabling method which is the enhanced way to disable Intel ME. Using this approach to disable the ME means that although it’s not completely eliminated from the computer, it is turned off in a way that’s at least good enough for computers that the NSA uses. [Clearnet Link](https://www.csoonline.com/article/562761/researchers-say-now-you-too-can-disable-intel-me-backdoor-thanks-to-the-nsa.html)

If you just want to buy an off the shelf product, consider that ME can be disabled in a NitroPC. [Clearnet Link](https://www.nitrokey.com)

It is optional to disable the ME, but worth it in my humble opinion!

<br/>

### Additional Privacy Resources

Privacy Tools - [Clearnet Link](https://www.privacytools.io)

Prism Break - [Clearnet Link](https://prism-break.org/en/)

Degoogle - [Clearnet Link](https://github.com/tycrek/degoogle)

**Tip:** Check these resources for more ideas after setting up Qubes OS.

</details>

<br/>

## Setting Up

1. Download and install Qubes OS. [Tor Link](http://qubesosfasa4zl44o4tws22di6kepyzfeqv3tg4e3ztknltfxqrymdad.onion) | [Clearnet Link](https://www.qubes-os.org)

2. During OS install leave all options default and enable updates over Tor if you prefer. Select desired language/passwords/disk encryption(LUKS).

3. System may reboot a few times, do not remove usb while rebooting. Log in to your newly created user once finished.

4. (Optional) Setup MAC Address spoofing if needed. [Clearnet Link](https://forum.qubes-os.org/t/anonymizing-your-mac-address/19072) 

5. (Optional) In the right corner of screen (toolbar), right-click the battery icon, and click Settings to open the power manager settings. Go to Display tab and disable power management.

6. (Optional) Screensaver will lock the screen every 10 minutes which may be desired. If you wish to disable go to top left corner menu on desktop, select system tools, and select Screensaver. Click the Mode (dropdown) menu and choose disable.

**Tip:** MAC spoofing is only necessary if traveling with your laptop or PC. It is not required for home PCs that do not change locations.

<br/>

## Check For Updates

First, update your dom0 and Template VMs so you are up to date with the latest releases. Keep up with the latest updates and annoucements using the links below.

<br/>

Template Updates, Annoucements, and more:

Qubes Updates - [Tor Link](http://qubesosfasa4zl44o4tws22di6kepyzfeqv3tg4e3ztknltfxqrymdad.onion/doc/how-to-update/) | [Clearnet Link](https://www.qubes-os.org/doc/how-to-update/)

Whonix Updates - [Tor Link](http://w5j6stm77zs6652pgsij4awcjeel3eco7kvipheu6mtr623eyyehj4yd.onion/wiki/Operating_System_Software_and_Updates#upgrade-nonroot) | [Clearnet Link](https.onion/wiki/Operating_System_Software_and_Updates#upgrade-nonroot)

Announcements - [Tor Link](http://qubesosfasa4zl44o4tws22di6kepyzfeqv3tg4e3ztknltfxqrymdad.onion/news/categories/#announcements) | [Clearnet Link](https://www.qubes-os.org/news/categories/#announcements)

<br/>

**Tip:** To update Whonix templates from command line use the "upgrade-nonroot" method in dom0 terminal. The following are some example commands.

    ```
    qvm-run --pass-io -u user whonix-gateway-17 "upgrade-nonroot"
    qvm-run --pass-io -u user whonix-workstation-17 "upgrade-nonroot"
    ```

**Tip:** The following command will help remove an old template VM that is installed by package manager run this command in dom0 terminal. For example, running the following command in dom0 terminal will allow you to remove an old fedora-38 template VM.

    ```
    qvm-prefs fedora-38 installed_by_rpm false
    ```

<br/>

## USB Qube

If you want to use USB devices, take some time to learn about the USB qube named sys-usb and be aware of its function.

How To Use USB Devices - [Tor Link](http://qubesosfasa4zl44o4tws22di6kepyzfeqv3tg4e3ztknltfxqrymdad.onion/doc/how-to-use-usb-devices/) | [Clearnet Link](https://www.qubes-os.org/doc/how-to-use-usb-devices/)

USB Qube - [Tor Link](http://qubesosfasa4zl44o4tws22di6kepyzfeqv3tg4e3ztknltfxqrymdad.onion/doc/usb-qubes/) | [Clearnet Link](https://www.qubes-os.org/doc/usb-qubes/)

<br/>

**Tip:** When updating your sys-usb qube to use a new template VM, the following command will help you not lose USB peripheral access by properly restarting it. For example, running this command in dom0 terminal to switch fedora-39 as the template VM:

    ```
qvm-shutdown --wait sys-usb; qvm-prefs sys-usb template fedora-39; qvm-start sys-usb
    ```

<br/>

## Disposables

Disposable VMs are a powerful feature of Qubes OS, please take a few minutes to further understand how you can use them. A Disposable VM can be based on any App VM.

How To Use Disposables - [Tor Link](http://qubesosfasa4zl44o4tws22di6kepyzfeqv3tg4e3ztknltfxqrymdad.onion/doc/how-to-use-disposables/) | [Clearnet Link](https://www.qubes-os.org/doc/how-to-use-disposables/) 

Customizing Disposables - [Tor Link](http://qubesosfasa4zl44o4tws22di6kepyzfeqv3tg4e3ztknltfxqrymdad.onion/doc/disposable-customization/) | [Clearnet Link](https://www.qubes-os.org/doc/disposablevm-customization/)

<br/>

## Customize Appearance

Get Qubes OS cleaned up and looking nice.

<details>

<summary>**>> Click here to expand customization options**</summary>

### Darkmode

Qubes OS Darkmode (see section for XFCE). [Clearnet Link](https://forum.qubes-os.org/t/dark-theme-in-dom0/18997)

Go to settings -> appearance -> choose Adwaita-dark. You can also got to the fonts tab here and customize font/size.

Go back to settings and click Window Manager, and set any options that you prefer.

<br/>

### Move System Panel

Some do not want the system panel on the top of their screen. Right click it and go to panel -> panel preferences. Unlock the panel, then use the button on the far left side (left of blue Q) to drag and move. Change any other settings that you prefer.

Right click the workspaces on the panel (left of clock). Go to workspace settings and adjust to your preferences. 

<br/>

### Install redshift in dom0 

If you want to eliminate the bright blue light coming from your screen, try out redshift so your eyeballs can relax.

Open the main menu by clicking the Q in the Corner. Click the Cogwheel icon, go to Other, and finally select the XFCE Terminal. This is the dom0 AKA domain zero terminal.

Install:
    ```
    sudo qubes-dom0-update redshift
    ```

Try out some redshift commands:
    ```
    sudo redshift -O 4000
    sudo redshift -x
    ```

</details>

<br/>

## Password & Key Management

KeePassXC is a great open source password manager. It is already installed in your Valut VM. Simply open the Vault Qube's settings, go to the Applications tab, and add KeepassXC to the apps menu.

Always airgap the virtual machine you are using for password management. For this you can use a Qubes Vault VM which has Net VM set to None.

<br/>

### Split GPG & SSH

Qubes Docs - [Tor Link](http://qubesosfasa4zl44o4tws22di6kepyzfeqv3tg4e3ztknltfxqrymdad.onion/doc/split-gpg/) | [Clearnet Link](https://www.qubes-os.org/doc/split-gpg/)

Guide 1 - [Clearnet Link](https://deniszanin.com/using-split-ssh-gpg-in-qubes-os/)

Guide 2 - [Clearnet Link](https://deniszanin.com/using-git-in-qubes-4-split-ssh-split-gpg/)

Guide 3 - [Clearnet Link](https://thedarktrumpet.com/security/2022/05/29/split-ssh-gpg/)

<br/>

## VPNs

Setup Wireguard VPN in a Proxy VM. 

Wireguard VPN Setup - [Clearnet Link](https://forum.qubes-os.org/t/wireguard-vpn-setup/19141)

Reusable Wireguard Template VM - [Clearnet Link](https://github.com/hkbakke/qubes-wireguard/tree/master)

More Info On Proxy VMs - [Clearnet Link](https://forum.qubes-os.org/t/configuring-a-proxyvm-vpn-gateway/19061)

Mullvad VPN On Qubes OS - [Tor Link](http://o54hon2e2vj6c7m3aqqu6uyece65by3vgoxxhlqlsvkmacw6a7m7kiad.onion/en/help/wireguard-on-qubes-os) | [Clearnet Link](https://mullvad.net/en/help/wireguard-on-qubes-os)

Consider using customized minimal templates for NetVMs to reduce the attack surface and memory requirements.

Minimal Templates - [Tor Link](http://qubesosfasa4zl44o4tws22di6kepyzfeqv3tg4e3ztknltfxqrymdad.onion/doc/templates/minimal/) | [Clearnet Link](https://www.qubes-os.org/doc/templates/minimal/)

Debian Templates - [Tor Link](http://qubesosfasa4zl44o4tws22di6kepyzfeqv3tg4e3ztknltfxqrymdad.onion/doc/templates/debian/) | [Clearnet Link](https://www.qubes-os.org/doc/templates/debian/)

<br/>

## Whonix

Security, Privacy, Hardening, Etc:

Whonix Wiki - [Tor Link](http://www.dds6qkxpwdeubwucdiaord2xgbbeyds25rbsgr73tbfpqpt4a6vjwsyd.onion/wiki/) | [Clearnet Link](https://www.whonix.org/wiki)

Hardening Checklist - [Tor Link](http://www.dds6qkxpwdeubwucdiaord2xgbbeyds25rbsgr73tbfpqpt4a6vjwsyd.onion/wiki/System_Hardening_Checklist) | [Clearnet Link](https://www.whonix.org/wiki/System_Hardening_Checklist)

<br/>

## VM Resource Usage

To edit the VCPUs and RAM usage for each VM, click the blue cube icon in the system tray, and select Open Qube Manager. From there you can right-click each VM, select Settings, and go to the Advanced tab.

I think 2VCPUs and 2gb RAM for things like very basic tasks. For heavier tasks like the VM with mediacodecs and videostreaming, then 4VCPU and 4gb RAM is a good starting point. All service VMs should be 1 VCPUs wtih 400mb/400mb fixed RAM (do not enable memory balance). Qubes uses a ton of RAM so make sure you have proper hardware.

Here are some examples to guide you.

*sys-net:* can stay at default settings.

*sys-firewall:* 1 VCPUs - 400mb Initial memory / 400mb Max memory

*sys-whonix:* 1 VCPUs - 400mb Initial memory / 400mb Max memory

*vault:* 1 VCPUs - 400mb Initial memory / 400mb Max memory

*anon-whonix:* 1 VCPUs - 800mb Initial memory / 2000mb Max memory

*whonix-ws-17-dvm:* 2 VCPUs - 400mb Initial memory / 2000mb Max memory

*default-dvm:* 2 VCPUs - 400mb Initial memory / 2000mb Max memory

*multimedia:* 4 VCPUs - 800mb Initial memory / 8000mb Max memory

Want to see resource usage of each VM? Try the following command:

    ```
    xl top
    ```

Want to check total RAM used/recognized by dom0? Try the following command:

    ```
    sudo xl info
    ```

<br/>
