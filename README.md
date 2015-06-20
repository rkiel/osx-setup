# Administration user

## Initial boot create `admin` user
* Install the latest updates

#### Finder
* Preferences
  * Sidebar
    * add Home (current user name)
    * add Mac (current computer name)

#### Preferences
* Dock
  * decrease **Size**
  * enable **Magnification**
  * check **Automatically hide and show the Dock**
* Printers & Scanners
  * add a printer and give it a name
* Security & Privacy
  * General
    * make sure **Require password** is set
* Sharing
  * change the **Computer Name**
* Trackpad
  * enable **Tap To Click**
  * enable **Three Finger Drag**
  * enable **All More Gestures**
  * disable **Secondary Click**
  * diable **Lookup**

#### Chrome
* [Download](http://www.google.com/chrome/)
* Launch
  * Dock -> Right click -> Options -> select **Keep in Dock**

#### Terminal
* Launch
  * Dock -> Right click -> Options -> select **Keep in Dock**
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
* okay, i guess i have to install this so i can build MacVim

#### Xcode command line tools
* use the following command to initiate the installation of the command line tools

```
gcc --version
```

#### Git
* Verify that a recent version of `git` was installed.

```
git --version
```

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

# Creating a new user

#### Preferences
* Users & Groups
  * click **+**
    * select **New Account** Standard
    * enter **Full Name** (lower case)
    * enter **Account Name** (lower case)
    * click **Password** Use separate password
    * enter password different from Administration user
    * click **Create User**
  * use Finder to drag an image onto the default user icon

# Development user

#### Finder
* Preferences
  * Sidebar
    * add Home (current user name)
    * add Mac (current computer name)

#### Preferences
* Desktop & Screen Saver
  * Desktop
    * choose picture
  * Screen Saver
    * choose **Classic**
    * choose shared folder
    * check **Shuffle slide order**
    * change **Start after** to 5 min
    * edit **Hot Corners** to Start Screen Saver
* Dock
  * decrease **Size**
  * enable **Magnification**
  * check **Automatically hide and show the Dock**
* Security & Privacy
  * General
    * make sure **Require password** is set
* Trackpad
  * enable **Tap To Click**
  * enable **Three Finger Drag**
  * enable **All More Gestures**
  * disable **Secondary Click**
  * diable **Lookup**

#### Safari
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
    * drag Home button

#### Chrome
* Launch
  * Dock -> Right click -> Options -> select **Keep in Dock**
 
#### Backblaze

#### Terminal
* Launch
  * Dock -> Right click -> Options -> select **Keep in Dock**
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

* create public/private keys with a passphrase
* verify you can read your private key
* copy public key into paste buffer
* add credentials to the authentication agent and Key Chain

```
ssh-keygen -t rsa -C "foo@bar.com"
openssl rsa -noout -text -in ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub | pbcopy
ssh-add -K
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

#### Vim

Create a backup directory

```
mkdir ~/.backup
```

Download a GitHub repository

```
mkdir -p ~/GitHub/rkiel
cd ~/GitHub/rkiel

git clone git@github.com:rkiel/vim-setup.git
```

Setup dot files

```
ln -nfs ~/GitHub/rkiel/vim-setup/dotfiles/vimrc ~/.vimrc
ln -nfs ~/GitHub/rkiel/vim-setup/dotfiles/vim ~/.vim
```
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

#### Preferences
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
