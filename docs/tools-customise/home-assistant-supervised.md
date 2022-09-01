## This Home Assistant Supervised installation method is for advanced users only

![cover-image](/assets/has-cover.png)

Run the following commands as root (`su -`or `sudo su -`on machines with sudo installed):

If docker is not installed follow that method or you direct skip to below method.

```bash
apt-get install \
jq \
wget \
curl \
udisks2 \
libglib2.0-bin \
network-manager \
dbus -y
```

Install Docker-CE with the following command:

```bash
curl -fsSL get.docker.com | sh
```

---

## Below process for those install `docker` on your Pi 4 already

Run that command to check docker install or not

```bash
docker --version
```

Now run this command help you pick next package which is `os-agent` very important. Before install Home Assistant Supervised.

```bash
uname -m
```

My case is `aarch64` now 

Go to page: https://github.com/home-assistant/os-agent/releases and pick based on your `arch —version`. Right-click and copy url.

![image1](/assets/has-image-1.png)

Now do follow below steps.

```bash
#install package
wget "add url"

#install os-agent
sudo dpkg -i os-agent_1.2.2_linux_aarch64.deb

#this commands to check everything intall proper
gdbus introspect --system --dest io.hass.os --object-path /io/hass/os
```

### Now time to install Home Assistant Supervised

Go to page: https://github.com/home-assistant/supervised-installer/releases

![image2](/assets/has-image-2.png)

Right click on **`homeassistant-supervised` and copy url**

```bash
#install package
wget "add url"

#install homeassistant-supervised
sudo dpkg -install homeassistant-supervised.deb
```

<aside>
ℹ️ Sometime it not work on `first go` do below command
`sudo apt --fix-broken install`

</aside>

Next step is `select machin type` it show you list and pick it. My case is `raspberrypi4-64`

Now just wait to see this If you see on your terminal means done

![image3](/assets/has-image-3.png)

![image4](/assets/has-image-4.png)

<aside>
⚠️ Wait it take 20 min to finish process depending on your internet do not go on rush.

</aside>

Enjoy 🎉

---

Reference links:

[https://www.youtube.com/watch?v=FdzPJ8LhAx4](https://www.youtube.com/watch?v=FdzPJ8LhAx4)

[https://github.com/home-assistant/os-agent](https://github.com/home-assistant/os-agent)

[https://github.com/home-assistant/supervised-installer](https://github.com/home-assistant/supervised-installer)