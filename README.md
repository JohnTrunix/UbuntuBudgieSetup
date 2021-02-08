# UbuntuBudgieSetup

## General
This cheat sheet is my personal setup after a reinstallation of Ubuntu Budgie 20.04

First always do:

`sudo apt-get update`

`sudo apt-get upgrade`

## Make sudo useable without pw

`sudo visudo`

Add this line at the bottom, change ubuntu by your username

`ubuntu ALL=NOPASSWD: ALL`


## Install XRDP Server

`sudo apt install xrdp`

Check if xrdp is running.

`sudo systemctl status xrdp`


`sudo adduser xrdp ssl-cert`

`sudo nano /etc/xrdp/startwm.sh` [Guide](https://froth-and-java.dev/posts/ubuntu-budgie-and-xrdp)

	Comment out this lines
	#test -x /etc/X11/Xsession && exec /etc/X11/Xsession
	#exec /bin/sh /etc/X11/Xsession
	
	Add this line to the bottom:
	budgie-desktop
	
`sudo systemctl restart xrdp`


## Install SSH Server
`sudo apt install openssh-server`

`sudo systemctl status ssh`
