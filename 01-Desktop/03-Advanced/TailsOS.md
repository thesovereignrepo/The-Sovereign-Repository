# TAILS - Advanced

## Table of Contents
* [1. Intro](#intro)
* [2. Install](#install)
* [3. VPN](#vpn)
* [4. Tor Browser](#tor-browser)
* [5. Web Browser](#web-browser)
* [5. Password Manager](#password-manager)


## Ratings
Gaming: Low
Enterprise: Low
Security: High
Privacy: High
Cryptocurrency: High
Open Source: Yes

<br/>

## Intro 

- Using a personal computer today may not be as private as you think, given the digital footprints left behind that can be discovered by others.

- The Tails operating system offers a comprehensive solution for maintaining anonymity and avoiding detection by those who might intrude on your privacy.

- Tails or The Amnesic Incognito Live System is one of most secure portable operating systems (OS).

https://tails.net/doc/index.en.html

https://tails.net/doc/first_steps/desktop/index.en.html

Everything you do disappears automatically when you shut down Tails. This is a default setting.

But you can save some of your files and configuration in an encrypted Persistent Storage on your Tails USB stick, for example:

https://tails.net/doc/persistent_storage/index.en.html

<details><summary>**First time? Click to expand ...**</summary>

Developed based on Debian GNU/Linux, it protects you against surveillance, censorship, advertising, and viruses.

Unlike typical operating systems like Windows, Linux, etc., that use the hard drive to boot, Tails starts using a USB drive and turns your computer into a secure system.

Because of the protection it provides, it has widespread usage among many people who have a dire need of online privacy and security. Journalists and hackers are at the top among people who use it.

The most controversial example is the NSA whistleblower Edward Snowden, who has claimed to have used Tails to leak secret files of the NSA.

So how Does Tails Work?

Tails are installed on a USB drive to boot up the OS using the USB stick without using the machine’s hard disk. Thus, it is independent of the current OS installed in the machine.

It encrypts your files and internet usage, and nothing gets saved on your HDD or SSD. So, after you shut down your computer, you will never leave any trace of anything you did or accessed on the machine you have the Tails USB plugged into.
Privacy

Tails uses a Tor network for all the internet activities encrypting and anonymizing your connection.

Because of this, third parties will not know what websites you are visiting. Moreover, advertisers cannot learn about your browsing habits as Tor allows you to be anonymous and change your identity if you need.

In addition, Tails provides a set of software applications like LibreOffice, where you can work on sensitive documents, OnionShare, Thunderbird, and many more.

Did you know about Persistent Storage?

Once you are disconnected from Tails, everything you did disappears, including the saved files. But you have the option to save the files persistently in its persistent storage.

Everything in the persistent storage will be encrypted with password protection making everything in it secured and private.

</details>
<br/>

## Install 

Here’s how to get started with Tails.

1. First, Download Tails from the official Tails website’s download page, selecting your operating system correctly. You can either directly download Tails from USB Image or download through BitTorrent, which will be much faster.

2. After the download, if you downloaded directly, verify the download by clicking on ‘Verify Tails’. Then select the USB image you downloaded.

3. After that, the page will run the check. This step ensures that the download is not a malicious tails USB image.

4. Verification from the Tails page is based on a Javascript code embedded in the Tails download page. You do not need this step if you download through BitTorrent because BitTorrent will automatically verify the download using checksum.

5. You will get the a successful verification notification if the verification is successful.

6. Next, you need to download a USB installer Etcher to write the Tails ISO image downloaded and create a bootable USB flash drive. You can get Etcher for windows from the link in the previous sentence.

7. Plug your USB device into your machine. Then, click on the downloaded Etcher installer to start Etcher.

8. Click the Select ‘Flash From file’ option. Then, select the Tails USB image, which should have a .img file extension that you downloaded earlier. You can also choose Flash from the URL option if you choose to download Tails from another mirror.

9. Next, click on ‘Select Target.’ Etcher will list all the connected USB drives and automatically selects a USB stick. Select the USB drive you want to install Tails on from the list.

10. Finally, click on ‘Flash!’. Etcher will Flash your USB drive with Tails on your selected USB, which should take only a few minutes.

11. Make sure target PC is powered off, stick USB stick in, and boot into bios

12. If successful you will boot into TAILS for the first time

## Persistent Storage 

For those who need to keep files on a long-term basis, Tails offers an option to set up persistent storage. By using two USB drives, you can create a securely encrypted persistent storage area.

Everything you do disappears automatically when you shut down Tails. This is a default setting.

But you can save some of your files and configuration in an encrypted Persistent Storage on your Tails USB stick, for example:
https://tails.net/doc/persistent_storage/index.en.html

What are the system and device requirements?

    A USB drive. You will need one USB drive to install Tails with at least 8GB of memory. Remember that you will lose all the data on your USB drive during the installation. Thus, make sure to use an empty USB drive.

    Your computer should have at least 2GB of RAM.

    About half an hour of your time to install Tails and time to download around 1.2 GB of data.

Everything you save inside Tails will vanish after you have shut it down. Thus, you can create persistent storage if you need to keep them persistently. Let’s see in this section how you can configure it.

Configure the Persistent Storage

    Click on the applications menu in the top-left corner and choose ‘configure persistent volume’. Then you will get the following persistent volume setup window.
    Insert and verify a passphrase according to the requirements.

    Tails Persistent Storage
    Click on the Create button, and Tails will give you a list of features of Persistent Storage. Select only the features that you require.
    Click Save.

    Restart the computer on Tails

    Shut down the computer and, as explained earlier, restart your Tails USB drive.
    This time, you will get the following welcome screen consisting of an option to input your persistent storage passphrase.
    Tails Installation - Restart Computer

    Select your Language & Region settings.
    In the Encrypted Persistent Storage input box, enter the passphrase you have configured earlier and unlock the Persistent Storage for the current working session.
    Click on Start Tails. Within a few seconds, you will get the Tails desktop.

There is a Persistent folder in the home directory where you can now save all the working files, images, etc. You can open the Persistent folder from Places -> Persistent.

Make sure to take a backup of the persistent folder because the USB stick can become corrupted or damaged at any time.
How to Install Tails on Two USBs?

You can also use two USBs to install and run Tails. Using two USBs is to use the Tail installer for incremental updates and create a secure encrypted persistent storage. You can use just one USB drive if you do not need encrypted storage.

For this, you need two USB drives of at least 4GB of storage each. Install Tails as described above on the first USB.
Create the Second USB

    After installing the first USB, plug in the second USB and restart your computer with Tails. Select Tails from the boot menu.
    Then, after the Tails welcome screen appears, select the language and region and start Tails. Within a few seconds, The Tails desktop will appear. At this time, Insert your second USB.
    Finally, open the “Applications” menu in the upper-left corner of the desktop. Next, click on “Tails,” -> “Tails Installer”.

    Install Tails on Two USBs
    Choose the first option, “Clone the current Tails.”. Once you click it, you’ll be able to select your second USB from target USB sticks and confirm the installation.
    After the installation completes, you’ll have another Tails USB.
    Remove the first USB, and restart the PC back on the second USBTails. You’ll see Tails starting on it successfully.

<br/>

## Tor Browser

Tails - Connect to the Internet

Tails - Connect to Wi-Fi

Tails - Connect to Tor

Tails - Connecting to the Internet with Tor

Tails - Tor Browser

After successfully connecting to the Tor browser, you can safely surf the internet. If you want to send any saved files through email, you need to keep the files in the ‘Tor browser folder.’ Otherwise, Tails does not allow you to access any file in the default home directory, where you will save your files.

## Web Browser
