# Electron-Workshop
Small Work shop about Electron

## Contents

- [Installation](#installation)
- [Boilerplates](#boilerplates)
- [Components](#components)
- [Config](#config)
- [Bug](#bug)


## Installation


**Electron**
---
##### Clone this repository
>git clone https://github.com/csepulv/electron-with-create-react-app.git
#### Go into the repository
>cd electron-with-create-react-app
#### Install dependencies
>npm install
#### Run the preview
>npm start
#### Run the app
>npm electron

**Electron api demo**
---
#### Clone this repository
>git clone https://github.com/electron/electron-api-demos
#### Go into the repository
>cd electron-api-demos
#### Install dependencies
>npm install
##### Run the app
>npm start

### Config

**In package.json add these script**

- package mac
> "package-mac": "electron-packager . --overwrite --asar=true --platform=darwin --arch=x64 --icon=assets/icons/mac/icon.icns --prune=true --out=release-builds --darwinDarkModeSupport=true",
- package windows    
> "package-win": "electron-packager . electron-tutorial-app --overwrite --asar=true --platform=win32 --arch=ia32 --icon=assets/icons/win/icon.ico --prune=true --out=release-builds --version-string.CompanyName=CE --version-string.FileDescription=CE --version-string.ProductName=\"Electron Tutorial App\"",
 - package linux
 > "package-linux": "electron-packager . electron-tutorial-app --overwrite --asar=true --platform=linux --arch=x64 --icon=assets/icons/png/1024x1024.png --prune=true --out=release-builds",
 
   `Optionnal`
   
> "create-installer-mac": "electron-installer-dmg ./release-builds/Electron\\ tutorial\\ app-darwin-x64/Electron\\ tutorial\\ app.app electron-tutorial-app --out=release-builds --overwrite --icon=assets/icons/mac/icon.icns",

> "create-installer-win": "node installers/windows/createinstaller.js",
    
> "create-debian-installer": "electron-installer-debian --src release-builds/electron-tutorial-app-linux-x64/ --arch amd64 --config debian.json"


**Don't forget, if you want to see the modification in the app of the css style, you need to build it before**

> "build": "react-scripts build",



#### Package the app
> npm run "package-win" or "package-mac" or "package-linux"


## Boilerplates

- [electron-boilerplate](https://github.com/sindresorhus/electron-boilerplate) - Boilerplate to kickstart creating an app - by [sindresorhus](http://github.com/sindresorhus).
- [generator-electron](https://github.com/sindresorhus/generator-electron) - Scaffold out an app boilerplate.
- [electron-boilerplate](https://github.com/szwacz/electron-boilerplate) - Comprehensive boilerplate which even generates installers - by [szwacz](https://github.com/szwacz).
- [electron-react-boilerplate](https://github.com/chentsulin/electron-react-boilerplate) - Boilerplate based on React and webpack.
- [descjop](https://github.com/karad/lein_template_descjop) - ClojureScript boilerplate for creating an app.
- [electron-quick-start](https://github.com/electron/electron-quick-start) - Clone the repo to try a simple app.
- [bozon](https://github.com/railsware/bozon) - Scaffold, run, test, and package your app.
- [electron-vue](https://github.com/SimulatedGREG/electron-vue) - Easily build your app with Vue and common plugins.
- [electron-next-skeleton](https://github.com/leo/electron-next-skeleton) - Boilerplate to build your app with Next.js.
- [electron-sandbox](https://github.com/kewde/electron-sandbox) - Boilerplate and tutorial for creating secure apps (sandbox & communication over IPC).
- [angular-electron](https://github.com/maximegris/angular-electron) - Angular 5, Electron, TypeScript, SASS, Hot Reload.


## Components

- [Photon](http://photonkit.com) - UI toolkit for building beautiful apps.
- [React PhotonKit](https://github.com/react-photonkit/react-photonkit) - Photon components built with React.
- [menubar](https://github.com/maxogden/menubar) - Menubar app framework.
- [cookies](https://github.com/hstove/electron-cookies) - Adds support for `document.cookie`.
- [window](https://github.com/jprichardson/electron-window) - Create and manage windows.
- [React Desktop](https://github.com/gabrielbull/react-desktop) - UI toolkit for macOS and Windows built with React.
- [electron-input-menu](https://github.com/parro-it/electron-input-menu) - Context menu for input elements.
- [chrome-tabs](https://github.com/adamschwartz/chrome-tabs) - Chrome like tabs.
- [titlebar](https://github.com/kapetan/titlebar) - Emulate the macOS window titlebar.
- [Brightwheel](https://github.com/loranallensmith/brightwheel) - Build and manage UI components with Photon and Etch.
- [Xel](https://xel-toolkit.org) - Widget toolkit for building native-like apps.

## Awesome Electron 

> https://github.com/sindresorhus/awesome-electron#components

## Tuto Electron

> https://www.christianengvall.se/category/electron/

## Here is somes exemple of what you can do whit Electron

> https://electronjs.org/apps

## Tips

- Sudo on cmd Windows

>https://www.parlonsgeek.com/sudo-sous-windows/



# Bug 
---

*Have you install Electron ?*

> npm install --save-dev electron 

**Have you install Electron-packager ?*

for use in npm scripts
> npm install electron-packager --save-dev

for use from cli
> npm install electron-packager -g

**You need to build before run electron**
> npm run build

and then 

> npm start

**rcedit.exe failed with exit code 193. wine: Bad EXE format**

> sudo dpkg --add-architecture i386 && sudo apt-get update && sudo apt-get install wine32

**Error: EACCES: permission denied, mkdir '/usr/local/lib/node_modules/electron/.electron' **

> sudo npm install -g electron --unsafe-perm=true --allow-root

**(electron:3541): Gtk-WARNING **: 12:29:39.100: cannot open display:**

> Add : "start": "electron ."  in script, in your package.json

**If the package-win script doesn't work, try this:**

> Delete folder "ansi-html" in node-modules

**If Some script, commande is missing or not found**

> Try to delete and re install the node module folder : "sudo rm -rf node_modules && sudo npm i --save" 
and don't forget the"sudo audit fix"
> Or if it's the electron-packager : npm install electron-packager --save

**Npm start for web preview doesn't work ?**

> Remplace the start script whit this : "node node_modules/react-scripts/scripts/start.js"

**You need to close the app before package it again**
