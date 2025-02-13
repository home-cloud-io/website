---
title: 'The Vision'
date: 2024-12-30
featureImage: images/undraw/undraw_adventure-map.svg
author: Jack Kawell
authorThumb: images/authors/jack.jpg
authorRef: jgkawell@mastodon.world
description: >
  We can't solve all the problems of the modern internet, but we can make a sizable impact in giving people ownership of their digital lives.
---

<img src="/images/undraw/undraw_adventure-map.svg" style="width: 75%;" />

## Intro

About six months ago I quit my job to work on Home Cloud full-time. It wasn't a sudden decision, my friend Andrew and I had been running prototypes of what ended up being Home Cloud for years and we talked for months about the possibility of turning it into something for the public benefit before I made the jump.

Andrew and I have been self-funding this endeavor since then and while we've delivered our first test devices, multiple versions of beta software, a beautiful informational website (at least to me but I'm biased), and project updates to the public, I've yet to publish a true vision for Home Cloud.

That's what this post is for. To clarify what it is we're creating and why we're so passionate about it.

<img src="/images/undraw/undraw_surveillance.svg" style="width: 50%;" />

## The Problem

The internet is broken. I don't think this is any sort of a hot take at this point.

While the web used to be an exciting place to learn, interact with your favorite people, and explore the world, nowadays just being online at all feels like a chore.

We see the symptoms of a broken system everywhere: advertisers track our every move, search engines are degrading, social media is a mess, and it feels like the entire web is owned by only a few massive corporations.

I could go on and on about the current issues of the modern internet but mostly you'd probably just be quietly nodding along and there's no use to that. Instead, I want to propose a vision to address the problem with a relatively simple solution.

Don't worry, I'm not pitching some wild scheme to reinvent the way we interact with the world. I'm simply proposing a return to the roots of the internet that can make the web a place where _people_ can thrive again.

We can't solve all the problems of the modern internet, but we can make a sizable impact in giving people ownership of their digital lives and empowering them to build a web where they can learn, interact, and explore again.

<img src="/images/undraw/undraw_educator.svg" style="width: 50%;" />

## A Little History

Let's go back in time a bit to put this in perspective. The internet started fundamentally as a way to share information between people in different places. It was built upon the same basic ideas as phones and the telegraph.

I think it's helpful to consider what the name "internet" even means. The internet is simply a linking of smaller networks (a network is just a collection of things that can talk to each other) into a larger inter-networked ("internet") system.

Initially, you chose to connect your local network to someone else's local network that you trusted. There wasn't any amorphous internet to just plug in a cable and connect to. You instead chose networks run by people you trusted to connect with and share data and access to.

Over time a generic internet formed allowing devices from any local network to connect to public services hosted on other networks. These public services were both complicated and expensive to manage and so they are typically run by larger organizations like companies, universities, and governments.

The promise of the "cloud" has been that it's cheaper and better than anything you could run at home. The narrative has been that it's less expensive and safer to, for example, store all your photos in some company's cloud rather than keep your data at home.

The prohibitive cost of running services has historically kept most people from running their own services and instead relying on larger organizations to run centralized services which the public uses. This has led to the problem outlined above where people have no choice but to use services provided by larger organizations regardless of the quality of the services themselves.

<img src="/images/logo.png" style="width: 75%;" />

## The Solution

While the complexity and cost of running services used to be very high, over the past couple of decades computer hardware costs and automation techniques have improved to the point where it's finally viable for everyday people to run their own services.

However, up until now there hasn't been an all-in-one solution to enable non-technical people to actually do this. Home Cloud is our attempt to pioneer this solution. Our goal is to finally bring the cloud back home by empowering everyone to reclaim their digital lives.

Home Cloud is far more than just a smart harddrive connected to your network. Let me outline a few things that make Home Cloud a complete solution to the needs of the modern internet.

<img src="/images/undraw/undraw_open-source.svg" style="width: 50%;" />

### Completely Open

First things first, Home Cloud is completely open source and free to use. For those who aren't aware, open source software is software where the developers publish the code online for anyone to read.

There are many benefits to this approach and I want to highlight a few of the main ones for Home Cloud users:

- Because the code is freely available no one can ever take Home Cloud away from you. No giant tech conglomerate can decide to charge you for access. If the current Home Cloud developers step away, any software engineer on the planet can continue supporting the project.
- Since the code is open, there are no secrets. There is no way for us as the developers to try and steal your data or do anything nefarious at all without the wider software community knowing about it.
- Open sourcing the code means you can trust the security of Home Cloud since any potential issues will be discovered by security researchers and reported. This is the model that core software components of the most important systems on the internet operate within and has been proven over decades.
- Releasing the code publicly means anyone on the planet can recommend ways to tweak, update, and bugfix the project. This ultimately means more features, faster fixes, and a better experience for Home Cloud users.

There are many more benefits to making Home Cloud open source like making it easier for developers to create applications for the platform but I'll leave the others for discussion another day.

<img src="/images/undraw/undraw_design-components.svg" style="width: 50%;" />

### Proven and Scalable Technologies

In an upcoming article I'll walk through the Home Cloud tech-stack in depth, but for now I want to highlight that we've built Home Cloud upon a proven and scalable software stack to make sure it will be able to support all the needs of a diverse userbase.

As a quick summary:

- Home Cloud runs on [NixOS](https://nixos.org/) which provides rock-solid stability.
- On top of NixOS, Home Cloud runs [Kubernetes](https://kubernetes.io/) for seamless management of apps and core services.
- The apps or services that run on Home Cloud are defined using [Helm charts](https://helm.sh/) for universal compatability.
- All core Home Cloud services are built using the [Draft framework](https://github.com/steady-bytes/draft) for consistency and scaleability.

We selected these technologies deliberately to ensure Home Cloud can scale from a single device running in an apartment closet to a multi-device Home Cloud cluster running your small business or non-profit.

<img src="/images/undraw/undraw_secure-server.svg" style="width: 50%;" />

### Your Own Internet

Recall earlier when I was discussing how the internet started with people choosing to link their local networks with other trusted networks? We are building this functionality into the core of the Home Cloud platform so that you can network your Home Cloud device with the Home Cloud devices of trusted friends and family.

You can think of these networked Home Cloud devices as your own sub-internet. This will enable you to safely and securely share that photo album of your child's first birthday with the grandparents or privately host a Minecraft server for you and your friends or even host your own Discord-like chat service for the whole family.

This Home Cloud network creates a place just for you and trusted friends and family to hang out online. And it's your place to do with as you wish. You choose the services you want, you choose the people to invite, you choose everything because you will finally own your digital life.

<img src="/images/blog/steady-bytes.png" style="width: 50%;" />

## About Us

Before I wrap up, I want to explain how some of this works behind the scenes. Like I mentioned earlier, Andrew and I have been funding this project ourselves from the beginning. There's no big company behind this and no million dollar investment round. **This is a project for people, built by people.**

Home Cloud is open source and free to use. If you want to install it on your own hardware you can do so without giving us so much as a dime. However, we do need to fund this thing somehow and our plan is to follow a similar route to [Home Assistant](https://www.home-assistant.io/) (awesome project that you should definitely check out by the way) which is funded through donations and selling hardware devices.

Alongside the Home Cloud project we have created a company called [Steady Bytes](https://steady-bytes.com) which will sell dedicated Home Cloud hardware and services with the profits going to fund Home Cloud development. We've already got hardware prototypes being tested by a few folks with the plan of releasing them for purchase **sometime in 2025**.

Finally, if you are interested in donating to Home Cloud development please [reach out](/contact) to let us know. We are considering creating a way for people to directly fund our development efforts if there is interest.

## Wrap Up

That's it for this Vision article. I hope this provides clarity on what we're building here at Home Cloud. We are passionate about the future of Home Cloud and are excited as we watch it take shape. If you have any questions, comments, or thoughts you'd like to share please [let us know](/contact).

Until the next one,

_Jack_
