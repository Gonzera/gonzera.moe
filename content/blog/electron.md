---
title: "Electron: the 9/11 for desktop apps"
date: 2026-01-23
type: blog
---

Over the past decade, something fundamental has shifted in the way that, we, as a species develop applications for the desktop. And I blame both, electron, and the newer generation.

<!--more-->

But first, we need to ask a very simple question, that prompted me to write this whole thing.

## Why is Spotify using 1GB of RAM just to play music?

This is a very simple question that should outrage anyone that ever used a computer during the 90's or 2000's, and remembers when everything was better. 
Why does a music streaming application needs as much memory as a small video game (Civ IV only needs about 250MB of RAM by the way), just to play a audio file? 

I recently made the mistake of opening Spotify on Windows while playing some vidya. I had one playlist playing in the background. When I checked Task Manager, I saw it: **950MB of RAM usage**. Nearly a entire **gigabyte** of memory, and for what? Video editing? 3D rendering? scientific computation and cool math? Nope, just so I can pay to have the privilege to stream a audio file (with some mid bitrate btw).

Welcome to the Electron era, where everything is chrome, where your music player, chat app and text editor are all secretly a web browser. 

<!-- Cool image -->
<p align="center">
  <img src="/resources/blog/everything_is_chromium.gif" alt="everything_is_chromium">
</p>

## The Electron promise: "Ship Fast And Break Efficiency"

Eletron's selling point is great: Build once, deploy everywhere using already well established web technologies. Need a Windows, macOS, and Linux version? Just wrap your web app in Electron and ship ip.

PMs and developers love it because: 

- Hiring is easier (Finding JS devs? Simple. Finding Windows COM experts? Good luck with that)
- Development speed is fast (Build a new feature in a few days, ship it in a week)
- Cross-platform compatibility (mostly) works out of the box
- Access to npm ecosystem (there's so many cool packages that you 100% need)

Companies love it because they can just put a web developter into a desktop role without training. The result? Desktop applications are now just poorly optimized websites running in a dedicated Chrome instance.

## The slop factory: "Why not replace album covers with a cool video?"

Here's the dark side of that development speed: When everything is easy to implement, anything will get implemented. Eletron doesn't just make it easier to release software. It makes it easier to release bloated software. 

Spotify isn't just a music player anymore. It's also: 

- Social media platform (Because you need to know what your friends are listening to) 
- Multimedia viewer (Remember all the times you listed to a 2 hours podcast while watching it on spotify?)
- Messaging service (I don't even know what to say about this one)
- A browser (so you can buy merch without leaving spotify)

None of these features were requested by users who just wanted to play a audio file. They're the result of a development cycle where adding a new npm package and slapping a React component into the sidebar takes a day.\
The product team asks, "Can we add X?" and the devs will always answer "Sure thing boss it's easy". No one will ever ask, "Should we really put our valuable man hours into this?"

## The performance tax

The math is brutal: 

- Chrome instance: 400MB 
- Spotify "features": 400MB
- Actual audio playback: 5MB

When we look at just the Chrome instance it gets even worse, every Electron app brings its own complete browser engine.\
Open Slack, Discord and Spotify? Yep, now you are running three new Chrome instances. Your computer isn't just running a simple application anymore, it's running three very complex pieces of software, each one pretending to be just a app. 

## The native road not taken

Meanwhile, native alternatives demonstrate what's possible.

- ncspot (terminal UI Spotify client): Uses 80MB with full music streaming functionality
- Apple Music (macOS native): Uses 300MB with similar levels of bloat 

So now we need to ask, where would Spotify need to invest to make something native.

For windows? WinUI\
For macOS? Swift\AppKit\
For Linux? GTK\Qt

Spotify could do all of this, while keep a core library in C++ for all the business logic and DRM needs. 

Would it cost more? Would it take more time? Absolutely, but we are talking about a billion dollar company, I'm sure they can spare some change in order to make the experience of their paying customers a little bit better. 

## Why Spotify (and other companies) will never care 

Here's the hard and uncomfortable truth that makes this entire rant useless:  **NO ONE USES DESKTOP COMPUTERS** 

The generation that grew up with smartphones just doesn't care about desktop apps anymore. And when they use it, it's probably at work, so a miserable experience is to be expected. Why we are here arguing about Electron vs Native apps, Zoomers are asking "Why would I use a Desktop if my phone does the same thing anyways"

Walk into a college or a gen Z workspace (outside of the tech bubble) and you'll see laptops and desktops being used as just machines to run the browser.\
Google Docs, Figma, Canva, Notion, WhatsApp web, YouTube, Netflix. Everything that people need are in the browser, they do not care if Spotify or Slack is yet another browser.

For those people, the Operating System is just a fancy boot loader for the Browser, where all the real computation happens. 

## Conclusion: Two different realities

The way I see it, we have two parallel realities:

**The optimizers and boomers**: Desktop matters, performance matters, software craftsmanship matters, Electron represents the fall of western society.

**The mobile first and zoomers**: Desktops are just tools to be used during school or work, everything is in the cloud, browsers are cool, Electron is irrelevant because they don't even know what it is. 

The worst part? Electron might not be killing desktop development, desktops might just be diying, and Electron is just a sign of that decline. Companies have no monetary incentive to build software for a platform that's slowly becoming a legacy environment. 

Perhaps the worst part is that Spotify uses 1GB of RAM on the desktop, and 95% of Spotify's users will never know. 
