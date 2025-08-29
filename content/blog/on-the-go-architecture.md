---
title: 'The Architecture of On the Go'
date: 2025-05-05
featureImage: images/undraw/undraw_private-data.svg
ogImage: images/undraw/undraw_private-data.png
author: Jack Kawell
authorThumb: images/authors/jack.jpg
authorRef: jgkawell@mastodon.world
description: >
  Let's cover how the upcoming On the Go remote access feature works! We'll cover the entire stack top to bottom (no PhD in networking required).
---

<img src="/images/undraw/undraw_private-data.svg" style="width: 75%;" />

## Intro

This post is going to cover how the upcoming **On the Go** remote access to your Home Cloud feature works! We'll cover the entire stack top to bottom (no PhD in networking required). We think it is important to explain how this feature works because there are plenty of ways to build it *very badly*. It is rarely wise to give any person or company remote access to a device running on your home network. This is why we are deliberately building On the Go so that no one (not even us at Steady Bytes) has remote access to your Home Cloud device or network without your permission.

To start, let's go over some of the core ideas of how devices talk to each other on the internet so that we have a good understanding of what we mean by "remote access" in relation to Home Cloud.

## The Basics

*Note: if you're already familiar with the basics of IP and networking, you can skip ahead to [the core problem](#the-core-problem).*

### How does the internet work?

You can think of the internet similarly to how a postal service works. If John wants to send a letter to Jane, he can do so by writing his note on a piece of paper, putting that paper in an envelope, adding Jane's address to the envelope, adding his own return address, and giving the letter to the postal service. The postal service looks at the address, and since they know how to find that address on the map, they can deliver the letter to Jane.

There are four main components to any letter:

1. The letter; which contains the personal note
2. The envelope; which keeps the note from being damaged or seen by the wrong person
3. The address; on the envelope which tells the postal service where to deliver it
4. The return address; which tells the recipient where to respond if desired

*Sending data on the internet functions in a very similar way.* If computer A wants to send a message to computer B, it can do so by encrypting the message data, attaching the internet protocol (IP) address of computer B, and giving the message to an internet service provider (ISP). The ISP then looks at the IP address, and since they know how to find that IP address on the internet, they can deliver the message to computer B.

<img src="/images/blog/message-comparison.svg" style="border-radius: 0px;" />

Notice that we have the same four main components as the postal service example:

1. The message itself = the letter
2. The encryption layer = the envelope
3. The IP address of the destination = the recipient's postal address
4. The IP address of the source = the sender's postal address

Just like the postal service, this is how the internet allows us to accomplish all of the tasks that we typically use it for.

For instance, when you opened this webpage, your device sent a message to a public computer on the internet asking for the webpage `home-cloud.io`. Using the information in the message, the public computer then sent a message that included the requested webpage back to you, using the source address of your device.

Pretty cool, huh?

### Okay, so every device on the internet has its own IP address?

Not quite.

Having a public IP address for all devices could be problematic for the same reason that you wouldn't want everyone to know your home address. If someone gets a hold of your home address, they could do bad things like send you junk mail or even harass you. Similarly, if someone could access the address of all your internet devices, they could do things like [DoS you](https://en.wikipedia.org/wiki/Denial-of-service_attack) or try to compromise your devices using vulnerabilities like [zero-days](https://en.wikipedia.org/wiki/Zero-day_vulnerability)."

Because of this (and other reasons we won't go into), the vast majority of devices don't actually have a unique address on the internet. Your phone doesn't, your laptop doesn't, and neither does your TV!

Using the postal service example from before, you can think of all these devices like residents in a big apartment building. People who live in the same building share a single street address. In the same way, your household devices all exist on a smaller network which connects to the internet using a single, shared, *public* IP address.

### Wait, so how do devices talk to each other if they don't all have unique addresses?

Well that's the funny part, they usually don't!

When you send your friend a message over something like WhatsApp or iMessage, your phone doesn't directly talk to their phone at all. Because each phone doesn't have a unique public IP address, they actually communicate with each other through an intermediate device called a server. The server is usually managed by a big company like Facebook or Google, and that server has a *public address*. That means any device on the internet can talk to it.

Your phone sends your message to the server, and then the server forwards that message to your friend's phone. This works fine, but you have to trust the company that runs the server not to peek at the message you’re sending. Also, you’ll have to pay that company to forward your messages for you. (You might pay them directly, via a subscription fee, or pay them indirectly, through your personal data and targeted ads).

But what if you don't want to trust big tech companies and pay them just to send your data? There is another way to get around the shared, public IP address problem. This is by using a [network address translation (NAT)](https://en.wikipedia.org/wiki/Network_address_translation). NAT enabled devices *without* public IP addresses to talk to each other directly *as if they did* have public IPs.

A NAT acts like a mailman in that big apartment building from earlier; accepting mail at the front desk, then delivering it to the apartment of each resident. All residents share a single street address, but they each get a different apartment number so they can receive individualized mail. Thinking back to the previous example, if your device requests the webpage `home-cloud.io` from a public computer on the internet, the computer sends back a message to the public IP address of your NAT, and the NAT forwards the message to your specific device.

### So, how does this apply to Home Cloud?

Great question! Let's summarize what we've discussed so far to bring things full circle...

In order for your *Home Cloud* to replace the big tech clouds from Apple, Google, and others, we need a way for your mobile devices to connect to it from anywhere. What good is your own personal cloud if you can't upload your family photos while on vacation or listen to your favorite music while jogging in the park?

Your Home Cloud device is a server, but it's not a *public server* (like the ones that Facebook or Google manage). This is because your Home Cloud device lives at your house and does not have its own unique *public address*.

This isn't a problem when you're at home, because your phone or laptop can connect to the Home Cloud server directly, using your private network. However, since your Home Cloud server does not have a public IP address, you would lose the ability to connect to it whenever you leave your house.

This leads us to...

#### The core problem:

**We need a way for your mobile devices to connect to your Home Cloud server from anywhere on the internet, and that's hard to do because neither your Home Cloud server nor your mobile device has a unique, public address to send messages to.**


This is where **Home Cloud On the Go** comes in. On the Go is a feature that is built into Home Cloud and provides remote access to your Home Cloud server, with total privacy and security, and *without* the need to trust any companies with your data. *On the Go provides automatic negotiation of direct communication tunnels between your mobile devices and your Home Cloud server across the internet* (don't worry, this sentence will make more sense later). Everything is managed through your personal Home Cloud device, and all data is secured using private keys so you don't have to trust anyone - not even us at Steady Bytes!

## Going Deeper

Okay, at this point we know the [basics](#the-basics) and understand the [core problem](#the-core-problem) we're trying to solve. Now the question is: how do we do it? The answer is the combination of one very neat networking magic trick and a superhero of software security.

### The Locator Server

When you're away from your house, your mobile device doesn't know where on the internet your Home Cloud server lives (the *where* is the public address of the NAT we talked about earlier). We need a way for the mobile device to find the Home Cloud server. To do that, Steady Bytes operates a *public server* on the internet called a **Home Cloud Locator** (this Locator is [completely open-source](https://github.com/home-cloud-io/core/tree/main/services/platform/locator) so you could run one yourself if you'd like).

This Locator server works as a simple negotiator between your mobile device and your Home Cloud server. Let's look at a diagram of how this works:

<img src="/images/blog/locator-diagram.svg" style="border-radius: 0px;" />

The negotiation steps are as follows:

1. Your Home Cloud server creates and maintains a persistent connection to the Locator. This allows the Locator to forward requests to your Home Cloud server whenever it receives them.
2. Your phone sends a request to the Locator for the public address of the NAT your Home Cloud server lives behind (this request includes the public address of the NAT your phone is behind).
3. The Locator forwards the request to your Home Cloud server using the persistent connection from step 1.
4. Your Home Cloud server verifies the phone is allowed to connect (using some private keys previously shared between the phone and the server).
5. The Locator forwards the response from your Home Cloud server to your phone.
6. Your phone and your Home Cloud server establish a direction connection using the NAT addresses they just shared with each other.

You may have noticed something about this process. As we saw in the [basics](#the-basics) section, your phone and your Home Cloud server don’t have unique public addresses on the internet. This means they can only share the public address of *their respective NATs*, which creates an additional problem that we need to solve: If your phone sends a message to your Home Cloud server at the given NAT address, the NAT will simply throw away (or "drop") the message.

Why is that? I'm so glad you asked...

### The Magic Trick

Remember earlier we were talking about how the internet is a dangerous place? Because of this, a NAT will only allow messages from the internet to reach devices it protects if the message passes specific rules.

Let's go over some (overly simplified) examples:

<img src="/images/blog/nat-dropped.svg" style="border-radius: 0px;" />

If device A tries to send a message to device B, the NAT in front of B will drop it because it won't allow some random device on the internet to access device B. This protects B from an attacker which could be trying to send malicious or unwanted messages.

Now let's flip this around. What if we now send a message from device B to device A? What do you think will happen?

<img src="/images/blog/nat-forwarded.svg" style="border-radius: 0px;" />

Wait, what!? Why did NAT A allow that message through!?

Well this is the subtle magic trick we're doing. NATs need to allow messages to devices behind them if the message originates from a device on the internet that the device is already communicating with. This is essential because without this, no device behind a NAT could ever receive data back from a public server on the internet.

For example, when your phone requested the `home-cloud.io` webpage from the public internet server, the server sent a message back with the webpage content and your NAT forwarded that message through to your device because it had just seen the previous message request *from* your phone to the server.

The magic trick here is that if both your phone and your Home Cloud server try to send messages to each other at roughly the same time, we can trick their respective NATs to allow the messages through because it appears like the phone and the server are *already* communicating directly with each other! This is possible because the Locator helped your phone and your Home Cloud server find each other across the internet first!

We now have direct communication between your mobile device and your Home Cloud server, but there's one more thing that we're missing. Let's cover that next.

### The Security Superhero

Now, if you’ve been paying close attention, you might be saying something like, “Hey! You started out by claiming all of this is secure, but doesn’t this mean that anyone could just connect to my Home Cloud server using the public Locator?” And you would be absolutely correct, if it weren’t for this final piece of the puzzle.

The software superhero that solves this issue is a technology called [WireGuard](https://en.wikipedia.org/wiki/WireGuard). WireGuard enables your Home Cloud server to implement a lightweight [virtual private network (VPN)](https://en.wikipedia.org/wiki/Virtual_private_network) between your Home Cloud server and your connected mobile devices. You can think of this VPN like a secure pipe that makes sure data can be sent between your devices without anyone else being able to listen in on what is being said. How is it so secure?

### Private and Secure

WireGuard's core security model uses a private/public key system to ensure messages are only readable by the intended recipients ([key exchange](https://en.wikipedia.org/wiki/Key_exchange) and [symmetric encryption](https://en.wikipedia.org/wiki/Symmetric_encryption)).

Very briefly, this type of cryptography works by generating a very large, random (unguessable) number, and then creating both a public and a private key from that number. You share your public key with anyone you want to send a private message to (the key is truly public, so it doesn't matter who can see it). The person you want to send a message to also needs to share their public key with you. When you want to send a message, you can "lock" your message using *your private key* and *their public key*. When the other person receives your message, they can "unlock" it by using *their private key* and *your public key* using some very fancy math!

Here's a helpful diagram of how this works:

<img src="/images/blog/encryption.svg" style="border-radius: 0px;" />

This technique guarantees that nobody can snoop on any messages you send between yourself and the other person. Remember earlier when we talked about the "envelope" of encryption when sending messages on the internet? Those encryption envelopes all use some form of the process outlined above (there are many variations of this, which we won't cover here).

### How Home Cloud Works

When you enable **On the Go** in your Home Cloud server settings, two things happen:

1. Your Home Cloud server registers with and connects to a public Locator server (you can choose the one hosted by Steady Bytes, host your own, or use a friend's server!).
2. Your Home Cloud server generates private and public WireGuard encryption keys to secure all messages sent to your mobile devices.

Then, you can register your mobile device (using the upcoming Home Cloud mobile app) to be able to connect remotely to your Home Cloud server, and the mobile device will be given its own private and public WireGuard keys by your Home Cloud server. The two devices (your mobile device and your server) can then exchange messages with total privacy and security, using the direct connection that we created with our little [magic trick](#the-magic-trick) from earlier!

One of the most important things about this process is that your Home Cloud server uses these WireGuard keys to encrypt **all** messages between your mobile devices and your Home Cloud server. Even the messages forwarded by the Locator! This means that even if you use the Locator provided by Steady Bytes, we cannot see any of the information on your server, on your mobile devices, or any of the messages passed between them.

## Conclusion

<img src="/images/undraw/undraw_celebration.svg" style="width: 75%;" />

And we're done! Congrats on making it to the end of this lengthy post. I hope you have a much better understanding of how internet communication works and how Home Cloud On the Go enables remote communication between your mobile devices and your Home Cloud server, while preserving both your privacy and your security.

**On the Go** is not quite ready for prime time yet. If you've been following our project update posts, you already know that we've been making a ton of progress and are getting close to the first release of the feature. Everything described in this post is already built and running on our beta user's prototypes. The final piece of the puzzle is developing Home Cloud mobile apps for iOS and Android (laptop operating systems will come later!).

We've already started developing the mobile apps and will hopefully have progress updates on that front soon!

Please [let us know](/contact) if you have any questions or comments about this On the Go feature or anything else regarding Home Cloud. We're building this whole project for you, the people who want to reclaim their digital lives, so all feedback is welcome.


Until the next one,

_Jack_
