# Administration user

## Initial boot create `admin` user
* Install the latest updates

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
* Users & Groups
 * create a **Standard** user for each GitHub account
 * choose **Use separate password**

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

#### MacVim
* "Google Code Overview":http://code.google.com/p/macvim/
* move MacVim into Applications
* move mvim to Desktop
* launch MacVim and authenticate 

```
mkdir -p ~/GitHub/macvim-dev
cd ~/GitHub/macvim-dev
git clone https://github.com/macvim-dev/macvim.git
cd macvim
cd src
./configure --with-features=huge \
            --enable-rubyinterp \
            --enable-pythoninterp \
            --enable-perlinterp \
            --enable-cscope
make
```
* Test it

```
open MacVim/build/Release/MacVim.app
```

* Install 
  * drag `MacVim/build/Release/MacVim.app` into `Applications`

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
    * set **Homepage** to https://take-action.herokuapp.com/bookmarks/home
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

#### Git
* configure global settings for `mygithubid`

```
git config --global user.name "mygithubid"
git config --global user.email foo@bar.com
git config --global color.ui true
git config --global push.default simple
```

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

#### Local Development Environment

```
cd ~
git clone git@github.com:rkiel/local.git
rm .profile
ln -nfs ~/GitHub/rkiel/osx-setup/dotfiles/bash_profile ~/.bash_profile
ln -nfs ~/GitHub/rkiel/osx-setup/dotfiles/bashrc ~/.bashrc
ln -nfs ~/GitHub/rkiel/osx-setup/dotfiles/vimrc ~/.vimrc
ln -nfs ~/GitHub/rkiel/osx-setup/dotfiles/vim ~/.vim
ln -nfs ~/GitHub/rkiel/osx-setup/dotfiles/git-completion.bash ~/.git-completion.bash
mkdir ~/.backup
mkdir ~/bin
ln -nfs ~/GitHub/rkiel/osx-setup/bin/* ~/bin
```
