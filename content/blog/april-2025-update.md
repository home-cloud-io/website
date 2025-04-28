---
title: 'April 2025 Update'
date: 2025-04-25
featureImage: images/undraw/undraw_secure-login.svg
ogImage: images/undraw/undraw_secure-login.png
author: Jack Kawell
authorThumb: images/authors/jack.jpg
authorRef: jgkawell@mastodon.world
description: >
  In the past few months we've made a ton of progress towards the release of Home Cloud On the Go! Plus bugfixes and dashboard improvements!
---

<img src="/images/undraw/undraw_secure-login.svg" style="width: 75%;" />

## Intro

It's been a while since our last update and it's high time for another blog detailing the improvements that we've been making to Home Cloud! These past few months have seen a ton of progress to the upcoming **On the Go** feature, some helpful improvements to storage usage, and a handful of dashboard updates. Let's get into it!

## Recap

<img src="/images/undraw/undraw_the-world-is-mine.svg" style="width: 50%;" />

### On the Go Progress

The primary focus of the past couple of months was finishing the core networking components for **Home Cloud On the Go** which will enable remote access to your Home Cloud even when not at home. We hit a big milestone in April where we connected to a prototype Home Cloud server from a test client across the internet using the full networking stack we've been building for the past six months!

We'll have a blog post out soon going over the way **On the Go** works from a technical perspective for those who are curious so I won't deep dive here, but we're super pumped to finally have all the hardest work behind us for this feature and are full speed ahead on getting the final things in place to roll it out to our beta testers! The next step on the roadmap is building a Home Cloud mobile app for iOS and Android which will create the secure tunnel that powers **On the Go**. More info coming soon!

<img src="/images/undraw/undraw_throw-away.svg" style="width: 50%;" />

### OS Garbage Collection

We got a report from one of our beta users that they were running out of space on their device and after investigating we found out the issue was that the Home Cloud operating system was storing a bunch of old update files that was taking up a ton of space. (If you're interested, these files are stored so that Home Cloud can automatically fix itself in case of a broken update.)

To fix this issue, we added a periodic garbage collection task that Home Cloud runs which checks for older update files and removes ones it no longer needs. We're so thankful for our beta users providing such helpful feedback as we continue development!

<img src="/images/undraw/undraw_blogging.svg" style="width: 50%;" />

### Dashboard Improvements

We also improved the Home Cloud dashboard by adding support for monitoring the usage of multiple storage drives as well as a live view of the device's CPU and memory usage!

<img src="/images/screenshots/stats-dashboard.png" style="width: 50%;" />

## Conclusion

It's an exciting time in Home Cloud right now as we gear up for the final push until the release of **On the Go** and we're glad you're following along with us. If this is your first time here, be sure to [subscribe](/subscribe) for future updates and if you have any questions for feedback for us please [reach out](/contact) and let us know!

That's it for now, keep your eyes peeled for the upcoming deep dive post all about **On the Go** which will be dropping soon!

Until the next one,

_Jack_
