---
layout: post
title: "Color Pickers"
subtitle: "Using Dribbble to pick better palettes."
date: 2013-05-08 16:59
active: true
stars: 3
categories: 
---

Our goal for this project is to design a color picker that helps everyone (even your grandma) pick "better" color combinations. In other words, is color picking limited to those with taste or is there some underlying relationship we can utilize? Can we write an algorithm that selects great color combinations for us?

Below is an experiment I call _The Colors of Dribbble_. It picks a random color and then displays the palettes of the most popular shots from [Dribbble](http://dribbble.com/) that contain that color. The refresh button on the right is the base color.

<script src="http://ajax.googleapis.com/ajax/libs/jquery/2.0.0/jquery.min.js"></script>
<script src="/js/colors.js"></script>
<link href="/css/colors.css" media="screen, projection" rel="stylesheet" type="text/css">

<div class="color-wheel">
  <div id="circle"></div>
  <div id="circle-border"></div>
  <div id="spokes"></div>
</div>

<div class="color-blocks">
  <div class="block-house"></div>
</div>


Below the color wheel are palettes of the top eight colors from each shot. If you hover over the bottom palettes it will hide all other palettes from the color wheel. On the surface it's a fun tool to play with. For example, look for the color rules below when hovering.

![color rules](/images/blog/color-rules.png)

###A Color Formula 

If you've ever dabbled in color theory you'll know there are a ton of rules for picking color combos. You can spend days reading about various color systems, HSV, RGB, CMYK, CIELAB, additive/subtractive color mixing, etc. The rule-based nature of this information makes a "color-combo formula" seem plausible.

Additionally, there won't be any new colors years from now. The color spectrum of the future will be exactly the same as it is today. It's neat to think we already have access to the color palettes of the year 3000. Because of this, it seems we have everything we need to write an end-all-be-all algorithm for picking good-looking color palettes.

Unfortunately, it's not that simple.

###Culture, Context, and Time
There is a lot more involved in picking color combinations than the rules and guidelines you'll find in basic color theory. Other things that matter include: 

   * Time - what looked good in the seventies may look terrible now
   * Medium - the colors of a movie poster would make a poor street sign
   * Popularity - skeuomorphism may be beautiful until everyone does it
   * Existing Landscape - a competitor's colors are off-limits

…suddenly color picking starts to look a lot like predicting stocks.

Ultimately, there is no such thing as a good color combination in a vacuum. What is considered good-looking requires information about society, and about existing color combinations in the space or industry. We need to know what colors are fashionable, trendy, or overused in the world. We need _a lot_ of information.

What does this mean for our color picking algorithm? Do we just give up? How could we possibly collect and incorporate all of this information into a color picker?

###Big Data
Believe it or not, this information is already available to us. Sites like Dribbble, Forrst, or Behance have created dense communities of designers with taste, sharing their work. At the time of this post there have been 108,854,356,487 pixels "dribbbled" on Dribbble. Not until now could you so quickly aggregate a "snapshot" of great design today. A place that collects samples of the best work from (only) those with taste. 

From this we can measure what is up-and-coming, popular, or on it's way out in the world of design.  We can use the innate understanding from these designers to make color picking easier for everyone else. In the not-too-distant future, we may even be able to measure (and generate?) good taste. 

We'll be releasing a more full-featured color picker soon where you can breakdown colors by medium, see the original artwork, etc. 