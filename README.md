AMD fglrx-core-15.201
=================

16-09-2015

fglrx-core-15.201, source + patches compiled on 64bit system, kernels: 

3.19.0-29-generic ( Ubuntu 15.04 ),
4.1.7, 
4.2.0,
4.3.0-rc1,
4.4.0


# check yours kernel version for compatibility 
command

	hostnamectl status

Result

	   Static hostname: Baybucher27-Android
		 Icon name: computer-laptop
		   Chassis: laptop
		   Boot ID: da97acdd4755401ea0228f4b90bef664
	  Operating System: Ubuntu 14.04.5 LTS
		    Kernel: Linux 4.4.0-34-generic
	      Architecture: x86_64


# How to install by BHB27:

I did this just in case I forget how to do...

This is for 12.9 but the tutorial work for me on update version to use on a update version of the driver but is need to use this repository https://github.com/bhb27/fglrx-15.30.1025 on [step 4] (https://github.com/bhb27/fglrx-core-15.201#step-4-download-this-git-repository-and-extract-it) and then just change where there is **201** with **302** or the number of the driver you trying to use.

I install this driver using GCC4.9 below there is a tutorial on [GCC 4.9 how to use it:] (https://github.com/bhb27/fglrx-core-15.201#this-was-build-using-gcc-49-how-to-use-it)

I used this for ubuntu 14.04.05 with amd-catalyst-15.9-linux-installer-15.201.1151-x86.x86_64.zip


# Step 1 Download
* [Download amd-catalyst-15.9-linux-installer techspot mirror](http://www.techspot.com/downloads/drivers/essentials/amd-catalyst-linux/)
* There may be other mirror or the original AMD site http://support.amd.com/en-us/download/desktop?os=Linux+x86_64 But that only display the latest driver this is for older version

# Step 2 extract the Download file .zip
file name

**amd-catalyst-15.9-linux-installer-15.201.1151-x86.x86_64.zip**

# Step 3 extract the extracted file .run
Go to extract folder, open the properties of file (right mouse key properties)

**amd-driver-installer-15.201-x86.x86_64.run**

Check permission and give read and write to all and enable execute

now run on terminal

	./amd-driver-installer-15.201-x86.x86_64.run --extract

# Step 4 Download this git repository and extract it
go to folder generated

**fglrx-install.xxxxx/common/lib/modules/fglrx/build_mod**

Download this git repository extract the generated zip and place/override all the files from it in the above folder

# Step 5 Install drivers

back to main folder **fglrx-install.xxxxx/**

run the install

	sudo ./ati-installer.sh 15.201 --install

if received a error check **/usr/share/ati/fglrx-install.log**
Google to solve error if not encounter a solution on the [Help below](https://github.com/bhb27/fglrx-core-15.201#help)


if the install start ok no error do the below

Don't change a thing just click... **continue > I agree > continue**
The process will generates the drivers 5 to 10min
After the drivers be generate you will be ask to click **Exit**, if all build ok you will be ask **to install** click **Ye**s to install now

check the terminal when everything end reboot the machine and test *** very important check the below [Help below](https://github.com/bhb27/fglrx-core-15.201#help) before reboot check the [how to uninstall] (https://github.com/bhb27/fglrx-core-15.201#how-to-uninstall)

##log of installation
This is from the installation of 15.302 but is all the same

	update-alternatives: using /usr/lib/fglrx-core/ld.so.conf to provide /etc/ld.so.conf.d/x86_64-linux-gnu_GFXCORE.conf (x86_64-linux-gnu_gfxcore_conf) in auto mode
	Loading new fglrx-core-15.302 DKMS files...
	Building only for 4.4.0-34-generic
	Building for architecture x86_64
	Building initial module for 4.4.0-34-generic
	Done.

	fglrx:
	Running module version sanity check.
	 - Original module
	   - No original module exists within this kernel
	 - Installation
	   - Installing to /lib/modules/4.4.0-34-generic/updates/dkms/

	depmod.....

	DKMS: install completed.
	update-initramfs: deferring update (trigger activated)
	Setting up fglrx (2:15.302-0ubuntu1) ...
	update-alternatives: using /usr/lib/fglrx/ld.so.conf to provide /etc/ld.so.conf.d/x86_64-linux-gnu_GL.conf (x86_64-linux-gnu_gl_conf) in auto mode
	update-alternatives: warning: forcing reinstallation of alternative /usr/lib/fglrx/ld.so.conf because link group x86_64-linux-gnu_gl_conf is broken
	update-alternatives: using /usr/lib/fglrx/alt_ld.so.conf to provide /etc/ld.so.conf.d/i386-linux-gnu_GL.conf (i386-linux-gnu_gl_conf) in auto mode
	Processing triggers for ureadahead (0.100.0-16) ...
	ureadahead will be reprofiled on next reboot
	Processing triggers for desktop-file-utils (0.22-1ubuntu1) ...
	Processing triggers for bamfdaemon (0.5.1+14.04.20140409-0ubuntu1) ...
	Rebuilding /usr/share/applications/bamf-2.index...
	Setting up fglrx-amdcccle (2:15.302-0ubuntu1) ...
	Processing triggers for gnome-menus (3.10.1-0ubuntu2) ...
	Processing triggers for mime-support (3.54ubuntu1.1) ...
	Processing triggers for shim-signed (1.18~14.04.1+0.8-0ubuntu2) ...
	Processing triggers for initramfs-tools (0.103ubuntu4.4) ...
	update-initramfs: Generating /boot/initrd.img-4.4.0-34-generic
	Processing triggers for libc-bin (2.19-0ubuntu6.9) ...
	fglrx-core_15.302-0ubuntu1_amd64.deb fglrx_15.302-0ubuntu1_amd64.deb fglrx-amdcccle_15.302-0ubuntu1_amd64.deb
	Removing the generated changes file
	Found fglrx primary device section
	Using /etc/X11/xorg.conf
	Saving back-up to /etc/X11/xorg.conf.fglrx-1
	fglrx_15.302-0ubuntu_.deb
	fglrx-amdcccle_15.302-0ubuntu_.deb
	fglrx-dev_15.302-0ubuntu_.deb
	fglrx-core_15.302-0ubuntu_.deb

# HELP

# version.h

if it is **version.h error** try the below **adjust 4.4.0-34** base on yours kernel use the below to get yours kernel

# check yours kernel version for compatibility 
command

	hostnamectl status

Result

	   Static hostname: Baybucher27-Android
		 Icon name: computer-laptop
		   Chassis: laptop
		   Boot ID: da97acdd4755401ea0228f4b90bef664
	  Operating System: Ubuntu 14.04.5 LTS
		    Kernel: Linux 4.4.0-34-generic
	      Architecture: x86_64

# Command to fix version.h

	sudo ln -s /usr/src/linux-headers-4.4.0-34-generic/include/generated/uapi/linux/version.h /lib/modules/4.4.0-34-generic/build/include/linux/version.h

# how to uninstall

if after the reboot the machine don't start the video, you get only a black screen go to grub advanced and select your kernel in recovery mode

after it load select 

	Drop to root shell prompt

then run the below command

	mount -o remount,rw /
	sudo apt-get remove fglrx-*
	sudo reboot

yours machine must boot ok now, try the web for other way to install amd drivers

# this was build using GCC 4.9 how to use it

a small tutorial on how to setup deferents GCC

add GCC repository

	sudo add-apt-repository ppa:ubuntu-toolchain-r/test
	sudo apt-get update

install gcc/g++

	sudo apt-get install gcc-4.9 g++-4.9

The next step is to add alternatives to **gcc/g++** show installed versions

	ls -lh /usr/bin/gcc* 

and for each of them add alternative, mine are

	sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-4.8 60 --slave /usr/bin/g++ g++ /usr/bin/g++-4.8
	sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-4.9 40 --slave /usr/bin/g++ g++ /usr/bin/g++-4.9
	sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-5 20 --slave /usr/bin/g++ g++ /usr/bin/g++-5

last step is to select what to use

	sudo update-alternatives --config gcc

and select **2** entry in my case

There are 3 choices for the alternative gcc (providing /usr/bin/gcc).

	  Selection    Path              Priority   Status
	------------------------------------------------------------
	  0            /usr/bin/gcc-4.8   60        auto mode
	  1            /usr/bin/gcc-4.8   60        manual mode
	* 2            /usr/bin/gcc-4.9   40        manual mode
	  3            /usr/bin/gcc-5     20        manual mode

There is the possibility some other modules may need **gcc5** or later so...

	sudo apt-get install gcc-5 g++-5

In future update or new modules not related or related to amd try to check GCC version...


In case you are using the latest Amd Driver Download from they web site check this git https://github.com/bhb27/fglrx-15.30.1025
