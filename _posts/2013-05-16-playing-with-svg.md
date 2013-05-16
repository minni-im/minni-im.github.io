---
layout: post
title: Playing with SVG
categories: code
---

<!-- excerpt start -->
Lately I was playing a bit with SVG.

[Patrick](http://twitter.com/patrickbrosset), a friend of mine, recently bought a Macbook Pro Retina
and suddenly I had to face the truth:

> Pictograms and images suck on Retina enabled devices !

So I took the opportunity to try SVG. I thought it would be great to try to reproduce
the left sidebar icons for the Lobby and the type of rooms.
<!-- excerpt end -->

So I ended up with this:

### Lobby icon

On the left, the original image, on the right the SVG one

<div style="background: url(/images/2013/05/background-sidebar-left.jpg) top left repeat; padding: 5px; text-align: center;">
    <style type="text/css"> .lobby {width: 32px; height: 32px; } </style>
	<img src="/images/2013/05/lobby.png" />
	<svg class="lobby">
		<line stroke-dasharray="4,2,28" x1="6" y1="10" x2="26" y2="10" stroke="#f9f9f9" stroke-width="4"/>
    	<line stroke-dasharray="4,2,28" x1="6" y1="16" x2="26" y2="16" stroke="#f9f9f9" stroke-width="4"/>
    	<line stroke-dasharray="4,2,28" x1="6" y1="22" x2="26" y2="22" stroke="#f9f9f9" stroke-width="4"/>
	</svg>
</div>

{% highlight html %}
<svg>
	<line stroke-dasharray="4,2,28" x1="6" y1="10" x2="26" y2="10" stroke="#f9f9f9" stroke-width="4"/>
    <line stroke-dasharray="4,2,28" x1="6" y1="16" x2="26" y2="16" stroke="#f9f9f9" stroke-width="4"/>
    <line stroke-dasharray="4,2,28" x1="6" y1="22" x2="26" y2="22" stroke="#f9f9f9" stroke-width="4"/>
</svg>
{% endhighlight %}

### Public room icon

<div style="background: url(/images/2013/05/background-sidebar-left.jpg) top left repeat; padding: 5px; text-align: center;">
	<style type="text/css"> .public_room { width: 24px; height: 24px; border: 4px solid #fff; border-radius: 6px; } </style>
	<img src="/images/2013/05/group-room.png" />
	<svg class="public_room">
		<line stroke-dasharray="4,2,4,2,4" x1="4" y1="6" x2="20" y2="6" stroke="#f9f9f9" stroke-width="4"/>
		<line stroke-dasharray="4,2,4,2,4" x1="4" y1="12" x2="20" y2="12" stroke="#f9f9f9" stroke-width="4"/>
		<line stroke-dasharray="4,2,4,2,4" x1="4" y1="18" x2="20" y2="18" stroke="#f9f9f9" stroke-width="4"/>
	</svg>
</div>

For the border I decided to still use CSS, with a simple `border: 4px solid #fff` and `border-radius: 6px`

{% highlight html %}
<svg>
	<line stroke-dasharray="4,2,4,2,4" x1="4" y1="6" x2="20" y2="6" stroke="#f9f9f9" stroke-width="4"/>
	<line stroke-dasharray="4,2,4,2,4" x1="4" y1="12" x2="20" y2="12" stroke="#f9f9f9" stroke-width="4"/>
	<line stroke-dasharray="4,2,4,2,4" x1="4" y1="18" x2="20" y2="18" stroke="#f9f9f9" stroke-width="4"/>
</svg>
{% endhighlight %}

### Private room icon

For this one I created a new one, more relevant to me.

<div style="background: url(/images/2013/05/background-sidebar-left.jpg) top left repeat; padding: 5px; text-align: center;">
	<style type="text/css"> .private_room { width: 24px; height: 24px; border: 4px solid #fff; border-radius: 6px; } </style>
	<img src="/images/2013/05/private-room.png" />
	<svg class="private_room">
		<g>
			<line stroke-dasharray="4,2,4,2,4" x1="4" y1="6" x2="20" y2="6" stroke="#f9f9f9" stroke-width="4"/>
			<line stroke-dasharray="4,2,4,2,4" x1="4" y1="12" x2="20" y2="12" stroke="#f9f9f9" stroke-width="4" stroke-opacity="0.5"/>
			<line stroke-dasharray="4,2,4" x1="4" y1="18" x2="16" y2="18" stroke="#f9f9f9" stroke-width="4"/>
		</g>
    	<g opacity="0.5">
	    	<rect x="16" y="16" width="4" height="4" fill="#f9f9f9" />
		</g>
	</svg>
</div>

Same story than above for the border.

{% highlight html %}
<svg>
	<g>
		<line stroke-dasharray="4,2,4,2,4" x1="4" y1="6" x2="20" y2="6" stroke="#f9f9f9" stroke-width="4"/>
		<line stroke-dasharray="4,2,4,2,4" x1="4" y1="12" x2="20" y2="12" stroke="#f9f9f9" stroke-width="4" stroke-opacity="0.5"/>
		<line stroke-dasharray="4,2,4" x1="4" y1="18" x2="16" y2="18" stroke="#f9f9f9" stroke-width="4"/>
	</g>
    <g opacity="0.5">
    	<rect x="16" y="16" width="4" height="4" fill="#f9f9f9" />
	</g>
</svg>
{% endhighlight %}

----

The original playground source code for all this, is available [here](http://juliandescottes.github.io/instantat/#51934f39e4b051dece087679) on InstantAT.
