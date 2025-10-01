---
title: Install Node.js the Right Way in M1 & M2 Mac
description: Complete guide for installing Node.js properly on Apple Silicon MacBooks using Homebrew and NVM
icon: apple
---

This guide is specifically for MacBook models M1 and M2 for a new and fresh install.

## Step 1 - Install Homebrew

Link: [https://brew.sh/](https://brew.sh/)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Brew give you another steps (like that) and do every command every steps.

```bash
- Add Homebrew to your PATH in ~/.zprofile:
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Last, `brew doctor` tell you everything if install perfect or there is any issue.

---

## Step 2 - Install Node version Manager aka NVM

```bash
brew install NVM
```

You should create NVM's working directory if it doesn't exist:

```bash
mkdir ~/.nvm
```

Add the following to `~/.zshrc` or your desired shell configuration file:

![Untitled](/docs/assets/nvm-path-min.png)

Last, do `source ~/.zshrc` or restart terminal.

---

## Step 3 - Install Nodejs

Open website nodejs website [nodejs.org](http://nodejs.org/) to check which version you need to install LTS version or Stable. You can change later with NVM manager.

```bash
nvm install 20 (or 21 check number to install)
```

---

## Step 3 - Install NPM

Open website nodejs website [nodejs.org](http://nodejs.org/) to check which version you need to install LTS version or Stable. You can change later with NVM manager.

```bash
brew install npm
```

---

## Tips

Here is other commends which help

```bash
#Some packages are not functioning properly on Macs with M1 or M2 processors.
npm install node-gyp

#switch node version
nvm use (node version 20 or 21)
```

---

Reference link:  
[https://www.youtube.com/watch?v=5jmtF6qpWq8](https://www.youtube.com/watch?v=5jmtF6qpWq8)
