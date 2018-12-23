Getting Started
---------------

To get started with Android, you'll need to get
familiar with [Git and Repo](http://source.android.com/source/using-repo.html).

To initialize your local repository using theese trees, use a command like this:

    repo init -u git://github.com/derCo0n/android.git -b aosp-8.1

Then to sync up:

    repo sync
    
    
    
Example:
--------
1. Setting Up Environment 

```
sudo apt-get install openjdk-8-jdk 
sudo apt-get update && sudo apt-get install git-core gnupg flex bison gperf libsdl1.2-dev libesd0-dev libwxgtk2.8-dev squashfs-tools build-essential zip curl libncurses5-dev zlib1g-dev openjdk-8-jre openjdk-8-jdk pngcrush schedtool libxml2 libxml2-utils xsltproc lzop libc6-dev schedtool g++-multilib lib32z1-dev lib32ncurses5-dev lib32readline-gplv2-dev gcc-multilib maven tmux screen w3m ncftp 
```

2. Initializing Repo

```
mkdir ~/bin 
PATH=~/bin:$PATH (oder PATH=/media/co0n/7a59f274-2a0c-4233-a4bf-03233b45a7e9/android-builds/bin:$PATH)
curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo 
chmod a+x ~/bin/repo 
```

3. Make Folders 

```
mkdir unlegacyandroid_8.1
cd unlegacyandroid_8.1 
```

4. Initialize ROM REPO 

```
repo init -u git://github.com/derCo0n/android.git -b aosp-8.1
```

5. Sync Repository
```
repo sync
```

6. Build your ROM
```
source build/envsetup.sh 
breakfast espresso
./extract-files.sh 
export USE_CCACHE=1 
export LC_ALL=C  # needed under Ubuntu 18.04 / Linux Mint 19 or newer
prebuilts/misc/linux-x86/ccache/ccache -M 50G 
croot 
brunch espresso

```
