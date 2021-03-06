JOSP Source
============
To get started with JOSP ROM, you'll need to get familiar with Git and Repo.

Part 1 Setting up Bashrc
==========================

sudo gedit ~/.bashrc

Add this at the very bottom of the file

export PATH=${PATH}:~/bin

Save, then exit

Part 2 - Setting Up The Build Environment
===========================================

Install Java JDK

sudo add-apt-repository ppa:webupd8team/java

sudo apt-get update

sudo apt-get install oracle-java6-installer
============================================

Installing required packages

sudo apt-get install git gnupg flex bison gperf build-essential \
  zip curl libc6-dev libncurses5-dev:i386 x11proto-core-dev \
  libx11-dev:i386 libreadline6-dev:i386 \
  libgl1-mesa-dev g++-multilib mingw32 tofrodos \
  python-markdown libxml2-utils xsltproc zlib1g-dev:i386

Setup Repo
============

mkdir -p ~/bin

PATH=~/bin:$PATH

Enter the following to download the "repo"

curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo

chmod a+x ~/bin/repo

Create working directory

mkdir ~/jtosp

cd ~/jtosp

JTOSP Source
=============

repo init -u git://github.com/JTOSP/android.git -b lp5.0

repo sync
Time To start the process

Step 3 Extract Proprietary Blobs
==================================

You will need to download a ROM.zip for your device
Then make a folder on your home directory, rename it to original, then extract the ROM zip to that folder
now go on terminal and type the following code with your device name.
cd ~/jtosp/device/manifacturer/your device code

./extract-files.sh ~/original

source build/envsetup.sh

"breakfast" your device code name

export USE_CCACHE=1

croot

Build the Code:
================

"brunch" your device code name

NOTE:if you get error: Exited sync due to fetch errors

Simply re-run repo again with repo sync -f -j10
