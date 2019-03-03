---
title: "Remote Hotspot Trigger on Tizen"
layout: post
date: 2016-06-01
tag: Mobile Device, IoT, Network, Hotspot, Tizen, Android
image: /assets/images/for-projects/hotspot-trigger.png
headerImage: true
projects: true
hidden: true # don't count this post in blog pagination
description: "Hotspot Trigger between Tizen and Android"
category: project
author: injunghwang
externalLink: false
---

# Hotspot Trigger on Tizen

This project was started to make some features on Tizen at the graduate class. So the code is not well written(we made it for 1~2 days without background), but we had focused on making new feature.

Inspired by the functionality in *IOS* of *Apple*, we made Hotspot Trigger.

Under IOS, the devices without cellular network such as *IPAD*
could make the cellular devices turn its own hotspot functionality through bluetooth communication.

Due to this functionality (I call it "**Remote Hotspot Trigger**", for convenience),
user can use IPAD online without cellular network and without doing any bothersome stuffs
such as turning on hotspot & wi-fi on the mobile phone and connect to the phone's network on IPAD.

I and my friend implemented the functionality on the Android and Tizen mobile devices:
Android phone & Tizen Odroid XU3(?) device


Demo is [here][1]

The source codes are here for [server][3] and [clients][2].


[1]:https://www.youtube.com/watch?v=EMwbEZmNppY
[2]:https://github.com/sinban04/tizenProject
[3]:https://github.com/gudbooy/tizentetheredwifi
