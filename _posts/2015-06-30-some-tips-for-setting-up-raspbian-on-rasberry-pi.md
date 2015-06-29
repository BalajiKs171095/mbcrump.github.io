---
layout: post
title: Some Useful Commands for Raspbian on Raspberry Pi
excerpt: I list out several commands that helped me get started with Raspberry Pi. 
tags: blog
comments: true
---

##Introduction

I bought a Raspberry Pi a couple of months ago and have been setting up Kodi, EmulationStation and more. If you are new to Raspberry Pi and especially the Raspbian distro, then some of the commands will be useful as you get started with Linux. 

##APT Commands

From your terminal, enter the following to make sure you are always working with the latest apt package : 

	sudo apt-get update
	
You will be using this to install all sorts of things. 

##Install Kodi (XBMC)

Kodi is basically Xbox Media Center. You want this if you plan on playing music, video, etc : 

	sudo apt-get install kodi
	

##Get your IP Address

From your terminal, enter the following : 

	ifconfig
	
You should see your IP address now. You will need this to SSH, FTP and so forth. 

##Mount a Drive (USB External)

From your terminal, enter the following : 

You'll need to know what the drive is called to mount it. 

	sudo fdisk -l
	
You're looking for a partition that should look something like: /dev/sda1. Write that down. 

Create a new directory if one is not already there in /media so you can mount the drive onto the filesystem:

	sudo  mkdir /media/usb

Mount the drive

	sudo mount /dev/sda1 /media/usb
	
If the drive is formatted in NTFS, install the following drivers then mount it: 

	sudo apt-get install ntfs-3g
	sudo mount -t ntfs-3g /dev/sda1 /media/usb


When you're done:

	sudo umount /media/usb

##SSH into your Pi

From your terminal, enter the following : 

	ssh pi@<IP>
	
where <IP> is your IP address that you got from the first code snippet in this post. 


##FTP into your Pi

From your terminal, enter the following first to install the daemon : 

	sudo apt-get install ftpd
	
Now you can open a connection in the terminal by using, 

	ftp
	open <IP>
	cd /to/whatever/directory
	lcd /is/your/local/directory
	put filename.zip
	bye
	
This open the connection and changes to a directory on the pie, then your local file system and puts a file in it. 

##Install RetroPie

Run these commands to install RetroPie, this will allow you to emulate various consoles, etc. 

	sudo apt-get upgrade -y git
	sudo apt-get install -y git dialog
	cd
	git clone --depth=0 git://github.com/petrockblog/RetroPie-Setup.git
	cd RetroPie-Setup
	chmod +x retropie_setup.sh
	sudo ./retropie_setup.sh 
	sudo chown -R pi:pi /home/pi/RetroPie

Take Option 1 during the setup process and exit out when it is finished. You can now place your ROMS in this directory. 

	/home/pi/RetroPie/roms
	
You can now connect a joypad and run : 
	
	emulationstation
	
to start playing your games. 

	
##Wrap-up

This is kind of a brain-dump of commands that I needed when I first got started. I'm sure I'll be coming back to it at some point and hopefully you found it useful. 

