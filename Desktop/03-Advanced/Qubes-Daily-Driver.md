https://github.com/Qubes-Community/Contents/tree/master
https://forum.qubes-os.org/c/guides/14

Icons:

https://askubuntu.com/questions/95104/how-to-lock-desktop-icons-on-xfce

https://forum.xfce.org/viewtopic.php?id=7597

Adding +i or -i adds or takes away immutability. When the file is immutable the desktop icon positions cannot be modified on screen resize/system reboot.

`sudo chattr +i ~/.config/xfce4/desktop/icons*`

`sudo chattr -i ~/.config/xfce4/desktop/icons*`

<br/>

# Turn qubes into a daily driver 

## Multimedia VM

Multimedia VM for things like Google chrome, vlc media player, spotify, etc.

I prefer Fedora rather than Debian for this.

https://www.qubes-os.org/doc/multimedia/

<br/>

For quick Chrome install:

`sudo nano /etc/yum.repos.d/google-chrome.repo`

<br/>

Make enabled true by changing:

`enabled=0` to `enabled=1`

Use Ctrl+O to save and Ctrl+X to exit nano text editor.

<br/>

Install:

`sudo dnf install google-chrome-stable`

Some users may want rpmfusion repository because it has some useful software. 

<br/>

Enter these commands if you want rpmfusion:

```sudo dnf config-manager --set-enabled rpmfusion-free rpmfusion-nonfree```

```sudo dnf upgrade --refresh```

When installing you will see all sha256checksums for the software, check that they match by using websites like:

https://rpmfusion.org/keys

(Optional) Resize disk image as needed and install cryptocurrency wallets in AppVMs as needed. 

(Optional) Resize app VMs or template VMs disk image as needed using `sudo df` to check on image size.

https://www.qubes-os.org/doc/resize-disk-image

<br/>

## Messenger

Make a standalone VM for your messengers. See VM settings above for VCPU and RAM info.

I prefer to intall `telegram-dekstop` on fedora using rpm fusion repo (info above):

<br/>

Install using rpm fusion:

```sudo dnf install telegram-desktop```

<br/>

Other Info:

https://snapcraft.io/install/telegram-desktop/fedora

https://snapcraft.io/docs/getting-started

https://www.addictivetips.com/ubuntu-linux-tips/how-to-use-and-install-snap-packages-on-linux/

A snap’s installed applications can be found under /snap/bin, and subsequently, often added to $PATH. This makes commands directly accessible from the command line.

<br/>

For example, the command installed via the VLC snap is simply vlc:

```which vlc```

```/snap/bin/vlc```

<br/>

If executing a command directly doesn’t work, try prefixing it with the /snap/bin path:

```/snap/bin/vlc```

Adding /snap/bin to your default $PATH makes running snaps that don’t automatically add themselves more convenient.

<br/>

Snaps are updated automatically. However, to manually check for updates, use the following command:

`sudo snap refresh vlc`

Finally, use https://www.qubes-os.org/doc/managing-appvm-shortcuts/ to get a #shortcut setup

<br/>

telegram 256x256 icon path:

```/var/lib/snapd/snap/telegram-desktop/1038/share/icons/hicolor/256x256/apps/telegram.png```

<br/>

## Tips and Tricks

Nvidia GPU Drivers on Fedora:

https://linuxconfig.org/how-to-install-the-nvidia-drivers-on-fedora-32

<br/>

Message of the day:

https://forums.fedoraforum.org/showthread.php?255780-How-to-get-motd-to-display

<br/>

Use this command in dom0 to monitor resources used by VMs:

```xl top```

```sudo xl info | grep -i total_memory```

You may wonder you see sys-net-dm & sys-usb-dm in addition to sys-net & sys-usb VMs from the output of this command. I was able to find the following answer.

"Xen uses by default qemu for HVMs. But this increases the attack surface for dom0, so in Qubes qemu is started in a PV domain, which is called [domainname]-dm."

<br/>

Troubleshooting signed git commits:

https://github.com/pstadler/keybase-gpg-github/issues/24#issuecomment-340877348

https://github.com/keybase/keybase-issues/issues/1712#issuecomment-141226705

When trying to get setup with gpg + git I was getting error when trying to make signed commits.

<br/>

Output: 

```> error: gpg failed to sign the data```

```> fatal: failed to write commit object```

Found the 2 links above that explain to try testing command below. If this fails with folowing errors, then you will know gpg having a problem.

<br/>

Run Command:

```echo "test" | gpg --clearsign```

<br/>

Output:

```> gpg: signing failed: Inappropriate ioctl for device```

```> gpg: [stdin]: clear-sign failed: Inappropriate ioctl for device```

To get rid of the completely usless misleading "Inappropriate ioctl for device" error, you have to run following command.

<br/>

Run Command:

```export GPG_TTY=$(tty)```

https://gist.github.com/Joeviocoe/6c4dc0c283f6d6c5b1a3f5af8793292b

<br/>

<br/>

talk about the alt + f3 trick

## Disposable VMs

On a fresh installation of Qubes, the default DVM Template is called fedora-XX-dvm (where XX is the Fedora version of the default TemplateVM). If you have included the Whonix option in your install, there will also be a whonix-ws-dvm DVM Template available for your use.

<br/>

You can set any AppVM to have the ability to act as a DVM Template in dom0 with:

```
qvm-prefs <vmname> template_for_dispvms True
```

The default system wide DVM Template can be changed with qubes-prefs default_dispvm. By combining the two, choosing Open in DisposableVM from inside an AppVM will open the document in a DisposableVM based on the default DVM Template you specified.

You can change this behaviour for individual VMs. 

In the Application Menu, open Qube Settings for the VM in question and go to the “Advanced” tab. Here you can edit the “Default DisposableVM” setting to specify which DVM Template will be used to launch DisposableVMs from that VM. 

<br/>

This can also be changed by running the following command in dom0:

```
qvm-prefs <vmname> default_dispvm <dvmtemplatename>
```

For example, anon-whonix has been set to use whonix-ws-dvm as its default_dispvm, instead of the system default. You can even set an AppVM that has also been configured as a DVM Template to use itself, so DisposableVMs launched from within the AppVM/DVM Template would inherit the same settings.

NetVM and firewall rules for DVM Templates can be set as they can for a normal VM. By default a DisposableVM will inherit the NetVM and firewall settings of the DVM Template on which it is based. This is a change in behaviour from R3.2, where DisposableVMs would inherit the settings of the AppVM from which they were launched. Therefore, launching a DisposableVM from an AppVM will result in it using the network/firewall settings of the DVM Template on which it is based. For example, if an AppVM uses sys-net as its NetVM, but the default system DisposableVM uses sys-whonix, any DisposableVM launched from this AppVM will have sys-whonix as its NetVM.

Warning: The opposite is also true. This means if you have changed anon-whonix’s default_dispvm to use the system default, and the system default DisposableVM uses sys-net, launching a DisposableVM from inside anon-whonix will result in the DisposableVM using sys-net.

A DisposableVM launched from the Start Menu inherits the NetVM and firewall settings of the DVM Template on which it is based. Note that changing the “NetVM” setting for the system default DVM Template does affect the NetVM of DisposableVMs launched from the Start Menu. Different DVM Templates with individual NetVM settings can be added to the Start Menu.

<br/>

Important Notes:

Some DVM Templates will automatically create a menu item to launch a DVM, if you do not see an entry and want to add one please use the following command:

```
qvm-features deb-dvm appmenus-dispvm 1
```

<br/>

To launch an App in DVM run the following command in dom0:

```
qvm-run --dispvm=NameOfDVM --service qubes.StartApp+NameOfApp
```

<br/>
