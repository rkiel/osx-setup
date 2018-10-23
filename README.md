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
* [node-utilities](https://github.com/rkiel/node-utilities) for various `node` setup
* [aws-utilities](https://github.com/rkiel/aws-utilities) for various AWS CLI setup
* [atom-setup](https://github.com/rkiel/atom-setup) for `atom` setup
* [vim-setup](https://github.com/rkiel/vim-setup) for `.vimrc` and `vim` plugins
* [images-starter](https://github.com/rkiel/images-starter) collection of starter images for wallpaper and screen saver

## Initial Boot

* [README](INITIAL_BOOT.md)

## User accounts

* administrative user called `admin`
* development user(s) -- one per GitHub account

# Administration user

Remove your Mac from the box. Admire the awesome packaging. Boot your Mac for the first time.

When prompted, create `admin` as the initial user

Install the latest OS X updates.

#### Chrome

* [Download](http://www.google.com/chrome/) and install

#### Xcode

If you are going to build and install MacVim, then you need to install the full Xcode. Go to the App Store to install Xcode.

If you are not going to build and install MacVim, then you only need to install the Xcode command line tools.
Check if the full Xcode package is already installed.

```unix
xcode-select -p
```

If not, you can use a command to install Xcode Command Line Tools. It will produce an alert box.

```unix
xcode-select --install
```

#### Git

* OS X generally has a recent version of `git` already installed.

```
git --version
```

#### Atom

To install Atom, follow the setup guide at [atom-setup](https://github.com/rkiel/atom-setup).

#### Visual Studio Code

To install VS Code, follow the setup guide at [vscode-setup](https://github.com/rkiel/vscode-setup).

#### Spotify

To install, go to [Spotify](https://www.spotify.com/)

#### Basecamp 3

To install, go to [Basecamp](https://www.basecamp.com/)

#### Evernote

Open App Store, search, and install.

#### MacVim

To build and install MacVim, follow the setup guide at [vim-setup](https://github.com/rkiel/vim-setup).

#### VirtualBox

* [Download](https://www.virtualbox.org/wiki/Downloads) VirtualBox 5.x for OS X hosts (x86/amd64)
* Run the installer
* create a VirtualBox-4.x folder in Documents
* copy User Manual and Uninstall Tool into VirtualBox-4.x

#### Vagrant

* [Download](https://www.vagrantup.com/downloads.html) Vagrant 1.x for Mac OS X
* Run the installer
* create a Vagrant-1.x folder in Documents
* copy Uninstall Tool into Vagrant-1.x

#### Images

```
cd /Users/Shared
git clone https://github.com/rkiel/images-starter.git
```

#### Preferences

* [Setup Preferences](PREFERENCES.md)

#### Homebrew

* [Homebrew](http://brew.sh/)
* copy/paste the installation command

```unix
brew doctor
```

#### Node

```unix
brew search node
brew install node@6
brew install yarn
```

If necessary, switch `node` to the LTS version

```unix
cd /usr/local/bin
ln -nfs ../Cellar/node@6/6.9.5/bin/node .
```

#### RVM & Ruby

```unix
brew install gpg
```

# Creating a development user

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
bob     ALL=(ALL) ALL
joe     ALL=(ALL) ALL
```

#### logout

# Development user

#### Preferences

* [Setup Preferences](PREFERENCES.md)

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

#### RVM & Ruby

```unix
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
```

```unix
 \curl -sSL https://get.rvm.io | bash -s stable --autolibs=homebrew
```

```unix
source /Users/rkiel/.rvm/scripts/rvm
```

```unix
rvm autolibs homebrew
rvm list known
rvm install 2.3
```
