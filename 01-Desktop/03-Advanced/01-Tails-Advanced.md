# TAILS - Advanced

## Table of Contents
* [1. Intro](#intro)
* [2. Install](#install)
* [3. Persistent Storage](#persistent-storage)
* [4. Tor Browser](#tor-browser)
* [5. Password Manager](#password-manager)
* [6. VPN](#vpn)
* [7. Continue Your Training](#continue-your-training)

## Ratings
Gaming: Low
Enterprise: Low
Security: High
Privacy: High
Cryptocurrency: High
Open Source: Yes

<br/>

## Intro

- Tails or The Amnesic Incognito Live System is one of most secure portable operating systems (OS).

- The Tails operating system offers a comprehensive solution for maintaining anonymity and avoiding detection by those who might intrude on your privacy.

- Tails may not have perfect gaming capability or support Microsoft Office, but that is outside its scope, and the point is it will help you stay private and secure where needed.

- For an average user, Qubes is all you will ever need for for your sensitive tasks on Desktop or Laptop.

<details><summary>**First time? Click to expand ...**</summary>

Developed based on Debian Linux, Tails protects you against surveillance, censorship, advertising, and malware. Unlike typical operating systems like Windows, Linux, etc., that use the hard drive to boot, Tails starts using a USB drive and turns your computer into a secure system.

Because of the protection it provides, it has widespread usage among many people who have a dire need of online privacy and security. Journalists, high value targets, cryptocurrency users, ethical hackers are at the top among people who use it. Tails is there for anyone that faces currently active threats. The most controversial example of usage is the NSA whistleblower Edward Snowden, who has claimed to have used Tails to leak secret files of the NSA.

So how Does TailsOS work? Tails is installed on the USB stick without using the machine’s hard disk. Thus, it is independent of the current OS installed in the machine. It encrypts your files and internet usage, and nothing gets saved on your HDD or SSD. So, after you shut down your computer, you will never leave any trace of anything you did or accessed on the machine you have the Tails USB plugged into.

Tails uses the Tor network for all the internet activities encrypting and anonymizing your connection. Because of this, third parties will not know what websites you are visiting. Moreover, advertisers cannot learn about your browsing habits as Tor allows you to be anonymous and change your identity if you need. Finally, Tails provides a set of software applications like LibreOffice, where you can work on sensitive documents, OnionShare for file transfer, Thunderbird for email, and many more.

Before you continue, did you know about Persistent Storage? Once you are disconnected from Tails, everything you did disappears, including the saved files. But you have the option to save the files persistently. Everything in the Persistent Storage will be encrypted with password protection making everything in it secured and private.

Docs - https://tails.net/doc/index.en.html
First Steps - https://tails.net/doc/first_steps/desktop/index.en.html
Persistent Storage - https://tails.net/doc/persistent_storage/index.en.html
Video - TODO

</details>
<br/>

## Install 

Here’s how to get started with Tails.

1. First, Download Tails from the official [Tails Download Page](https://tails.net/install/index.en.html), selecting your operating system correctly. You can either directly download Tails from USB Image or download through BitTorrent, which will be much faster.

2. After the download verify it by clicking on `Verify Tails`. Then select the USB image you downloaded.

3. After that, the page will run the check. This step ensures that the download is not a malicious Tails USB image.

4. Verification from the Tails page is based on a Javascript code embedded in the Tails download page. You do not need this step if you download through BitTorrent because BitTorrent will automatically verify the download using checksum.

5. You will get the a successful verification notification if the verification is successful.

6. Next, you need to download a USB installer Etcher to write the Tails ISO image downloaded and create a bootable USB flash drive. You can get Etcher for windows from the [Balena Etcher Website](https://etcher.balena.io/).

7. Plug your USB device into your machine. Then, click on the downloaded Etcher installer to start Etcher.

8. Click the Select `Flash From file` option. Then, select the Tails USB image, which should have a .img file extension that you downloaded earlier. You can also choose Flash from the URL option if you choose to download Tails from another mirror.

9. Next, click on `Select Target`. Etcher will list all the connected USB drives and automatically selects a USB stick. Select the USB drive you want to install Tails on from the list.

10. Finally, click on `Flash!`. Etcher will flash your USB drive with Tails on your selected USB, which should take only a few minutes.

11. Make sure target PC is powered off, stick USB stick in, and boot into bios. Select USB as boot device.

12. If successful you will boot into Tails for the first time.

<br/>

## Persistent Storage

Everything you do disappears automatically when you shut down Tails. This is a default setting.For those who need to keep files on a long-term basis, Tails offers an option to set up persistent storage. By using two USB drives, you can create a securely encrypted [Persistent Storage](https://tails.net/doc/persistent_storage/index.en.html) area.

1. Configure the Persistent Storage Click on the applications menu in the top-left corner and choose `configure persistent volume`. Then you will get the following persistent volume setup window. Insert and verify a passphrase according to the requirements.

2. Click on the `Create` button, and Tails will give you a list of features of Persistent Storage. Select only the features that you require.

3. Shut down the computer and, as explained earlier, restart your Tails USB drive. This time, you will get the following welcome screen consisting of an option 

4. In the Encrypted Persistent Storage input box, enter the passphrase you have configured earlier and unlock the Persistent Storage for the current working session. Click on Start Tails. Within a few seconds, you will get the Tails desktop.

5. There is a Persistent folder in the home directory where you can now save all the working files, images, etc. You can open the Persistent folder from Places -> Persistent.

6. Make sure to take a backup of the persistent folder because the USB stick can become corrupted or damaged at any time.

<br/>

## Tor Browser

The Tor Browser comes built into Tails. Open the applications menu to launch Tor Browser and you can get started privately browsing right away!

<br/>

## Password Manager

The KeePass Password Manager comes built into Tails so you can get started managing your passwords right away! KeePass can also be used for 2FA in addition to usernames, passwords, etc.

TODO: Make sure db added to persistence, see [docs](https://tails.net/doc/encryption_and_privacy/manage_passwords/index.en.html).

<br/>

## VPN

VPN is not recommended with Tails operating system and VPN should not be considered truly private or for anonoymous browsing. VPN is never a replacement for Tor.

If you do decide to install a VPN, it should only be used for very casual browsing and never for any sensitive task.

## Coin

TODO

## Continue Your Training

The majority of normal users will at most need Tails for their sensitive tasks and not need to continune any further with the desktop computer guides. Now continue to the [Mobile Section](https://github.com/thesovereignrepo/The-Sovereign-Repository/tree/master/02-Mobile) of guides to advance your traning further.

Only continue to the next set of desktop computer guides if you are a dev, sysadmin, hardcore poweruser, find Tails features lacking, and yearn for a more complex setup. See the [Hardcore Section](https://github.com/thesovereignrepo/The-Sovereign-Repository/tree/master/01-Desktop/04-Hardcore) to learn more about the peak of extreme security and privacy focused operating systems.
