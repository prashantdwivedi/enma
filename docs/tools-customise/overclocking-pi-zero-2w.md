### Follow the below `steps` to Pi Zero 2 W 1.3GHz

```bash
#update
sudo apt update

#upgrade
sudo apt full-upgrade

#config-file
sudo nano /boot/config.txt
```

Add both Lines at The Bottom of the config.txt
`#Overclock 1400` to use `Attach a fan or heatsink` to the Pi Zero before powering on.

```bash
#Overclock 1300
arm_freq=1300
over_voltage=4 #change value(4/6)

#Overclock 1400
arm_freq=1400
core_freq=525
over_voltage=6
gpu_freq=700
force_turbo=1
```

Reboot

```bash
sudo reboot
```

Measure Temperature 

```bash
vcgencmd measure_temp
```

---

Reference link:

[https://youtu.be/5RB29g18m-I](https://youtu.be/5RB29g18m-I)

[https://www.tomshardware.com/how-to/overclock-raspberry-pi-zero-2-w](https://www.tomshardware.com/how-to/overclock-raspberry-pi-zero-2-w)