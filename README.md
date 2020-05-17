# macOS Catalina (10.15.4) Front-end Dev Setup

This guide represents the different steps to configure my new Mac for front-end development.

## Installation de macOS Catalina

1. Télécharger macOS.
2. [Créer une clé d'installation](https://support.apple.com/fr-fr/HT201372)
 * Connecter une clé USB d'au moins 12Go au format macOS étendu.
 * Ouvrir le terminal et entrer la commande suivante (pour Catalina) :
 ```bash
sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
 ```
4. Suivre les instructions
3. Insérer la clé USB et démarrer avec la touche `alt` enfoncée pour choisir le volume de démarrage

## Préparation initiale

* Connexion au wifi
* Supprimer les applications inutiles du Dock : Mail, FaceTime, Messages, Plans, Photos, Contacts, Calendrier, Rappels, iTunes, Podcasts, TV

## Préférences Système

* Moniteurs > Résolution : à l’échelle > Plus d'espace
* Trackpad > Toucher pour cliquer
* Accessibilité > Contrôle du pointeur > Options du trackpad > Activer le glissement > faire glisser avec 3 doigts
* Connectez-vous à votre identifiant Apple
* Spotlight > Raccourcis clavier… > décocher Afficher la recherche Spotlight

## Préférences Finder

* Barre latérale :
	* Décocher des Favoris : AirDrop
	* Cocher dans les Favoris : Vidéos, Musique, Images, Utilisateur
	* iCloud : décocher
* Présentation :
	* Afficher la barre du chemin d'accès
	* Afficher la barre d'état

## Xcode

1. Télécharger Xcode depuis l'Appstore
2. Installer les outils en ligne de commande
  
  ```bash
  xcode-select --install
  ```
3. Lancer Xcode and accepter le contrat de licence

## ZSH/Prezto

...

## Homebrew

...

## Git

...

## SSH

...

## node.js (via nvm)

[Node Version Manager](https://github.com/nvm-sh/nvm) (nvm) permet de gérer plusieurs versions de node.js.

L'installation avec Homebrew n'est pas supporté par nvm.

...

## Docker

...

## Logiciels

### App Store (macOS)

* [WhatsApp Desktop](https://apps.apple.com/fr/app/whatsapp-desktop/id1147396723)
* [Telegram](https://apps.apple.com/fr/app/telegram/id747648890?mt=12)
* [Lightshot Screenshot](https://apps.apple.com/fr/app/lightshot-screenshot/id526298438?mt=12)
* [Slack](https://apps.apple.com/fr/app/slack/id803453959?mt=12)
* [Evernote](https://apps.apple.com/fr/app/evernote/id406056744?mt=12)


### Autres

* Utilitaires :
	* [Alfred](https://www.alfredapp.com/) : Productivity App for macOS
	* [Spectacle](https://www.spectacleapp.com/) : Move and resize windows with ease
	* [iTerm2 Version 3](https://www.iterm2.com/version3.html) : terminal emulator for macOS
* Navigateurs :
	* [Chrome](https://www.google.fr/chrome/)
	* [Firefox](https://www.mozilla.org/fr/firefox/)
* Communication :
	* [Skype](https://www.skype.com/fr/)