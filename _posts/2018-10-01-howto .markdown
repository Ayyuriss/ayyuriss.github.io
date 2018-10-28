---
layout: post
title:  "How to reduce time on social networks : Unfollow everyone, with code"
date:   2018-10-28
description:  "How to spend less time on social networks"
categories: posts
author: "Ayoub"
tag: Social
---

<p class="indented">
It should be evident by now that social networks are forcing the users to stalk their connections. They do so through the infinite news feed that includes the health status of the pet dog of your friend's cousin's grandma.</p>
<p class="indented">
Facebook and Linkedin offer a way to unfollow multiple connections at a time. You can then cherrypick the connections to keep following.
For a long friend list, this simple task is exhausting. Fortunately, you can automate such task with few lines of code.
</p>
<h3>Facebook</h3>

<ol>
<li> Head to your main feed, and click on the three dots next to "News feed" on the side menu. </li>
<li> "Edit Preferences" -> "Unfollow people and groups to hide their posts". You can load the full list by scrolling before applying the next step.</li>

<li> Open the console from web developer menu. For Firefox, you can open the console with Ctrl+Shift+K</li>
<li> Execute the following line to automatically click on all the image blocks:
<pre class="lang:javascript decode:true ">
var c = document.querySelectorAll("div._5u3n");
for(i in c){
	if(c[i].getAttribute("aria-pressed")=="false"){
		c[i].click()}
	    }</pre>
</li>
<li>Done ! (Click)</li>
</ol>


<h3>LinkedIn (Facebook for disruptive people)</h3>

<ol>
<li> Head to your "following list" : <a href="https://www.linkedin.com/feed/following/">link </a></li>
<li> Open the console from developer mode. For Firefox, you can open the console with Ctrl+Shift+K</li>
<li> Excute the following snippet to automatically loop between unfollowing and scrolling (with >1000 connections, it takes some minutes):
<pre class="lang:javascript decode:true ">
setInterval(function(){
		var c = document.querySelectorAll("button.is-following");
		for (i in c){
			if(c[i].id != null){
				if(c[i].id.includes("ember")){
					 c[i].click()
				}
			}
	    	};
		window.scrollBy(0,2000);
	     },1000)</pre>
</li>
<li>Done !</li>
</ol>


<h2 style="text-align:center;">Enjoy you new saved time !</h2>
