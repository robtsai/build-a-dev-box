# build-a-dev-box
My notes on building a dev box on Ubuntu 16.04 LTS and Thinkpad T450s


## My environment ##

I'm a huge fan of the Lenovo T450s.  The base config with 8GB RAM and a 256 GB SSD, with a dual core i7 (with Hyper Threading).  The machine is very upgradeable.  I've read that the motherboard supports up to 16GB DDR3 RAM in the DIMM slot, on top of the 4GB sodered to the motherboard.  So one day, I may do that, but 8GB is pretty good for now.

I've chosen to go with Ubuntu LTS 16.04.  I tried Ubuntu MATE as well, but I don't mind the Unity desktop environment.  It runs a bit heaver on the memory footprint, about 1.3 GB when idle on my machine versus 700 Mb when idle using Ubuntu MATE.

## The Install ##

The installer is really simple.  I burned an ISO onto the USB flash drive, using RUFUS from my Windows machine.

Then you just boot up the Lenovo, press ENTER to get to the boot menus.  You will need to enter the BIOS to disable secure boot. 

Then you want to press F12 to select to boot off your USB, and you can proceed to install off the flash drive.

The default selections are all good.  I wiped out my Windows OS, and Ubuntu will write a GRUB2 boot loader into your boot partition.  I created an LVM disk, but in the future, I'd stick with the basic option, as I think you can use GParted as your partition editor.


## The config ##

Some quick configs.

I run from the command line a couple of quick commands:
<pre>
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install gparted
sudo apt-get install unity-tweak-tool
sudo apt-get install mono-complete
sudo apt-get install git
</pre>

I also like moving the launcher to the bottom of the screen - use the Unity Tweak Tool.

Some .deb packages to install include:

Google Chrome
Sublime Text 3
Haroopad

Simply run the command:
<pre>
sudo dpkg -i sublime-text-_build-3126_amd64.deb
</pre>


## Set Up Git ##

You will need to set up your ssh keys first.  I run this from my home directory.

<pre>
ssh-keygen -t rsa
</pre>

The defaults are fine,  You will now have two files in your ~/.ssh directory
<pre>
id_rsa
id_rsa.pub
</pre>

Make sure to add your public key to your Github profile deploy keys.

You can now set your config.

<pre>
git config --global user.name yourgitname
git config --global user.email youremail
</pre>






