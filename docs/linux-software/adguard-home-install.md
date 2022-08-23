![Untitled](/assets/adguard-cover.png)

### Automated install (Linux and Mac)

Run the following command in your terminal:

```bash
curl -s -S -L https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

The script also accepts some options:

- `c <channel>` to use the specified channel.
- `r` to reinstall AdGuard Home;
- `u` to uninstall AdGuard Home;
- `v` for verbose output;

Note that options `-r` and `-u` are mutually exclusive.

### You can control the service status with the following commands:

```bash
sudo /opt/AdGuardHome/AdGuardHome -s start|stop|restart|status|install|uninstall
```

### Adding Additional DNS Blocklists

Go to this website [https://firebog.net](https://firebog.net/)
or list of below name `copy` and `paste` on google and search it

- AdGuard DNS filter (37977)
- AdGuard Base filter (68189)
- EasyList (39079)
- Fanboy’s Annoyance List (17874)
- EasyPrivacy (17878)
- Spam404 (8038)
- The Big List of Hacked Malware Web Sites (8913)
- Scam Blocklist by DurableNapkin (404)
- NoCoin Filter List (611)
- feodotracker (163)
- Fanboy’s Problematic websites List (1781)
- StevenBlack: Unified hosts (adware + malware) (57571)

Other → https://github.com/StevenBlack/hosts

---

Reference link:

https://youtu.be/KOc4k0oFlzU

[https://github.com/AdguardTeam/AdGuardHome#getting-started](https://github.com/AdguardTeam/AdGuardHome#getting-started)
