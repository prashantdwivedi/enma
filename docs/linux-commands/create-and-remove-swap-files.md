There are two basic types of memory: Random Access Memory (RAM) and swap files.

## Recommended swap file size based on RAM

The following table shows the recommended swap size based on your RAM and whether you choose *hibernation*. Hibernation requires more space because it saves the system state when you shut down and restores it when you restart.

Remember that you'll need a large page file if your system has hibernation enabled, as it writes the contents of the RAM to swap on shutdown.

## How to Create a Swap File and Increase Swap Space

Verify the current swap file size. You can use any of the following commands to determine the size of the existing swap file:

```bash
free -m
swapon -s
swapon -show
```

Now that we've verified it's safe to proceed, and we can craft our swap file. There are a few ways to do this, but the easiest is via the `fallocate` program, which lets us allocate the exact size we want our `swapfile` to be. As mentioned earlier, our server has 1 GB of RAM. We're going to set our swapfile to 2 GB because we have plenty of free space, but 1 GB of the swap would likely work just fine if we didn't:

```bash
sudo fallocate -l 2G /swapfile
```

As we didn't specify a folder, our swap file will be placed in our root directory, which is what we want. The command won't give any output, so you can make sure the swap space was actually reserved with:

```bash
ls -lh /swapfile
```

In our case, the command returns:

`rw-r--r-- 1 root root 2.0G Aug 15 12:47 /swapfile`

However, though we have space reserved for our swapfile, our system hasn't yet be told this is where we want to it store information when out of memory. Before we do so, we want to make sure nobody but root can modify the file. Otherwise, an attacker could potentially use the file to perform an attack or steal information. Set the permissions with:

```bash
sudo chmod 600 /swapfile
```

Now verify that change using the same command as earlier: `ls -lh /swapfile`

The output should have changed from `rw-r--r-- 1 root root` to `-rw------- 1 root root 2.0G Aug 15 12:47 /swapfile`, indicating that now only root has the read and write flags enabled.

With that done, dedicate the file as swap space by entering:

```bash
sudo mkswap /swapfile
```

The output should say something like: 

``Setting up swapspace version 1, size = 2 GiB (2147479552 bytes) no label, UUID=f9429158-ec78-4dce-98c0-986167b47016``

Now we just need to enable the swap file:

```bash
sudo swapon /swapfile
```

And verify that it's available via the check commands from earlier:

```bash
sudo swapon --show
```

Make it permanent:

```bash
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
```

Last `reboot` to update change.

---

## Remove Swap File

Run the following command to reactivate the swap file:

```bash
swapoff -v /swapfile
```

Remove the entry

```bash
sudo nano /etc/fstab
```

Run the following command to remove the swapfile:

```bash
rm -f /swapfile
```

Last `reboot` to update change.

---

Reference & commands pick from:

[https://bitlaunch.io/blog/how-to-create-and-adjust-swap-space-in-ubuntu-20-04/](https://bitlaunch.io/blog/how-to-create-and-adjust-swap-space-in-ubuntu-20-04/)

[https://askubuntu.com/questions/1066358/increasing-the-swap-space-on-ubuntu](https://askubuntu.com/questions/1066358/increasing-the-swap-space-on-ubuntu)

[https://docs.rackspace.com/support/how-to/create-remove-swap-file-in-ubuntu/](https://docs.rackspace.com/support/how-to/create-remove-swap-file-in-ubuntu/)

[https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-20-04](https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-20-04)