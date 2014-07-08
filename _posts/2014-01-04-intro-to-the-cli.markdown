---
layout: post
title:  "The command line, in plain English BUTTTT what if our content spill onto two lines?"
date:   2014-01-04 21:11:00
categories: operating-systems command-line web-ed
---

When I first began really diving into Web development, the lack of a clear starting point was staggering. All I could do was latch on to what I understood, read a lot, and research the terms that'd come up that I'd never even heard before. 

I took two courses in college that I'd argue to be my cornerstone: System administration I, and System administration II. Being a sysadmin in the real world pretty much means maintaining the servers and other infrastructure upon which other people – developers in particular – rely. The thing about these courses that gave me such a fantastic head start was the deep education on the command line interface of *nix-like operating systems.

No matter what operating system you use on a day-to-day basis, most people interact with a user interface that makes life breezy. Drag something into the trash can, empty it sometimes. Click 'File,' then 'New File' to create a new document. Double click an icon to open a file in the program it was created with. You get my drift.

Under the hood, these actions are being translated into lower-level commands that you can issue yourself, bypassing the UI entirely. You can open a session in your terminal – you can find the 'Terminal' program on OS X – maneuver into a folder, create a new one inside it, create a file inside of that, then add text to that file.

Let's say you want to create a new folder on your desktop and create a few files within it. Rather than right click, fumble with naming/renaming, a few commands will get us where we need to be. On OS X:

{% highlight bash %}
# Change directory into my Desktop
## Note: The tilde(~) represents your home directory, which, in *nix systems, is completely unique for all users
cd ~/Desktop

# Now that my working directory is my desktop, let's make my new folder
mkdir newFolder

# Let's verify the folder has been created by listing the contents of the Desktop
ls -al

# We can see our new folder. Let's change into it
cd newFolder

# Now let's create a few text files that we can come back to and edit later
touch my-diary.txt foo.txt bar.txt

# Now let's list the contents of our new folder to ensure our files were created
ls -al

{% endhighlight %}

At face value, this seems entirely pointless. Why learn commands to do this sort of thing? For starters, you could toss all these commands into a script, add a bit more code and run it on a schedule, creating new folders with files inside them. Similar things are often done in the real world to create log files that we can look back upon when things break.

The thing is, these basic commands are only a start. The tools available to a savvy user are incredibly powerful. Have you ever wanted to separate the videos and images on an SD card into separate folders in one swoop? Maybe find all files in a folder than contain the word 'taxes?' You can also build an entire Web application using only the command line. In fact, I have several developer friends who do just that.

Even if you don't have a book or nerdfriend handy, you can see the 'manual' for almost any command by using the `man` command.

{% highlight bash %}
man ls;
man cd;
man touch;

# Each of the above commands will output a manual for the following command.
{% endhighlight %}

Learning your way around a Linux or Mac command line can ultimately lead to a better day-to-day computing experience. Take it for a spin!