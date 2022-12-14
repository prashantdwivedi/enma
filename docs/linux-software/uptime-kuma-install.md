### Follow the below steps:

Fix Time, location, and language

```bash
sudo raspi-config
```

1- Go on root

```bash
sudo su
#for exit from root
exit
```

2- Install git

```bash
apt-get install curl git -y
curl -fsSL https://deb.nodesource.com/setup_16.x | bash -
```

3- Install node js

```bash
apt install nodejs
```

4- Verify 

```bash
node --version && npm --version
```

5- Install global npm to install the latest version

```bash
npm install --local=global npm@latest
```

6- Installer via CLI and follow the steps:

```bash
curl -o kuma_install.sh http://git.kuma.pet/install.sh && sudo bash kuma_install.sh
```

Done and returned with that!

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

### Update or upgrade

```bash
#default path  
cd /opt/uptime-kuma

# or if you changed path during installation
cd <uptime-kuma-directory>

# Update from git
git fetch --all
git checkout 1.18.0 --force

# Install dependencies and prebuilt
npm install --production
npm run download-dist

# Restart
pm2 restart uptime-kuma
```

---

**Reference link:**

[https://www.atlantic.net/dedicated-server-hosting/how-to-install-uptime-kuma-self-hosted-uptime-robot-alternative-on-ubuntu-20-04/](https://www.atlantic.net/dedicated-server-hosting/how-to-install-uptime-kuma-self-hosted-uptime-robot-alternative-on-ubuntu-20-04/)

[https://www.tutorialspoint.com/how-to-install-git-on-linux](https://www.tutorialspoint.com/how-to-install-git-on-linux)

[https://www.golinuxcloud.com/install-nodejs-and-npm-on-raspberry-pi/](https://www.golinuxcloud.com/install-nodejs-and-npm-on-raspberry-pi/)

[https://github.com/louislam/uptime-kuma/wiki/🔧-How-to-Install](https://github.com/louislam/uptime-kuma/wiki/🔧-How-to-Install)
