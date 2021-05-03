# UbuntuBudgieSetup

## General
This cheat sheet is my personal setup after a reinstallation of Ubuntu Budgie 20.04.

I try to keep it up to date!

First always do:
```sh
sudo apt update
```

```sh
sudo apt upgrade
```

## Make sudo useable without pw

```sh
sudo visudo
```
Add this line at the bottom, change ubuntu by your username
```sh
ubuntu ALL=NOPASSWD: ALL
```


## Install XRDP Server
```sh
sudo apt install xrdp
```


Check if xrdp is running.
```sh
sudo systemctl status xrdp
```

Add xrdp-user to ssl-cert group
```sh
sudo adduser xrdp ssl-cert
```

### Fix the "RDP Windowsession closes after login" Problem

Take a look at "Configuring" in this [Guide](https://froth-and-java.dev/posts/ubuntu-budgie-and-xrdp)

```sh
sudo nano /etc/xrdp/startwm.sh
```
	Comment out this lines:
	#test -x /etc/X11/Xsession && exec /etc/X11/Xsession
	#exec /bin/sh /etc/X11/Xsession
	
	Add this line to the bottom:
	budgie-desktop

```sh
sudo systemctl restart xrdp
```


## Install SSH Server
```sh
sudo apt install openssh-server
```

Check if SSH is running
```sh
sudo systemctl status ssh
```