This is a fork of Unlegacy-Android which aims to bring new life to old android devices.

I own a Samsung Galaxy Tab 2 released in 2012, and i refuse to throw it away just because of old software.
At this point: many thanks to the original project. :)

This fork uses a slightly modded Kernel for the Galaxy Tab 2 which overclocks its CPU from original 1008 MHz to 1350 MHz, which makes the device even more useable.


Getting Started
---------------
Basic requirements:
- some time
- A computer with
  - some CPU-Cores (the more the better)
  - enough RAM (the more the better, i'm fine with 16 GB), 
  - a lot of free disk space (repository will use up to 200 GB)
  - a linux environment (as main OS or in a VM)
- knowledge about linux and the command line
- an unlimitied fast internet access.
- you'll need to get familiar with [Git and Repo](http://source.android.com/source/using-repo.html).

To initialize your local repository using theese trees, use a command like this:

    repo init -u git://github.com/derCo0n/android.git -b aosp-7.1

Then to sync up:

    repo sync
    
    
    
Example for device espresso (Samsung Galaxy Tab 2):
---------------------------------------------------
1. Setting Up Environment
```
sudo apt-get install openjdk-8-jdk 
sudo apt-get update && sudo apt-get install git-core gnupg flex bison gperf libsdl1.2-dev libesd0-dev libwxgtk2.8-dev squashfs-tools build-essential zip curl libncurses5-dev zlib1g-dev openjdk-8-jre openjdk-8-jdk pngcrush schedtool libxml2 libxml2-utils xsltproc lzop libc6-dev schedtool g++-multilib lib32z1-dev lib32ncurses5-dev lib32readline-gplv2-dev gcc-multilib maven tmux screen w3m ncftp 
```

2. Initializing Repo
```
mkdir ~/bin 
PATH=~/bin:$PATH
curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo 
chmod a+x ~/bin/repo 
```

3. Make Folders
```
mkdir unlegacyandroid_7.1
cd unlegacyandroid_7.1 
```

4. Initialize ROM REPO
```
repo init -u git://github.com/derCo0n/android.git -b aosp-7.1
```

5. Sync Repository
```
repo sync
```
grab a coffee or two and wait for it to finish...

6. Build your ROM
```
source build/envsetup.sh 
breakfast espresso # or other devicename of your choice
./extract-files.sh 
export USE_CCACHE=1 
export LC_ALL=C  # needed under Ubuntu 18.04 / Linux Mint 19 or newer
prebuilts/misc/linux-x86/ccache/ccache -M 50G 
croot 
brunch espresso # or other devicename of your choice
```
grab some more coffee's and wait for it to finish...this can take some time depending on your CPU, Cache, RAM and Storage capabilities.

7. Flash your new ROM
- via custom recovery like TWRP

8. Flash other things (GAPPS, MAgisk, etc. ) as you like

9. Don't forget to wipe your DALVIK/cache
