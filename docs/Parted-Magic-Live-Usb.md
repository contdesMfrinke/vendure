
 
I am looking for a distribution/live cd that enables ssh/telnet (or something similar) on boot. The reason I need this: I am trying to get data from a broken all-in-one PC (only the monitor appears broken), and do not have access to a monitor.
 
Seriously, I think the easiest situation would be the Arch installer since it drops you into the tty, logged in ready to go. With other live media, you will end up in a gui, in which case you would need to start a terminal, then issue these commands. I think that you have figured out above that even if you can get a live media with sshd started by default, you still need a password, which you will have to set. This being the case, I can't seem to understand why blindly issuing two commands is not a viable option.
 
**Download –––––>>> [https://amreamate.blogspot.com/?d=2A0SYx](https://amreamate.blogspot.com/?d=2A0SYx)**


 
How about instead of simply shooting down every suggestion that comes along, why don't you try something! Besides, this is information that should be attainable with a search engine, so you since no one seems to be able to come up with what you consider a valid answer, you are now simply outsourcing searches.
 
I never said you were rude, but I am giving you a viable solution. It is not like you are going to have to do this over and over again, you simply need access to your headless machine (hopefully just once anyway).
 
I did exactly what I am proposing to you when I installed Arch on my headless server. So I know it can be done, and it is probably one of the simplest of solutions... by that I mean you could be moving data off your drive by now.
 
I tried this earlier, but it did not seem to work. I'll move the PC downstairs and hook it up straight to the router instead of my current usage of powerline ethernet (seems harder to find the IP with nmap), and try the arch iso again.
 
Parted Magic starts sshd on boot. I am not sure if root is allowed to login, but the root password would be "partedmagic" (i believe). Will check this when i'm back home. However, you need to be connected by wire.

As in the title:When I add programs to Parted Magic
(as described here: -programs/ ; I actually "make my own bundle" by using "mksquashfs"; I applied chmod 777 \* -R to my filesystem before using "mksquashfs"; I then copyied the resulting \*.sqfm file to the indicated folder (on the USB pendrive, which stays bootable; not nessessary to write the whole iso-image again); at the time of booting Parted Magic from the USB pendrive, my files are automatically installed by Parted Magic)
and I try to start firefox (which is part of the standard package of Parted Magic) this is not possible.(when using parted magic as is ("out-of-the-box"), firefox can be started without any problem.)
 
Now, my question is: Why does adding own programs (or even minor changes, like a textfile that is placed on the desktop of "Parted Magic") cause that ownership of /root is changed to uid 1000 ? What do I need to do to avoid this change of ownership when adding stuff to "Parted Magic" ?
 
to change ownership of all files (and all subdirectories) in the current directory to root(be careful: by this command, you can potentially wreak your system, if you apply it when being in the wrong directory)
 
What obviously happens is: When "Parted Magic"- during the booting process - installs the files contained in the \*.sqfm file that I added, it will change the ownership of /root in the case that one of the files that get added to /root in the process, are not owned by root.
 
4. Open up the ISO using 7Zip or any other tool and locate the SQFS file in the \pmagic\pmodules folder and note the exact filename and CASE (if the case is not correct, you may not be able to Save the session on exit).
 
4. Once Parted Magic is booting, if the **boot=live** parameter has been specified, it will look for a folder on any drive that has the \pmagic\pmodules\xxx.sqfm saved session file. Luckily, it seems to search all drives and so it should find the folder we created on the USB drive.
 
"Dr.Parted Live is a bootable GNU/Linux distribution based on Debian Testing. It is a live CD/USB featuring a lightweight Openbox window manager and useful applications for data backup, restore and recovery."
 
What does Dr Parted offer that might get a user to switch from one of a half dozen similar tools? I use Gparted's live iso. What's the benefit offered to entice me to change? I've also used Parted Magic. QtParted is a free version of Parted Magic.

 
I guess one could say the same for Linux distos. What does one have over another? What does one bring to the table that another does not? What can one distro do that another can not? Which distro is the best or better? All subjective opinions. Dont shoot the messenger.
 
Problem being, I am not sure how to (at least) keep an eye on the "space" left of the filesystem (Note: There is no entry for the / partition in the output of df, fdisk -l or mount), let alone (assuming I am right that the filesystem space not being relative to the system memory, that I had been monitoring with conky) how to go about increasing the sizing ?at boot time?
 
P.S Thought it most appropriate to tag this question with parted-magic, ramfs (or tmpfs... Not sure how to identify which one is in use) and low-disk-space like tags, but alas there doesn't appear to be any of them. If the community doesn't want to create one/all, please feel free to suggest other tags that others feel are appropriate.
 
By default, a tmpfs ramdisk will be set up to use a maximum of half of the available RAM in the system (note that a standard, non-PAE, 32-bit kernel can address a maximum of 4GB less any address space used by devices like VGA cards).
 
I've just booted Parted Magic 2013 08 01 in a virtual machine, giving it 4GB RAM. The rootfs has a total of 2GB, with about 444KB used, so PM is using the defaults for tmpfs. If i reboot the VM with only 1GB RAM, the root tmpfs has only 504MB available - the kernel uses some, so that's slighly less than half total RAM.
 
It also mounts /tmp and /run as tmpfs of the same size. Note that these filesystems are not additional space, they use the same pool of RAM as the rootfs and any running programs (i.e. slightly less than 1GB on a system with 1GB RAM).
 
The important thing to remember is that tmpfs and any programs running share the same system memory - so if you fill up the tmpfs, it will reduce the amount of RAM available for running programs, and if you run programs that use lots of RAM, it will reduce the amount of RAM available for tmpfs.
 
You seem to be doing both. You're filling up the disk with your log files, **AND** you're running firefox, X, and rdesktop - all of which tend to use large amounts of RAM. Unix systems don't react well when the rootfs gets full, and when RAM starts getting tight the Linux kernel's out-of-memory (OOM) task will start randomly killing processes to free up some RAM.
 
As others have suggested, I strongly recommend that you don't use a Live CD (Parted Magic or any other) in this way. They're not designed for it, and what you are doing is pretty much guaranteed to cause problems. In short, Don't Do That, Then!.
 
Instead, either re-partition your hard disk and install a small distro onto it, run a linux distro in a VM, or find a distro that installs and runs off a USB stick without using tmpfs for /root - i.e. uses the USB stick as its root filesystem (this would be a lot slower than running from a tmpfs. and no, I don't know of any that work like that). or use a USB hard disk rather than a USB flash disk.
 
Parted shows the available memory on it's little "heads up" display (apparently called conky) in the top right hand corner. So you don't even have to work out how to get this information, it is already displayed. (As the available memory IS your free disk space left).
 
Anyway, that said, to check the space available you can just run df. I don't want to buy a copy of Parted Magic OS to test this, but the following is the output of df on a virtual machine running an Ubuntu Live CD:
 
Most of these are tmpfs style things (non of them are actual mounted partitions anyway) that exist in RAM. df can still accurately report usage. If you don't see a / entry under Parted magic, I guess they are using some kind of esoteric naming. Another hint that you are using the wrong tool for the job.
 
I've run into this problem for years on live CD/DVD/USB distros like Debian, Ubuntu, Mint, maybe even Fedora if I recall. Memory used by overlayfs (the currently used fstype for live Mint/Ubuntu) and tmpfs are hidden in free 's cached memory (and /proc/meminfo's Inactive entries), along with temporary disk read caches, so it's unclear how much memory is really "free".
 
I'm using df to add up all the space used by overlayfs & tmpfs, and subtracting it from the free + buffers + cached info from free. I'll have conky highlight that number next to it's misleading "free ram". All sizes are in K's.
 
If your distro's live version doesn't support df then I don't know where to look for info on overlayfs/tmpfs. mount, /proc/mounts and /etc/mtab seem to only show maximum or no sizes, not current size like df does.
 a2f82b0cb4
 
