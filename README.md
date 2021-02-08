# UbuntuBudgieSetup

## General
This cheat sheet is my personal setup after a reinstallation of Ubuntu Budgie 20.4

## Make sudo useable without pw
"sudo visudo"

ubuntu should be your user

ubuntu ALL=NOPASSWD: ALL


## Install XRDP Server

sudo apt-get update
sudo apt-get upgrade

sudo apt install xrdp
sudo systemctl status xrdp
sudo adduser xrdp ssl-cert
sudo nano /etc/xrdp/startwm.sh (https://froth-and-java.dev/posts/ubuntu-budgie-and-xrdp)
	#test -x /etc/X11/Xsession && exec /etc/X11/Xsession
	#exec /bin/sh /etc/X11/Xsession
	budgie-desktop
sudo systemctl restart xrdp


## Install SSH Server
sudo apt install openssh-server
sudo systemctl status ssh
