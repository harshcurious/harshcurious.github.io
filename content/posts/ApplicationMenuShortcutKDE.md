---
title: 'Application Menu Shortcut KDE'
date: 2022-02-14T14:22:58+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ['KDE', 'shortcut', 'terminal']
author: 'Harsh Kumar'
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: 'Learning how to create application menu shortcut in KDE Linux.'

disableShare: false
# to disable highlightjs
disableHLJS: false
searchHidden: false
cover:
  image: '<image path/url>' # image path/url
  alt: '<alt text>' # alt text
  caption: '<text>' # display caption under cover
  relative: false # when using page bundles set this to true
  hidden: true # only hide on current single page

plotly: false #turn plotly support on and off
mathjax: false #turn mathjax support on and off
---

## Option 1: GUI

Right click on the app launcher and select `Edit Applications` from the menu. This should launch a menu editor. Make the desired edits and save them.

## Option 2: Terminal

The menu applications are stored in `/usr/share/applications/`. If you want to make an edit to an existing application, edit the file: `application_NAME.desktop`. You can search for it using: `ls | grep 'search_term'`.[^ripgep] Don't forget to use **sudo** for editing the file.

If you want to add a new application, create a new `.desktop` file:

```sh
cd /usr/share/applications/
sudo touch program-shortcut.desktop
sudo chmod +x program-shortcut.desktop
sudo nano program-shortcut.desktop
```

Edit the `.desktop` file by adding the following

```sh
[Desktop Entry]
Name=Display Name
GenericName=Monitor Settings
Comment=Add a description and other words to improve searchability
Exec=/path/to/bin
Icon=/path/to/icon
Terminal=false #to start a terminal or not
Type=Application
Categories=GTK;Settings;HardwareSettings;
```

Note that you can run python programs using `Exec=python /path/to/python/app`. Similarly, for other languages!

[^ripgrep]: You can also use `rg` for ripgrep if you have that installed.
