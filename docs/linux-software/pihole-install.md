---
title: Pi-hole Install
description: Set up Pi-hole for network-wide ad blocking via your own Linux hardware
icon: shield
---

Network-wide ad blocking via your own Linux hardware

The Pi-hole is a [DNS sinkhole](https://en.wikipedia.org/wiki/DNS_Sinkhole) that protects your devices from unwanted content without installing any client-side software. Follow below steps:

### One-Step Automated Install

Those who want to get started quickly and conveniently may install Pi-hole using the following command:

```bash
sudo curl -sSL https://install.pi-hole.net | sudo bash
```

### Alternative Install Methods

Method 1: Clone our repository and run

```bash
git clone --depth 1 https://github.com/pi-hole/pi-hole.git Pi-hole
cd "Pi-hole/automated install/"
sudo bash basic-install.sh
```

Method 2: Manually download the installer and run

```bash
wget -O basic-install.sh https://install.pi-hole.net
sudo bash basic-install.sh
```

---

Reference link:

[https://youtu.be/UE2sO8d3sx8](https://youtu.be/UE2sO8d3sx8)

[https://github.com/pi-hole/pi-hole/](https://github.com/pi-hole/pi-hole/)
