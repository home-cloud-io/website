---
title: "Welcome to Home Cloud!"
date: 2024-09-02
featureImage: images/logo.png
author: Jack Kawell
authorThumb: images/authors/jack.jpg
authorRef: jgkawell@mastodon.world
---

## My Story

About 7 years ago I got my first [Raspberry Pi](https://www.raspberrypi.com/). That little microcomputer was my first step into hosting services at my house when I installed [Pi-hole](https://pi-hole.net/) as a way to block ads on my home WiFi. Over time my home server evolved from the Pi to an old PC I salvaged from going to the landfill. Fast-forward to today and I'm now running a multi-node cluster of custom servers hosting everything from photo storage to family recipes to smart home controls.

I've been a software and hardware engineer for a long time now and my self-hosting journey has been equally challenging and rewarding as I've had to pickup new skills and learn from many mistakes. It's been completely worth it though as I now get to enjoy the benefits of so many cloud services without the monthly subscription fees or constent errosion of privacy caused by Big Tech.

As I've shared my journey with friends and family I have always heard the same response: "I'm glad *you* get to benefit from self-hosting, Jack, but it's way to complicated for *me* to do." And I've always agreed with them. Running your own cloud is complicated. In order to run your own services you need to understand computer hardware, manage some form of orchestration, keep apps up to date, double check compatibility with each upgrade, and be ready to research and fix things when they break.

I've always wanted more people to be able to enjoy the benefits of self-hosting, but until recently I just considered it out of reach for most. The work required is much more than the average person is willing to do and because it's so technical it's out of reach for many people even if they wanted to.

![blog image](/images/blog/shapes.svg)

## The Idea

I hadn't really considered the idea of creating a solution to this problem until my good friend Andrew (a brilliant engineer who I've worked alongside for many years) proposed building a simple device to block ads and trackers at home earlier this year. We spent the next few weeks talking through this idea. We quickly realized that with the right design this could do far more than just be an ad-blocker. It could finally be a solution for people wanting a simple way to run their own services at home.

Andrew and I were immediately excited about this new idea. We had been working together on [a framework](https://github.com/steady-bytes/draft) for easily creating powerful, scaleable, and stable applications for years now and we knew this was a great opportunity to finally put it to the test.

![blog image](/images/logo.png)

## Home Cloud

So what is Home Cloud? In a single sentence; **Home Cloud makes running your own personal cloud of services as easy as owning a smartphone or laptop**. With Home Cloud, someone with no technical experience can buy a Home Cloud device, plug it in, and immediately get the benefits of hosting their own cloud. The only thing a user needs to do is choose the apps they want to install. The Home Cloud system manages updates, security, installing and managing apps, networking, storage, and much more.

From a technical perspective, Home Cloud itself is composed of a few different components:

- Operating System: Home Cloud runs on [NixOS](https://nixos.org/) which provides rock-solid stability.
- Orchestration: On top of NixOS, Home Cloud runs [Kubernetes](https://kubernetes.io/) for seamless management of apps and core services.
- Applications: The apps or services that run on Home Cloud are defined using [Helm charts](https://helm.sh/) for universal compatability.
- Framework: All core Home Cloud services are built using the [Draft framework](https://github.com/steady-bytes/draft) for consistency and scaleability.

## Current Status

We've been hard at work for months to get an initial release of Home Cloud out the door. We currently are circulating an early-stage prototype to some early testers as we gear up for a wider release.

If you would like to test out a Home Cloud prototype for yourself please [reach out](/contact)! If you've got technical experience and would like to run Home Cloud on your own hardware, check out [our GitHub](https://github.com/home-cloud-io) where we have open-sourced all the code for Home Cloud. Feel free to open up issues or pull requests for any bugfixes or improvements you'd like to see.

![blog image](/images/blog/clouds.svg)

## The Road Ahead

We still have a lot of work ahead of us and we're excited at where we're headed. Home Cloud as a project is moving quickly right now so if you'd like to stay tuned please [sign up](/subscribe) so we can keep you in the loop!

Until the next one,

*Jack*
