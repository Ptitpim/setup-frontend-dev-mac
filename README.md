# Mac OS X 10.11 El Capitan Front-end Dev Setup

This guide represents the different steps to configure my new Mac for front-end development.

I install ZSH, utilities, command line tools and upgrade tools like git and php to have the latest versions.

## Clean install Mac OS El Capitain (10.11)

* [El Capitan: Prepare the usb key](http://www.macplanete.com/tutoriels/16680/el-capitan-creer-usb-bootable-mac-os-x-10-11)
* [Create a El Capitan with DiskMaker X](http://www.macg.co/os-x/2015/10/creez-une-clef-dinstallation-del-capitan-avec-diskmaker-x-91185)

## Xcode

1. Download Xcode from Appstore
2. Install developer command line tools
  
  ```bash
  xcode-select --install
  ```
3. Launch Xcode and agree license

## Homebrew

1. Install [Homebrew](http://brew.sh)

  ```bash
  ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  ```
2. Install [Homebrew extension Cask](http://caskroom.io/)

  ```bash
  brew tap caskroom/cask
  ```

## Utilities

You can use Brew Cask to install them if you prefer.

* [iTerm 2](https://www.iterm2.com/)
* [Sublime Text 3](http://www.sublimetext.com/3)
* [Sublime Text 3 Package Control](https://packagecontrol.io/installation)
* [Spectacle](https://www.spectacleapp.com)
* [Alfred](https://www.alfredapp.com)
* [Dropbox](https://www.dropbox.com/fr)
* [Google Drive](https://www.google.fr/intl/fr/drive/download/)

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
5. Edit ~/.zshrc

  ```bash
  nano ~/.zshrc
  ```
6. Add Sublime text Alias

  ```bash
  # Sublime Text Alias
  alias s='open -a "Sublime Text"'
  export EDITOR="s -n -w"
  ```
7. Now you can open file or folder with Sublime Text 3 from terminal

  ```bash
  s ~/.zshrc
  ```

## Git (latest version) & Git-flow

Git is pre-installed on Mac OS X, but I want the latest version.

1. Install Git and Git-flow

  ```bash
  brew install git git-flow
  ```
2. Configure global name and email:

  ```
  git config --global user.name "Your Name Here"
  git config --global user.email "your_email@youremail.com"
  ```
3. Configure .gitignore_global

  ```
  touch .gitignore_global
  ```

  Edit the file

  ```
  .DS_Store
  .Trashes
  .Spotlight_V100
  ```

  Add to gitconfig

  ```
  git config --global core.excludesfile ~/.gitignore_global
  ```

## Github

* [Generating an SSH key](https://help.github.com/articles/generating-an-ssh-key/)
* [Changing a remote's URL](https://help.github.com/articles/changing-a-remote-s-url/)

## SSH

When generating an SSH key, you'll need to [add your newly created (or existing) SSH key to the ssh-agent](https://help.github.com/articles/adding-a-new-ssh-key-to-the-ssh-agent/).

```bash
ssh-add ~/.ssh/id_rsa
```

or enable [SSH module](https://github.com/sorin-ionescu/prezto/tree/master/modules/ssh) for Prezto:

* Edit `.zpreztorc` file and add `ssh` module

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
    'ssh' \
    'prompt'
  ```

* Add multiple entities

  ```bash
  zstyle ':prezto:module:ssh:load' identities 'id_rsa' 'id_dsa' 'id_github'
  ```

* It seem it doesn't work, OS X ask password after reboot when I use git command. Instead I store the key in the keychain:

  ```bash
  ssh-add -K [path/to/private SSH key]
  ```

By creating a [local configuration file for SSH](https://mediatemple.net/community/products/grid/204644730/using-an-ssh-config-file), you can create shortcuts for servers you frequently access, in addition to configuring more advanced options

* Create config file:

  ```bash
  touch ~/.ssh/config
  ```
* Edit the file:
  
  ```bash
  s ~/.ssh/config
  ```
* Add config:
  
  ```bash
  Host dev
    Hostname dv.example.com
    IdentityFile ~/.ssh/mykey_rsa
  ```

## Node.js

```bash
brew install node
```

## Vagrant

```bash
brew cask install vagrant
brew cask install vagrant-manager
brew cask install virtualbox
```

## Front-end command line tools

* Bower, Gulp and Grunt-CLI

  ```bash
  npm install -g bower
  npm install -g gulp
  npm install -g grunt-cli
  ```

  List installed modules with

  ```bash
  npm list -g --depth=0
  ```

* SASS

  ```bash
  sudo gem install sass
  ```

## Sublime Text 3

### Install Sublime Text 3 packages (cmd+shift+p)

* Alignment
* ApacheConf
* Backbone.js
* BracketHighlighter
* Comment-Snippets
* CSS Format
* DocBlockr
* Dotfiles Syntax Highlighting
* Drupal
* EditorConfig
* Emmet
* GitGutter
* Handlebars
* HTML5
* Indent XML
* JsFormat
* LESS
* Sass
* SCSS
* SideBarEnhancements
* Theme - Spacegray
* Underscorejs
* Virtual Host Snippet

### Configure Sublime Text 3 User settings

```json
{
  "auto_complete_selector": "source - comment, meta.tag - punctuation.definition.tag.begin",
  "auto_complete_triggers":
  [
    {
      "characters": "ng-controller=\"*",
      "selector": "punctuation.definition.string"
    }
  ],
  "bold_folder_labels": true,
  "color_scheme": "Packages/Theme - Spacegray/base16-eighties.dark.tmTheme",
  "draw_white_space": "all",
  "fade_fold_buttons": false,
  "font_size": 14.0,
  "highlight_line": true,
  "ignored_packages":
  [
    "SublimeLinter",
    "Vintage"
  ],
  "indent_guide_options":
  [
    "draw_normal",
    "draw_active"
  ],
  "tab_size": 2,
  "theme": "Spacegray Eighties.sublime-theme",
  "translate_tabs_to_spaces": true,
  "world_wrap": true
}
```

## Apache

* [Get Apache, MySQL, PHP and phpMyAdmin working on OSX 10.11 El Capitan](http://coolestguidesontheplanet.com/get-apache-mysql-php-and-phpmyadmin-working-on-osx-10-11-el-capitan/)
* Create logs alias:

  ```bash
  cd ~/Documents
  mkdir logs
  cd logs
  mkdir apache2
  cd apache2
  ln -s /var/log/apache2/access_log access_log
  ln -s /var/log/apache2/error_log error_log
  ```

## PHP

* [Upgrade PHP version to 5.6 or 7](http://coolestguidesontheplanet.com/upgrade-php-on-osx/)

  ```bash
  curl -s http://php-osx.liip.ch/install.sh | bash -s 5.6
  ```
* Update php command line version (php -v)

  Edit .zprofile file

  ```bash
  s ~/.zprofile
  ```
  Add path:

  ```bash
  # Set the list of directories that Zsh searches for programs.
  path=(
    /usr/local/{bin,sbin}
    /usr/local/php5/bin
    $path
  )
  ```

## MySQL

```bash
brew install mysql
```