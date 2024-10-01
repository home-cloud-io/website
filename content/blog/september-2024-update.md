---
title: "September 2024 Update"
date: 2024-10-01
featureImage: images/logo.png
author: Jack Kawell
authorThumb: images/authors/jack.jpg
---

## Intro

Welcome to our first project update blog post! A month ago I published a [blog post](/blog/welcome/) introducing the Home Cloud project and giving an overview of the journey so far. This month, I want to recap the improvements we've made over the past month and also offer a sneak peek into what's coming over the next couple of months.

## September Recap

### Platform Updates

At the beginning of the month, we delivered our first prototype to our very first beta tester. We received a bunch of excellent feedback for suggested improvements and bug reports. Most of the development efforts this month went into implementing changes to address that feedback and stabilize the platform before deliverying more prototypes for wider testing. Below is a list of the major changes we made over the past month:

- Reworked the way Home Cloud advertises itself to devices on your network to address some bugs where sometimes Android and Windows devices couldn't access the **home-cloud.local** domain.
- Added better error handling in the web app.
- Implemented input validation in the web app for the onboarding flow.
- Fixed some critical bugs with the auto-update system for apps, system services, and the operating system itself.
- Added a settings page: [home-cloud.local/settings](http://home-cloud.local/settings)
- Implemented an "installing" visual to the web app until an app finishes installation.
- Sorted apps within the store consistently.

Towards the end of September we also delivered more prototypes for further testing. We're currently receiving feedback from those early users and will incorporate change to address them in coming releases.

### App Store Additions

The initial release last month only included two apps within the App Store. **Immich** which acts as a full replacement for services like Google Photos and iCloud photos, and **Postgres** which is a database that Immich uses under the hood. During the past month we added our first batch of new apps to the store:

- **Jellyfin** is the volunteer-built media solution that puts you in control of your media. Stream to any device from your own server, with no strings attached. Your media, your server, your way.
- **Mealie** is an intuitive and easy to use recipe management app. It's designed to make your life easier by being the best recipes management experience on the web and providing you with an easy to use interface to manage your growing collection of recipes.
- **Memos** is a privacy-first, lightweight note-taking service. Easily capture and share your great thoughts.
- **SearXNG** is a free internet metasearch engine which aggregates results from various search services and databases.

We'll be continually adding apps to the App Store and if there's anything specific you'd like added [let us know](/contact) so we can prioritize getting it added!

### Documentation Website

This month we also released a documentation website: https://docs.home-cloud.io

It's barebones for now but it will be expanding rapidly over time. The website will be the home for both user manual articles like setting up a new device as well as technical developer docs for people interested in developing Home Cloud apps or working on the core platform.

## Current Work

Our current work is focusing on a cornerstone feature for the future of Home Cloud. Home Cloud in its current state is a powerful tool to replace external cloud services but Home Cloud apps are only useable while on your home network. While this is sufficient for some folks, for Home Cloud to truly replace cloud services the apps must be accessible even when you are away from your home.

To that end, we are working on a remote access feature which will provide secure, fully-private access to your Home Cloud server even when away from your home. This will enable you to check your grocery list in Mealie while at the store, add a note to Memos while at work, and even stream your favorite show from Jellyfin while on vacation.

We're in the early phases of development of remote access and don't expect to to be live for at least a couple of months so stay tuned for updates as we make progress. Also, if you have any special requests or suggestions about this feature please [let us know](/contact)

## Wrap up

That's it for this month! We're excited to see the enthusiastic response to the project both in our early testers and others as we've been sharing both our progress and vision for the future with Home Cloud. If you're interested in testing out one of our prototypes please [reach out](/contact) to let us know. If you want to run Home Cloud on an existing system check out [our GitHub](https://github.com/home-cloud-io) where all our code is open-sourced.

We're grateful for everyone who's joining us on this journey and can't wait to share future updates with you!

Until the next one,

*Jack*
