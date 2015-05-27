---
layout: post
title: Setting up Github with Visual Studio Code on OSX
excerpt: Step by Step Guide on Setting up Github with Visual Studio Code on OSX
tags: blog
comments: true
---

##Introduction

[Visual Studio Code](https://code.visualstudio.com/) has built in Git support, but very few know how to use it on OSX with GitHub. Even in the [official docs](https://code.visualstudio.com/Docs/versioncontrol), there is only a few paragraphs on it. In this post, I'll show you how I set it up. 

##Adding your project to GitHub

Switch to your project and hit the source control button as shown below. 

![image](/files/vscodeshowsource.jpg)

The first thing you will see is that your workspace isn't under git source control. 

![image](/files/addtogitvscode.jpg)

Press the "Initialize Git Repository" button and include a commit message (1) and finally hit the check mark at the top (2). 

![image](/files/gitinitialcommitvscode.jpg)


##Your Project is Under Git Source Control, now What?

If you navigate back to your project, then you will see a new folder called ".git" and a config file that contains the following :

{% highlight text %}
[core]
repositoryformatversion = 0
filemode = true
bare = false
logallrefupdates = true
ignorecase = true
precomposeunicode = true
{% endhighlight %}

Here is a screenshot of my project : 

![image](/files/gitconfigvscode.jpg)

This is typically the part where you begin a Google Search because you can't figure out how to get the drop down to populate to push your source to a remote server. 

![image](/files/cantcommittogitvscode.jpg)

##Time to Fix it!

Open [github.com](http://github.com) and create a Repo. Copy the path to the .git for later use. 

![image](/files/gitingithub.jpg)

Navigate to the directory where your Visual Studio Code project is and add the following two lines (replace my .git with yours) : 

{% highlight text %}
git remote add origin https://github.com/mbcrump/SampleProject.git
git push -u origin master
{% endhighlight %}

If you examine your .git/config file you will see the following has been added: 

{% highlight text %}
[core]
repositoryformatversion = 0
filemode = true
bare = false
logallrefupdates = true
ignorecase = true
precomposeunicode = true

[remote "origin"]
url = https://github.com/mbcrump/SampleProject.git
fetch = +refs/heads/*:refs/remotes/origin/*

[branch "master"]
remote = origin
merge = refs/heads/master
{% endhighlight %}

Here is a screenshot of my project : 

![image](/files/gitconfigfinalvscode.jpg)
	
You can now switch back to Git in Visual Studio Code and perform the operations from now on without the command line. Here is an example of where I modified a file and can now push to a remote server. 

![image](/files/maintsmodified.jpg)

##Wrap-up

Thanks for reading and if you have any questions or comments, then leave them below. If you are interested in my previous article on Visual Studio Code with TypeScript, then click [here](http://michaelcrump.net/using-typescript-with-code/). 

