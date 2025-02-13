---
title: 'November 2024 Update'
date: 2024-12-02
featureImage: images/undraw/undraw_design-process.svg
author: Jack Kawell
authorThumb: images/authors/jack.jpg
authorRef: jgkawell@mastodon.world
description: >
  A complete overhaul of the Home Cloud dashboard plus upload improvements!
---

<img src="/images/undraw/undraw_design-process.svg" style="width: 75%;" />

## Intro

November has come and gone and with it some big changes for Home Cloud! I hope you're enjoying some extra time with friends and family during this holiday season. In between family celebrations and travel we've been hard at work on the upcoming **Home Cloud On the Go** feature as well as entirely overhauling the Home Cloud Admin Dashboard (web app). Read on below for the full update!

## November Recap

### Admin Dashboard Overhaul

The biggest change this month was a complete reworking of the Admin Dashboard. For those of you interested, the previous version was written using React Bootstrap in Javascript during the rapid prototyping that led to our initial early access release. The new version is now using React and the [Ant Design](https://ant.design/) component library in Typescript. Not only does the design feel a lot more modern, the change to a component library and Typescript will help us add more features faster and with more polish.

You can see the before and after comparison below:

<!-- PICTURES HERE -->

OLD
![a screenshot of the old Home Cloud admin dashboard](/images/blog/old-dashboard.png)
NEW
![a screenshot of the new Home Cloud admin dashboard](/images/blog/new-dashboard.png)

Along with these changes we improved the file upload so you can upload multiple files at once as well as track the progress of each file as it's uploading. Neat!

![a screenshot of multiple files being uploaded at once with a large video file showing a progress bar](/images/blog/better-uploads.png)

### On the Go Progress

We're continuing to make progress on **Home Cloud On the Go**, the upcoming feature that will enable you to securely and privately connect to your Home Cloud server from anywhere in the world. If you look at the new Settings page you'll actually see the beginnings of this feature already showing up. We've finished the first iteration of the way you'll set up **On the Go** but there's still a lot to do before it's ready for use.

Like last month, I'd like to ask you if you have any specific use cases for remote access you'd like us to consider as we build out this feature. We've got a good foundation for the functionality so far and we'd love to hear from you about any use cases you're interested in and would like to see in the final product. Please [reach out](/contact) and let us know your thoughts!

## Wrap up

That's it for November! It's wild that we're heading into the final month of 2024. It's been an exciting year for us with going from ideation to prototyping within just a few months. We're glad you're coming along for the ride! If you're interested in testing out one of our prototypes please [reach out](/contact) to let us know. If you want to run Home Cloud on an existing system check out [our GitHub](https://github.com/home-cloud-io) where all our code is open-sourced.

While our next project update will be in January, I do have at least one more blog post that will be dropping later in December so stay tuned for that!

Until the next one,

_Jack_
