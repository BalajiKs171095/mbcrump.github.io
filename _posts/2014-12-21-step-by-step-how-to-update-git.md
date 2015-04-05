---
layout: post
title: "Step-by-Step on How to Update Git on Mac"
excerpt: "A quick way to update your Git client to the official distro."
tags: [git, mac, sourcecontrol]
comments: true
---

###Introduction

I've seen a lot of questions on the web about how to update your Mac client to the latest version which contains the fix for the [security vulnerability](Vulnerability announced: update your Git clients) announced last week. 

It is actually quite simple: 

Open your terminal prompt and type the following: 

	git --version
	
If it comes back with the following result, then you are using Apple's Git, not the offiical distro of Git. 

	git version 1.9.3 (Apple Git-50)
	
This version is **NOT** patched. 

Furthermore if you type, 

	which git
	
and it returns

	/usr/local/bin/git
	
Then you are going to want to modify your PATH to make git look for the official distro (which we will install in just a sec) to just /usr/local/bin.

##Let's Fix it and switch Git Clients

Install [Homebrew](http://brew.sh) if you haven't already. It is easy just copy and paste this in the terminal window. 

	ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
	
Assuming you have homebrew installed, type the following: 

	brew install git
	
Once it is installed, then type the following two lines, which will set our path to the local git distro instead of the Apple one.  

	export PATH=/usr/local/bin:$PATH
	git --version
	
and you will see:

	git version 2.2.1
	
That is it! You are now updated to the official distro of Git on your Mac. To update it in the future all you will need to do is run the following line:

	brew upgrade git
	
Until next time, Michael signing off.


