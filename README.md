# Tor relay setup

![image](https://github.com/user-attachments/assets/555688ab-e683-404b-857a-f09d678e3bb8)

Download Tor browser from https://www.torproject.org/download/

**Tor circuit**
 - Tor User -> Guard Relay -> Middle Relay -> Exit Relay -> Destination (i.e example.com)
   
***using Bridge***

 - Tor User -> Bridge Relay -> Middle Relay -> Exit Relay -> Destination (i.e example.com)

In this, we setup a guard relay, as it safe to get started with minimal risk. Setting up a exit relay is generally unsafe as the IP address of the exit relay is exposed to the website and sometimes they might not be perfectly legal to visit. So, consult your ISP or local law enforcement or even the three letter agencies before proceeding (just kidding, be safe, as people might visit illegal or malicious site)
## setup instructions

- Follow this [guide](https://community.torproject.org/relay/setup/) on the official tor website to setup tor relay on your distro of choice.
- In rolling-release distros, you might have latest versions of tor, but in stable releases, it would be a bit *out-of-date*.
- For Ubuntu & Debian-based distros:
```
	# apt update
	# apt install tor
```

*Sometimes, tor package in the Debian or Ubuntu repos might be old, so it is recommended to install a newer version for better security, by following this [guide](https://landchad.net/tor/)*

*setup instructions for specific distros are [here](https://community.torproject.org/relay/setup/guard/)*

-  Edit the torrc file with required info: port, contact (include a anonymous email that does not include your real name, e.g., mr_robot@protonmail.me) & a nickname (optional).
```
	# nvim /etc/tor/torrc
```

- Restart the tor daemon
``` 
	# systemctl restart tor@default
```
