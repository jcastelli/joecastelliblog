---
layout: post
title:  "In a nutshell: How the internet works"
date:   2014-02-07 21:11:00
categories: web-ed
---

I'm generally told I do a solid job of explaining technical things to newcomers, so I thought I'd do some introductory breakdowns of the various parts of Web development in hopes that I can help some friends and wandering Googlers.

A great place to start is with Web servers. The internet is just a crapload of computers and other devices (phones, tablets, etc.) connecting to one another across a crapload of networks. The deep mechanics behind how our computers talk to each other isn't important for diving into webdev, but there's a part that is crucial to beginning to code dynamic websites.

You've probably heard the term 'server' by now. The word can be intimidating, but it's not as angry as it may seem in pop culture. Technically, the Web server is software sitting on a computer somewhere, waiting for you to send it a request. Apache, IIS and Nginx are the three you see a lot. I'm using Nginx to serve this very website. By default, Nginx and its peers will 'listen' on a certain port for incoming requests. A request is made when you type a URL into a browser. You're asking for a website, and the server, well, serves it up.

If you're using a desktop computer to view this site, you can literally install free server software on the machine you're using, start the server, create an HTML document and other devices on your home network can view it by typing your IP address into their favorite browser. The word 'server' is also often used interchangeably to describe the hardware (the computer itself) or both at the same time. "We've got 12 servers in our IT room" would more than likely be referring to the whole machines, not the software they're running.

So when you open your browser and type in google.com, your browser talks to the nearest DNS server, which contains the IP address for Google. Once it's got that IP, it finds the actual server where Google's waiting for you. Once it sees your request, it sees that you're going to the main page, and sends you the HTML, CSS and JavaScript that make up that main page. Your browser literally downloads these files, and the pretty page is put together right in front of you.

## Server-side stuff

Web browsers used to be pretty terrible. Hell, computers were, too. Just a few years ago, when we wanted a page to be dynamic – think of your profile picture popping up on Facebook – all of that processing would happen on the server before the page you requested was sent back to you.

A good example of this is your Facebook homepage. Even though many people are at www.facebook.com, what you see is completely unique. You see your friends' posts, targeted advertising, groups you're in, messages, etc. While the way Facebook does this is much more sophisticated, early dynamic websites did most of this magic on the server before the page ever loaded into your browser.

Languages like PHP and Python run on the server before any pages are sent. This can be animated by some easy-to-read code. Let's pretend we have a super simple page that just greets the logged-in user. The HTML that would end up on your screen would look like this:

{% highlight html %}
<h1>Hello, Joe!</h1>
{% endhighlight %}

But it'd be silly to create individual pages like this with each user's name. That'd get messy very quickly. Instead, we do some processing on the server to grab the name of the logged in user. Let's do a mixture of PHP and comments where PHP would be to articulate this a bit.

{% highlight php %}
<?php
// ^~That's the opening PHP tag. The server's going to execute all of the code within these tags.
//The '//'' tells the server to ignore this line. It's a comment.

function getUserFirstName() {
	// We'll pretend code is here that grabs the currently logged-in user's username from the database and throws it into a variable called $firstName. Then we'll return it. In coding, we often use functions to contain code we'll want to run multiple times from elsewhere in our application.

	return $firstName;
}

// Variable names can be whatever we want, though you want to give them names that make sense.
$cheeseburger = getUserFirstName();

//We called our function and put it into a variable. Now we drop it into our content.
?>

<h1>Hello, <?php echo $cheeseburger; ?> </h1>
{% endhighlight %}

The resulting HTML would look exactly like that last snippet where I hardcoded my name into the `<h1>` tag. Notice there can be as many PHP blocks in one document as you need. If we pretend this file is called `myname.php` and it's on this very website, you could visit joecastelli.com/myname.php, the PHP code would run on the server, then simple HTML would appear in the document that lands in your browser.

As the Web has evolved, this has shifted a bit. JavaScript is often being used on the client (your browser) to perform tasks servers used to handle alone. 

## JavaScript

The combination of HTML, CSS and a server-side language like PHP was pretty much the way of the world for a while there. Once you requested `myname.php`, your computer was pretty much done talking to the server until you requested another page. There were few cases where the page would update without refreshing, which is a feature of many sites we've grown quite accustomed to recently.

JavaScript is the language that runs in the browser. It can move things around, count stuff, change things, store data, and do pretty much anything PHP or Python can, but in your browser. HTML alone doesn't do much outside of suppply content and structure:

{% highlight html %}
<h1>Hello, Joe!</h1>
<p>This is just a paragraph sitting in a paragraph tag.</p>
{% endhighlight %}

Adding CSS makes it prettier, not smarter:

{% highlight css %}
h1 {
	font-weight: 100;
	font-size: 30px;
	font-family: "Helvetica Neue",Helvetica,Arial,sans-serif;
	color: purple;
}

p {
	color: gray;
	font-size: 14px;
}
{% endhighlight %}

By themselves, they're pretty stupid. With JavaScript, the possibilities are endless. Let's do some stuff so you can see what I mean. For this little playtime, you'll need to be on a desktop or laptop computer using Firefox or Chrome to view this web page.

Right click anywhere on the page and click 'Inspect Element.' In the drawer that pops up, look at the top for 'Console' and click that. From here, we can run whatever JavaScript we want. Look for the little prompt – `>` – as that's where we're about to type. In Firefox, it'll be at the bottom of that drawer. In Chrome, it'll be at the top of the white space, but below anything that's already been output (errors, messages, etc.).

Once you're there, paste in `alert('testing');` and hit Enter. `alert()` is one of the many functions that come baked in with JavaScript.

For this site, I'm also loading jQuery, which is just a JavaScript framework. It brings a lot of cool stuff to the table, including some animation funcitons. Let's wreck some things with jQuery before we wrap this one up.

{% highlight javascript %}
// Calling the jQuery function slideUp() on every <p> tag on this page.
$('p').slideUp();

// This next line will refresh the entire page after eight seconds, undoing our mess so you can come back to the last paragraph here.
setTimeout("window.location.reload()", 8000);
{% endhighlight %}

You can do this on any number of sites. Try it on Pinterest, but replace the 'p' with 'img' to make all the images disappear. So now you're equipped to trick someone into thinking you're an evil hacker! The thing is, if a given site is NOT using jQuery, this won't fly.

Notice that reloading the page removed our hackery. That's because we only changed the document that was loaded into our browser, not the actual file on my server.

I just threw a lot at the wall, but I'm putting this post down for now. Feel free to comment with any questions, requests for new posts, or just to drop a hello!