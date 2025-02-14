---
title: 'October 2024 Update'
date: 2024-11-05
featureImage: images/undraw/undraw_file-sync.svg
ogImage: images/undraw/undraw_file-sync.png
author: Jack Kawell
authorThumb: images/authors/jack.jpg
authorRef: jgkawell@mastodon.world
description: >
  File uploads come to Home Cloud! Also, SSH access has been added for our advanced users!
---

<img src="/images/undraw/undraw_file-sync.svg" style="width: 75%;" />

## Intro

Has it been a month already? Time certainly flies when you're busy! Our [last update](/blog/september-2024-update) covered the updates to Home Cloud over the month of September and we're back with an update on what's happened during October!

## October Recap

This month saw us focus mostly on structural work which is readying Home Cloud for the next big feature coming soon (more on this later in the update)! Aside from those behind the scenes changes, we fixed a bunch of bugs, cleaned up some of the admin dashboard's UI elements, and added two new features!

### File Uploads

![a screenshot of the file upload feature](/images/blog/upload-feature.png)

The first new feature of October is file uploads! For apps like Jellyfin, you need files (movies, TV shows, music, etc.) in order for the App to work. We've added the ability to upload files directly from the Home Cloud admin dashboard to any installed app. Simply choose the App's storage volume, optionally choose a path or file name, then select your file and boom! You're file will be uploaded to the App and will be ready to use. Give it a try and [let us know](/contact) what you think!

### SSH Access

![a screenshot of the new SSH settings page](/images/blog/ssh-settings.png)

This second feature was requested by a couple of our beta testers who are interested in have more granular options on how to manage their Home Cloud devices. For those of you who want to develop Home Cloud or want options to manually tweak OS configuration or App files, you can now enable SSH access and even add trusted SSH keys directly through the Home Cloud admin dashboard! Simply toggle the feature on in settings and you're ready to directly connect to your Home Cloud device from any other device.

### Other Changes

I mentioned earlier that we've been doing a lot of behind the scenes work on Home Cloud this month as well. These aren't in user features (yet) but are setting the groundwork for upcoming features in the near future! I wanted to shout them out really quick too.

- The Home Cloud daemon now supports migrations to enable updates to the NixOS configuration over time.
- We fixed some issues regarding RPC streaming inside the [draft](https://github.com/steady-bytes/draft) framework
- We've been building out a native eventing system within [draft](https://github.com/steady-bytes/draft) which will power many upcoming features

## Home Cloud on the Go

I mentioned [last month](/blog/september-2024-update) that we've started work on the next big feature which we're calling **"Home Cloud on the Go"**. Home Cloud in its current state is a powerful tool to replace external cloud services but Home Cloud apps are currently only useable while on your home network. While this is sufficient for some folks, for Home Cloud to truly replace cloud services the apps must be accessible even when you are away from your home.

To that end, we are working on a remote access feature which will provide secure, fully-private access to your Home Cloud server even when away from your home. This will enable you to check your grocery list in Mealie while at the store, add a note to Memos while at work, and even stream your favorite show from Jellyfin while on vacation.

This month we wrapped up our first iteration on this feature and are rapidly forging ahead to get it in your hands as soon as possible. Do you have any specific use cases for remote access you'd like us to consider as we build out this feature? Please [reach out](/contact) and let us know your thoughts!

## Wrap up

That's it for this month! We're excited to see the enthusiastic response to the project both in our early testers and others as we've been sharing both our progress and vision for the future with Home Cloud. If you're interested in testing out one of our prototypes please [reach out](/contact) to let us know. If you want to run Home Cloud on an existing system check out [our GitHub](https://github.com/home-cloud-io) where all our code is open-sourced.

We're grateful for everyone who's joining us on this journey and can't wait to share future updates with you!

Until the next one,

_Jack_
