# macOS Setup - Sierra Edition

# Opinionated Setup

* I want to spend my time doing development not getting my machine configured.
* I tend to have more than one computer.
* I tend to have more than one user account per machine.
* I want an easy way to get everything setup and keep them consistent.

## Tool Stack

* Mac OS X
* `bash`
* `git`
* GitHub
* MacVim
* Chrome
* VirtualBox
* Vagrant

## GitHub repositories

* [osx-setup](https://github.com/rkiel/osx-setup) for step-by-step guide and `bash` setup
* [git-utilities](https://github.com/rkiel/git-utilities) for various `git` setup
* [atom-setup](https://github.com/rkiel/atom-setup) for `atom` setup
* [vim-setup](https://github.com/rkiel/vim-setup) for `.vimrc` and `vim` plugins
* [images-starter](https://github.com/rkiel/images-starter) collection of starter images for wallpaper and screen saver

## Initial Boot

* [README](INITIAL_BOOT.md)

## User accounts

* administrative user called `admin`
* development user(s) -- one per GitHub account

# Administration user

Remove your Mac from the box.  Admire the awesome packaging.  Boot your Mac for the first time.

When prompted, create `admin` as the initial user

Install the latest OS X updates.

#### System Preferences
* Trackpad
  * Point & Click
    * enable **Tap To Click**
    * disable **Secondary Click**
    * diable **Lookup**
    * enable **Three Finger Drag**
  * Scroll & Zoom
    * enable **Scroll direction: natural**
    * enable **Zoom in or out**
    * enable **Smart zoom**
    * enable **Rotate**
  * More Gestures
    * enable **Swipe between pages**
    * enable **Swipe between full-screen apps**
    * enable **Notification Center**
    * enable **Mission Control**
    * enable **App Expose**
    * enable **Launchpad**
    * enable **Show Desktop**
* Mission Control
  * uncheck **Automatically rearrange Spaces based on most recent**
* Bluetooth
  * check **Show Bluetooth in menu bar**
* Dock
  * decrease **Size** to about 20%
  * enable **Magnification**
  * check **Automatically hide and show the Dock**
* Printers & Scanners
  * add a printer and give it a name
* Security & Privacy
  * General
    * check **Require password**
    * select **immediately** after sleep or screen save begins
* Sharing
  * change the **Computer Name**

#### Finder
* Preferences
  * Sidebar
    * Favorites
      * check Applications
      * check Desktop
      * check Documents
      * check Downloads
      * check Home icon (current user name)
    * Devices
      * check Mac icon (current computer name)

#### Mission Control
* F3
  * click **+** (on the far right) to add Desktop 2
  * click **+** (on the far right) to add Desktop 3
  * click **+** (on the far right) to add Desktop 4

#### Safari
* launch (in Applications)
  * F3
    * drag Sarari to Desktop 3
  * hover over the icon in Dock & right click
    * follow **Options**
      * select **Keep in Dock**
      * select **This Desktop**

* Preferences
  * General
    * set **Safari opens with** All windows from last session
    * set **New windows open with** Empty Page
    * set **New tabs open with** Empty Page
    * set **Homepage** to https://www.google.com
  * Advanced
    * check **Show Develop menu in menu bar**
* View
  * Customize Toolbar
    * drag Home button onto Safari navbar between Sidebar and the spacer

#### Chrome
* [Download](http://www.google.com/chrome/) and install
* launch (in Applications)
  * F3
    * drag Chrome to Desktop 1
  * hover over the icon in Dock & right click
    * follow **Options**
      * select **Keep in Dock**
      * select **This Desktop**

#### Terminal
* launch (in Applications)
  * F3
    * drag Terminal to Desktop 4
  * hover over the icon in Dock & right click
    * follow **Options**
      * select **Keep in Dock**
      * select **This Desktop**
* Preferences
  * General
    * select **On startup, open** New window with profile Novel
  * Profile
    * select **Novel**
    * click **Default**
    * Text
      * use **Font** Menlo Regular 14pt
    * Window
      * **Columns** 128
      * **Rows** 24

#### Xcode

* If you are not going to build and install MacVim, then you only need to install the Xcode command line tools.  You can initiate the installation of the command line tools simply by trying to invoke one of them.  For example,

```
gcc --version
```

* If you are going to build and install MacVim, then you need to install the full Xcode.  Go to the App Store to install Xcode.

#### Git

* OS X generally has a recent version of `git` already installed.

```
git --version
```

#### MacVim

To build and install MacVim, follow the setup guide at [vim-setup](https://github.com/rkiel/vim-setup).

* launch (in Applications)
  * F3
    * drag MacVim to Desktop 2
  * hover over the icon in Dock & right click
    * follow **Options**
      * select **Keep in Dock**
      * select **This Desktop**

#### Atom

To install Atom, follow the setup guide at [atom-setup](https://github.com/rkiel/atom-setup).

* launch (in Applications)
  * F3
    * drag Atom to Desktop 2
  * hover over the icon in Dock & right click
    * follow **Options**
      * select **Keep in Dock**
      * select **This Desktop**

#### VirtualBox

* [Download](https://www.virtualbox.org/wiki/Downloads) VirtualBox 4.x for OS X hosts (x86/amd64)
* Run the installer
* create a VirtualBox-4.x folder in Documents
* copy User Manual and Uninstall Tool into VirtualBox-4.x

#### Vagrant

* [Download](https://www.vagrantup.com/downloads.html) Vagrant 1.x for Mac OS X
* Run the installer
* create a Vagrant-1.x folder in Documents
* copy Uninstall Tool into Vagrant-1.x

# Creating a new development user

I create one development user for each GitHub account.

#### System Preferences
* Users & Groups
  * click **+**
    * select **New Account** Standard
    * enter **Full Name** (lower case)
    * enter **Account Name** (lower case)
    * click **Password** Use separate password
    * enter password different from Administration user
    * click **Create User**
  * use Finder to drag an image onto the default user icon

#### sudo

```
sudo vim /private/etc/sudoers
```

* add developer user ids to the Users section

```
# User privilege specification
root    ALL=(ALL) ALL
%admin  ALL=(ALL) ALL
foo     ALL=(ALL) ALL
bar     ALL=(ALL) ALL
```

# Development user

#### System Preferences
* Trackpad
  * Point & Click
    * enable **Tap To Click**
    * disable **Secondary Click**
    * diable **Lookup**
    * enable **Three Finger Drag**
  * Scroll & Zoom
    * enable **Scroll direction: natural**
    * enable **Zoom in or out**
    * enable **Smart zoom**
    * enable **Rotate**
  * More Gestures
    * enable **Swipe between pages**
    * enable **Swipe between full-screen apps**
    * enable **Notification Center**
    * enable **Mission Control**
    * enable **App Expose**
    * enable **Launchpad**
    * enable **Show Desktop**
* Mission Control
  * uncheck **Automatically rearrange Spaces based on most recent**
* Bluetooth
  * check **Show Bluetooth in menu bar**
* Dock
  * decrease **Size** to about 20%
  * enable **Magnification**
  * check **Automatically hide and show the Dock**
* Security & Privacy
  * General
    * check **Require password**
    * select **immediately** after sleep or screen save begins

#### Finder
* Preferences
  * Sidebar
    * Favorites
      * check Applications
      * check Desktop
      * check Documents
      * check Downloads
      * check Home icon (current user name)
    * Devices
      * check Mac icon (current computer name)

#### Mission Control
* F3
  * click **+** (on the far right) to add Desktop 2
  * click **+** (on the far right) to add Desktop 3
  * click **+** (on the far right) to add Desktop 4

#### Safari
* launch (in Applications)
  * F3
    * drag Sarari to Desktop 3
  * hover over the icon in Dock & right click
    * follow **Options**
      * select **Keep in Dock**
      * select **This Desktop**

* Preferences
  * General
    * set **Safari opens with** All windows from last session
    * set **New windows open with** Empty Page
    * set **New tabs open with** Empty Page
    * set **Homepage** to https://www.google.com
  * Advanced
    * check **Show Develop menu in menu bar**
* View
  * Customize Toolbar
    * drag Home button onto Safari navbar between Sidebar and the spacer

#### Chrome
* launch (in Applications)
  * F3
    * drag Chrome to Desktop 1
  * hover over the icon in Dock & right click
    * follow **Options**
      * select **Keep in Dock**
      * select **This Desktop**

#### Terminal
* launch (in Applications)
  * F3
    * drag Terminal to Desktop 4
  * hover over the icon in Dock & right click
    * follow **Options**
      * select **Keep in Dock**
      * select **This Desktop**
* Preferences
  * General
    * select **On startup, open** New window with profile Novel
  * Profile
    * select **Novel**
    * click **Default**
    * Text
      * use **Font** Menlo Regular 14pt
    * Window
      * **Columns** 128
      * **Rows** 24

#### SSH

create public/private keys with a passphrase
```
ssh-keygen -t rsa -C "foo@bar.com"
```

verify you can read your private key
```
openssl rsa -noout -text -in ~/.ssh/id_rsa
```

add credentials to the authentication agent and Key Chain
```
ssh-add -K
```

copy public key into paste buffer
```
cat ~/.ssh/id_rsa.pub | pbcopy
```


#### GitHub
* Setting
  * SSH Keys
    * click **Add SSH Key**
    * enter computer name as **Title**
    * paste in **Key**
    * click **Add key**

#### Git

* configure global settings for `mygithubid`

```
git config --global user.name "mygithubid"
git config --global user.email foo@bar.com
git config --global color.ui true
git config --global push.default simple
```

Download a GitHub repository

```
mkdir -p ~/GitHub/rkiel
cd ~/GitHub/rkiel

git clone git@github.com:rkiel/git-utilities.git
```

#### MacVim

Download a GitHub repository

```
mkdir -p ~/GitHub/rkiel
cd ~/GitHub/rkiel

git clone git@github.com:rkiel/vim-setup.git
```

To configure MacVim, follow the **Local Environment** setup guide at [vim-setup](https://github.com/rkiel/vim-setup).

* launch (in Applications)
  * F3
    * drag MacVim to Desktop 2
  * hover over the icon in Dock & right click
    * follow **Options**
      * select **Keep in Dock**
      * select **This Desktop**

#### Atom

To configure Atom, follow the **Configuration** setup guide at [atom-setup](https://github.com/rkiel/atom-setup).

* launch (in Applications)
  * F3
    * drag Atom to Desktop 2
  * hover over the icon in Dock & right click
    * follow **Options**
      * select **Keep in Dock**
      * select **This Desktop**

#### Bash

Create local bin directory

```
mkdir ~/bin
```

Download a GitHub repository

```
mkdir -p ~/GitHub/rkiel
cd ~/GitHub/rkiel

git clone git@github.com:rkiel/osx-setup.git
```

Setup dot files

```
ln -nfs ~/GitHub/rkiel/osx-setup/dotfiles/bash_profile ~/.bash_profile
ln -nfs ~/GitHub/rkiel/osx-setup/dotfiles/bashrc ~/.bashrc
```

#### Images

Go to the shared user and download the starter wallpaper and screen saver images

```
cd /Users/Shared
git clone git@github.com:rkiel/images-starter.git
```

#### System Preferences
* Desktop & Screen Saver
  * Desktop
    * select **Fill Screen**
    * click **+** to add a folder under `/Users/Shared/images-starter`
    * check **Change picture:** Every 5 minutes
    * check **Random order**
  * Screen Saver
    * select **Classic**
    * choose **Source:** Choose Folder
    * pick a folder under `/Users/Shared/images-starter`
    * check **Shuffle slide order**
    * select **Start after** 5 Minutes
    * click **Hot Corners** and select **Start Screen Saver** for lower left and right
