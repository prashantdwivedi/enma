# Uptime Kuma install

Last Update August 13, 2022 

---

### Follow below steps:

Fix Time, location and language

```bash
sudo raspi-config
```

1. Go on root

```bash
sudo su

#for exit from root
exit
```

1. Install git

```bash
apt-get install curl git -y
curl -fsSL https://deb.nodesource.com/setup_16.x | bash -
```

1. Install node js

```bash
apt install nodejs
```

1. Verify 

```bash
node --version && npm --version
```

1. Install global npm to install latest version

```bash
npm install -g npm@8.15.0
#or
npm install --local=global npm@latest
```

1. Installer via CLI and follow steps:

```bash
curl -o kuma_install.sh http://git.kuma.pet/install.sh && sudo bash kuma_install.sh
```

Done and returned with that!

![Untitled](assets/images/Untitled.png)

### Some use full commands `pm2`

```bash
# Run at startup (recommended to-do)
pm2 startup
#check-status
pm2 list
#stop
pm2 stop process_name
#delete
pm2 delete process_name
```

---

Reference link:

https://www.atlantic.net/dedicated-server-hosting/how-to-install-uptime-kuma-self-hosted-uptime-robot-alternative-on-ubuntu-20-04/ 

https://www.tutorialspoint.com/how-to-install-git-on-linux

https://www.golinuxcloud.com/install-nodejs-and-npm-on-raspberry-pi/

[https://github.com/louislam/uptime-kuma/wiki/🔧-How-to-Install](https://github.com/louislam/uptime-kuma/wiki/%F0%9F%94%A7-How-to-Install)