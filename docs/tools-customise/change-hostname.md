The hostname of a Linux system is important because it’s used to identify the device on a network. The hostname is also shown in other prominent places, such as in the terminal prompt. This gives you a constant reminder of which system you’re working with. It’s a real-life saver when you’re managing multiple systems through SSH and those command line terminals start to blend together in your mind.

First, let’s check the current hostname by using either the `hostname` or `hostnamectl` command.

Next, change the hostname with the following command.

```bash
sudo hostnamectl set-hostname "newName"
```

Lastly, edit the `/etc/hosts` file to reflect the change.

```bash
sudo nano /etc/hostname
```

Save it and reboot