---
title: "January 2025 Update"
date: 2025-02-12
featureImage: images/logo.png
author: Jack Kawell
authorThumb: images/authors/jack.jpg
authorRef: jgkawell@mastodon.world
---

## Intro

Welcome back! It's been a busy time for Home Cloud since our last update in November! At the end of 2024 I posted [a blog post outlining our vision](/blog/vision) and we've been hard at work improving various things across the dashboard like an about page, logging, manual updates, and app store improvements. In between those items we've also added some new apps to the store and continued to make progress on the upcoming **On the Go** feature! Read on below for details on what's changed and what's coming in future updates.

## Recap

### About Page

In our [last project update](/blog/november-2024-update) I showed how we have completely overhauled the Home Cloud dashboard to use a new component library which refreshed the entire interface. This new structure has made it much easier to add more functionality to the dashboard and the first one we've added is a new about page! On this page you can see the versions of all the components of your Home Cloud server. While this isn't important on a day-to-day basis, it will help with troubleshooting if anything goes wrong so you can easily know what versions of everything you have running. See below for what it looks like!

![A screenshot of the Home Cloud dashboard showing the About page listing all platform and system components and their respective versions.](/images/blog/about-page.png)

### Manual Updates

Alongside this, we've also added manual component updates to Home Cloud! When we initially launched our beta last year the only way to update components was automatically as the Home Cloud device scans for updates every night. Now, you can disable automatic updates and instead manually update as you see fit! There's a new page in the dashboard where you can check for updates and manually update each component only whenever is best for you; or never update, it's your choice!

![A screenshot of the Home Cloud updates page showing a list of Platform and System Components, their current versions, and some showing available updates.](/images/blog/updates-page.png)

### Logging

As we progress towards an official stable release, we knew we needed a better way to troubleshoot if anything goes wrong with a Home Cloud server. Just this month we added a logging page to the dashboard where you can see all the logs from each Home Cloud component, including all apps! The page supports filtering so you can drill down on a specific system component or filter out everything except that one app that doesn't seem to be working right.

![A screenshot of the Home Cloud dashboard showing a table of system logs broken into columns of timestamp, domain, group, source, and log. The domain, group, and source columns are color coded based on the value in the cell.](/images/blog/logging-page.png)

### On the Go Progress

We're continuing to make progress on **Home Cloud On the Go**, the upcoming feature that will enable you to securely and privately connect to your Home Cloud server from anywhere in the world. These past couple of months have seen some big steps forward as we added a STUN server to the Locator service and added Locator registration and STUN negotiation to the Home Cloud daemon. If that last sentence sounded like a foreign language just know that we're getting ever closer to an official release of **On the Go** but we've still got some more things to finish before then. Stay tuned!

## Wrap up

What a couple of months it's been. It's exciting to see Home Cloud continue to grow as we add features, polish rough edges, and continue to improve through user feedback. If you have suggestions, questions, or comments you'd like us to know about please [reach out](/contact) and leave us a message! If you'd like to learn more about how Home Cloud works behind the scenes or would like to run it yourself, check out [our Github](https://github.com/home-cloud-io) where all our code is fully open source.

I've mentioned in previous posts how we are building Home Cloud in the open and available for free. We plan on funding Home Cloud development through hardware sales and optional add-on services but for now we're funded through our company Steady Bytes as a software consultancy. We are currently fielding client work which helps fund Home Cloud development. If you're interested in hiring us, you can learn more about what we offer at our [company website](https://steady-bytes.com).

That's it for this month! Be sure to [subscribe](/subscribe) for future updates so you can keep up with all things Home Cloud!

Until the next one,

*Jack*
