---
layout: post
title: BlocJams
thumbnail-path: "img/blocJams-landing.png"
short-description: An online music player.

---

{:.center}
![]({{ site.baseurl }}/img/blocJams-landing.png)

## Explanation

BlocJams is an online music player application built on the AngularJS framework. It displays multiple albums and allows the user to click into each album to view and play the songs associated with that album.

## Problem

This application was originally built using HTML, CSS, JavaScript, and jQuery. The goal was to rewrite the application using Angular.

## Solution

The solution was to split up the main album.js file from the previous application into multiple JavaScript files such as controllers, services, and a custom directive. This made is easier to locate code for specific parts of the application rather than digging through hundreds of lines of code. It also reduces the amount of repeat code which make the application faster.

## Results

The result from this rewrite is a fully functional music player application written in Angular! The file structure makes it easier to navigate the code base. In the non-angular version of this app, one of the JavaScript files had almost 300 lines of code!

{:.center}
![]({{ site.baseurl }}/img/blocJams-album.png)

Albums are displayed and the user can click into each one which will display tracks from that album.

{:.center}
![]({{ site.baseurl }}/img/blocJams-songPlayer.png)

## Conclusion

Using Angular for the first time was very challenging, but it was also very rewarding. I definitely had a lot more fun writing this app using Angular and now I feel more confident in my ability to use frameworks.
