# Mac OS X 10.11 El Capitan Front-end Dev Setup

## Clean install Mac OS El Capitain (10.11)

* [El Capitan: Prepare the usb key](http://www.macplanete.com/tutoriels/16680/el-capitan-creer-usb-bootable-mac-os-x-10-11)
* [Create a El Capitan with DiskMaker X](http://www.macg.co/os-x/2015/10/creez-une-clef-dinstallation-del-capitan-avec-diskmaker-x-91185)

## Xcode

1. Download Xcode from Appstore
2. Install developer command line tools
```bash
xcode-select --install
```

## Homebrew

1. Install [Homebrew](http://brew.sh)
```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
2. Install [Homebrew extension Cask](http://caskroom.io/)
```bash
brew tap caskroom/cask
```

## ZSH (Prezto)

1. Install [Prezto](https://github.com/sorin-ionescu/prezto)
2. Edit .zpreztorc
```bash
nano ~.zpreztorc
```
3. Change theme to 'steeef'
```bash
# Set the prompt theme to load.
# Setting it to 'random' loads a random theme.
# Auto set to 'off' on dumb terminals.
zstyle ':prezto:module:prompt' theme 'steeef'
```
4. Load git module
```bash
# Set the Prezto modules to load (browse modules).
# The order matters.
zstyle ':prezto:load' pmodule \
  'environment' \
  'terminal' \
  'editor' \
  'history' \
  'directory' \
  'spectrum' \
  'utility' \
  'completion' \
  'git' \
  'prompt'
```